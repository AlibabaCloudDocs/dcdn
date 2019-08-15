# Copy configurations {#task_827751 .task}

This topic describes how to copy one or more configurations of a DCDN domain to another or multiple DCDN domains.

Ensure that the domain from which you copy configurations has been enabled and appropriately configured.

Note the following points when you copy configurations of a domain:

-   The coped configurations will overwrite the existing configurations of the domain. Therefore, exercise cautions when performing the operation.
-   The copy operation cannot be undone. The domain from which you copy configurations is enabled and provides a high operational bandwidth. The domain from which you copy configurations is active.

1.  Log on to the [Dynamic Route for CDN console](https://dcdn.console.aliyun.com/overview).
2.  On the Domain Names page, find the domain from which you want to copy configurations, click **Copy Configuration**. 

    ![](images/50048_en-US.png)

3.  Select the configuration items you want to copy, and click **Next**. 

    **Note:** 

    -   The origin information cannot be copied at the same time as the other information.
    -   An HTTPS certificate cannot be copied.
    -   Custom HTTP origin headers are copied incrementally. For example, if Domain A has two custom HTTP origin headers and you copy another five HTTP origin headers from Domain B to Domain A, Domain A has seven custom HTTP origin headers.
    -   The HTTP headers are not incrementally copied. For example, if the cache\_control HTTP header is set to private for Domain A and to public for Domain B and you copy the HTTP header configuration of Domain B to Domain A, the cache\_control HTTP header of Domain A is set to public.
    -   If you copy switch-related configurations or Refer or IP address blacklists or whitelists, the new configurations overwrite the original configurations of the target domains.
    -   The new configurations overwrite the original configurations of the target domains.
    ![Select configuration items](images/50049_en-US.png)

4.  Select the domains to which you want to copy the configurations, and click **Next**. You can enter a keyword in the search bar to search for a domain.

    ![Select domain](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15658488238717_en-US.png)

5.  In the **Copy Configurations** dialog box, click **OK**. 

    ![Copy configuration confirmation](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15658488248719_en-US.png)


