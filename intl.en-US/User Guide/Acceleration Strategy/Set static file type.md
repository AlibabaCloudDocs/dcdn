# Set static file type {#concept_afy_fbx_ydb .concept}

## Introduction {#section_hvd_jbx_ydb .section}

The feature allows you to specify static file types by filename extension. The specified static files no longer use dynamic acceleration. Instead, they use static acceleration and allocate the best CDN nodes for caching and distribution.

## Procedure {#section_d4j_kbx_ydb .section}

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Acceleration Rules** \> **Static File Types**, and click **Modify**.
3.  Select static file types. The specified files are cached and CDN nodes do not need to request them from the origin site.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13462/15456325444414_en-US.png)

