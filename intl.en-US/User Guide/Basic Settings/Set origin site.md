# Set origin site {#concept_umy_yqw_ydb .concept}

## Origin types {#section_jpw_zqw_ydb .section}

The origin types include IP, OSS domain, and origin domain.

-   IP: Enter the server outer network IP. You can enter multiple IPs and configure their priorities. Alibaba Cloud ECS IP can be exempted from verification.

-   OSS domain: You can directly select OSS buckets under the same account, or manually enter the external domain name of the OSS, such as `xxx.oss-cn-hangzhou.aliyuncs.com`. You can view the external domain name of the OSS in the OSS console.

-   Origin domain: Enter the domain name of your origin site. You can configure multiple origin site domain names and set their priorities.

**Note:** The origin domain name cannot be the same as the DCDN domain name. Otherwise, an origin fetch loop is caused. For example, if your DCDN domain name is `cdn.example.com`, we recommend that you set the origin site to `src.example.com`.


## Multiple origin sites {#section_czy_2rw_ydb .section}

When you set the origin type to IP or origin domain, you can configure multiple origin sites and set their priorities. Acceleration nodes perform origin fetch according to their priorities.

## Ports {#section_vpb_grw_ydb .section}

Ports 80 \(for HTTP\) and 443 \(for HTTPS\) are currently supported. Custom ports are not currently supported.

![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65086/cn_zh/1533109379037/D20.png)

