# Private OSS bucket back-to-source {#concept_hk4_l5w_ydb .concept}

## Function introduction {#section_wzm_t5w_ydb .section}

Private OSS bucket back-to-origin authorization means that if the acceleration domain name is to be returned to the user account and marked as a private OSS bucket \(referred to as a private bucket\), authorization must be performed first. If authorization is successful and authorization configuration is enabled, the user can access the private bucket only after the domain name is authorized by the private bucket.

## Risk warnings {#section_zqh_55w_ydb .section}

-   If authorization succeeds and the private bucket feature of the corresponding domain name is enabled, the acceleration domain can access resources in your private bucket. Before you enable this function, carefully consider your business requirements.

    **Note:** bucket content is not suitable as a back-to-origin source for CDN acceleration domain names.

-   You can use the functions provided by CDN, such as **OSS Anti-Leech\(Referer\)**, **Authentication** and so on, to effectively secure your resources.
-   If your website is at risk of attack, we recommend that you purchase the Anti-DDoS Pro service. Moreover, do not authorize or enable the private OSS bucket function.

## Procedure {#section_kcw_y5w_ydb .section}

Enable Private Bucket Back-to-Origin Authorization

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Basic Settings** \> **Origin Information**, and click **Modify**.
3.  In **Back-to-Origin Settings** \> **Private Bucket Back-to-Origin Settings** \> **Service Access Authorization**, click **Immediate Authorization**.
4.  Authorization successful. Click **OK** to enable private OSS bucket back-to-source for the domain name.
5.  Operation successful.

Turn off private Bucket back-to-origin authorization

1.  Go to **Resource Access Management** \> **Role Management**.
2.  **Delete** the roles you want to remove.
3.  Private bucket authorization removal successful.

    **Note:** If your acceleration domain name is using a private bucket as the source site for back-to-origin, do not close or remove the private bucket authorization.


