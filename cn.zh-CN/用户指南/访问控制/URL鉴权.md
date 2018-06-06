# URL鉴权 {#concept_tkl_mgd_zdb .concept}

## 功能介绍 {#section_cx5_pgd_zdb .section}

URL鉴权功能旨在保护用户站点的内容资源不被非法站点下载盗用。采用防盗链方法添加 Referer 黑、白名单方式可以解决部分盗链问题。但是，由于 Referer 内容可以伪造，Referer 防盗链方式尚不能完全保护站点资源，因此采用URL鉴权方式保护用户源站资源更为安全有效。

## 工作原理 {#section_g1g_rgd_zdb .section}

URL鉴权功能是通过阿里云CDN加速节点与客户资源站点配合，实现的一种 更为安全可靠的源站资源防盗方法。

1.  由CDN客户站点提供给用户加密 URL（包含权限验证信息）。
2.  用户使用加密后的 URL 向加速节点发起请求。
3.  加速节点对加密 URL 中的权限信息进行验证以判断请求的合法性，正常响应合法请求，拒绝非法请求，从而有效保护CDN客户站点资源。

## URL鉴权方式 {#section_lfq_5gd_zdb .section}

阿里云CDN 兼容并支持A、B、C三种鉴权方式，用户可以根据自己的业务情况，选择合适的鉴权方式，来实现对源站资源的有效保护。

原理说明

用户访问加密 URL 构成

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

鉴权字段描述

**说明：** `PrivateKey` 字段用户可以自行设置。

有效时间1800s指，用户访问客户源服务器时间超过自定义失效时间\(timestamp字段指定\)的1800s后，该鉴权失效。 ，例如用户设置访问时间为 2020-08-15 15:00:00，则链接真正失效时间为2020-08-15 15:30:0

|字段|描述|
|:-|:-|
|timestamp|失效时间，整形正数，固定长度10，1970年1月1日以来的秒数。用来控制失效时间，10位整数，有效时间1800s。|
|rand|随机数，一般设成0|
|uid|暂未使用（设置成0即可\)|
|md5hash|通过md5算法计算出的验证串，数字和小写英文字母混合0-9a-z，固定长度32|

0。

鉴权步骤

1.  CDN服务器拿到请求后，首先会判断请求中的 `timestamp` 是否小于当前时间。
    -   如果 `timestamp` 大于当前时间，则构造出一个同样的字符串\(参考以下sstring构造方式\)。
2.  使用MD5算法算出 `HashValue` ，再和请求中带来的 `md5hash` 进行比对。

    -   比对结果一致，则认为鉴权通过，返回文件。
    -   比对结果不一致，鉴权失败，返回HTTP 403错误。
    **说明：** `HashValue` 是通过以下字符串计算出来的：

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey" （URI是用户的请求对象相对地址，不包含参数，如 /Filename）
    HashValue = md5sum(sstring)
    ```


示例说明

1.  通过 `req_auth` 请求对象：

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  密钥设为：aliyuncdnexp1234 \(由用户自行设置\)。
3.  鉴权配置文件失效日期为 2015年10月10日00:00:00，计算出来的秒数为1444435200。
4.  则CDN服务器会构造一个用于计算Hashvalue的签名字符串：

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234"
    ```

5.  CDN服务器会根据该签名字符串计算HashValue：

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  则请求时url为：

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```


计算得出的HashValue与用户请求中带的 md5hash = 80cd3862d699b7118eed99103f2a3a4f 值一致，鉴权通过。

原理说明

用户访问加密 URL 格式

-   用户访问的 URL 如下：

    ```
    http://DomainName/timestamp/md5hash/FileName
    ```

    加密URL的构造：域名 + 生成URL的时间（精确到分钟）\(timestamp\) + md5值 \(md5hash\)。最后拼接回源服务器的真实路径\(FileName\)，URL有效时间为1800s。

-   当鉴权通过时，实际回源的URL是：

    ```
    http://DomainName/FileName
    ```


鉴权字段描述

**说明：** `PrivateKey`由CDN客户自行设置。

有效时间1800s是指，用户访问客户源服务器时间超过自定义失效时间\(timestamp字段指定\)的1800s后，该鉴权失效。例如用户设置访问时间为 2020-08-15 15:00:00，链接真正失效时间为 2020-08-15 15:30:00。

|字段|描述|
|:-|:-|
|DomainName|CDN客户站点的域名|
|timestamp|资源失效时间，作为URL的一部分，同时作为计算 `md5hash` 的一个因子，格式为： `YYYYMMDDHHMM` ,有效时间1800s|
|md5hash|以timestamp、FileName和预先设定好的 PrivateKey 共同做MD5获得的字符串，即 md5\(`PrivateKey` + `timestamp` + `FileName`\)|
|FileName|实际回源访问的URL \(注意，鉴权时候FileName要以/开头\)|

示例说明

1.  回源请求对象：

    ```
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  密钥设为：aliyuncdnexp1234 \(用户自行设置\)。
3.  用户访问客户源服务器时间为 201508150800（格式为： YYYYMMDDHHMM）。
4.  则CDN服务器会构造一个用于计算 md5hash 的签名字符串：

    ```
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  服务器会根据该签名字符串计算 md5hash：

    ```
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  请求CDN时url：

    ```
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```


计算出来的 md5hash 与用户请求中带的 md5hash = 9044548ef1527deadafa49a890a377f0 值一致，鉴权通过。

原理说明

用户访问加密 URL 格式

-   格式1

    ```
    http://DomainName/{/}/FileName
    ```

-   格式2

    ```
    http://DomainName/FileName{&KEY1=&KEY2=}
    ```

    -   花括号中的内容表示在标准的URL基础上添加的加密信息。
    -   `<md5hash>` 是验证信息经过 MD5 加密后的字符串。
    -   `<timestamp>` 是未加密的字符串，以明文表示。固定长度10，1970年1月1日以来的秒数，表示为十六进制。
    -   采用格式一进行URL加密，例如：

        ```
        http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
        ```

        `<md5hash>` 为 a37fa50a5fb8f71214b1e7c95ec7a1bd`<timestamp>` 为 55CE8100。


鉴权字段描述

`<md5hash>` 部分字段描述：

|字段|描述|
|:-|:-|
|PrivateKey|干扰串，不同客户采用不同的干扰串|
|FileName|实际回源访问的URL \(注意，鉴权时候path要以/开头\)|
|time|用户访问源服务器时间，取 UNIX 时间，以十六进制数字字符表示。|

PrivateKey 取值： `aliyuncdnexp1234`

FileName 取值： `/test.flv`

time 取值： `55CE8100`

因此 md5hash 值为：

```
md5hash = md5sum(aliyuncdnexp1234/test.flv55CE8100) = a37fa50a5fb8f71214b1e7c95ec7a1bd
```

明文：`timestamp = 55CE8100`

这样生成加密 URL：

格式1

```
http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
```

格式2

```
http://cdn.example.com/test.flv?KEY1=a37fa50a5fb8f71214b1e7c95ec7a1bd&KEY2=55CE8100
```

示例说明

用户使用加密的 URL 访问加速节点,CDN服务器会先把加密串 1 提取出来, 并得到原始的 URL 的 `<FileName>` 部分，用户访问时间，然后按照定义的业务逻辑进行验证：

1.  使用原始的 URL 中的 `<FileName>` 部分,请求时间及 PrivateKey 进行 MD5 加密，得到一个加密串。
2.  比较加密串 2 与加密串 1 是否一致，如果不一致则拒绝。
3.  取加速节点服务器当前时间，并与从访问 URL 中所带的明文时间相减，判断是否超过设置的时限 t\(时间域值 t 默认为 1800s\)。
4.  有效时间1800s是指，用户访问客户源服务器时间超过自定义时间的1800s后，该鉴权失效。

    例如用户设置访问时间2020-08-15 15:00:00，链接真正失效时间是2020-08-15 15:30:00。

5.  时间差小于设置时限的为合法请求，CDN加速节点才会给予正常的响应，否则拒绝该请求，返回 http 403错误。

## URL鉴权代码示例 {#section_x4t_cld_zdb .section}

请查看CDN周边工具中 [鉴权代码示例](../../cn.zh-CN/开发指南/周边工具/鉴权代码示例.md#) 文档。

## 操作步骤 {#section_dby_dld_zdb .section}

1.  在 域名管理 页，选择域名，单击**配置**。
2.  在 **访问控制** \> **URL鉴权** 栏，单击 **修改配置**。
3.  在 **URL鉴权配置**栏，您可以自定义设置参数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13476/4608_zh-CN.png)


