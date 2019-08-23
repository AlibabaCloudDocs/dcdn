# API概览 {#doc_1188128 .concept}

全站加速提供以下相关API接口。

## 域名配置接口 {#section_nyc_ksk_iok .section}

|API|描述|
|---|--|
|[DescribeDcdnDomainConfigs](cn.zh-CN/API参考/域名配置接口/DescribeDcdnDomainConfigs.md)|调用DescribeDcdnDomainConfigs查询域名配置，一次可查询多个功能配置。|
|[BatchDeleteDcdnDomainConfigs](cn.zh-CN/API参考/域名配置接口/BatchDeleteDcdnDomainConfigs.md)|调用BatchDeleteDcdnDomainConfigs批量删除域名配置。|
|[BatchSetDcdnDomainConfigs](cn.zh-CN/API参考/域名配置接口/BatchSetDcdnDomainConfigs.md)|调用BatchSetDcdnDomainConfigs实现域名批量配置功能。|
|[DeleteDcdnSpecificConfig](cn.zh-CN/API参考/域名配置接口/DeleteDcdnSpecificConfig.md)|调用DeleteDcdnSpecificConfig指定删除某个域名的某个配置。|

## 数据监控接口 {#section_vgk_d2e_r5c .section}

|API|描述|
|---|--|
|[DescribeDcdnDomainPvData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainPvData.md)|调用DescribeDcdnDomainPvData获取加速域名最小1小时粒度的PV页面访问统计。|
|[DescribeDcdnDomainHttpCodeData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainHttpCodeData.md)|调用DescribeDcdnDomainHttpCodeData获取加速域名最小5分钟粒度的HTTP返回码占比数据。|
|[DescribeDcdnDomainTopReferVisit](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainTopReferVisit.md)|调用DescribeDcdnDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。|
|[DescribeDcdnDomainUvData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainUvData.md)|调用DescribeDcdnDomainUvData获取加速域名最小1小时粒度的UV页面独立访问统计。|
|[DescribeDcdnDomainRegionData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRegionData.md)|调用DescribeDcdnDomainRegionData获取加速域名天粒度的用户区域分布数据统计。|
|[DescribeDcdnTopDomainsByFlow](cn.zh-CN/API参考/数据监控接口/DescribeDcdnTopDomainsByFlow.md)|调用DescribeDcdnTopDomainsByFlow获取用户按流量排名的域名。|
|[DescribeDcdnDomainHitRateData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainHitRateData.md)|调用DescribeDcdnDomainHitRateData获取加速域名的命中率。|
|[DescribeDcdnDomainTopUrlVisit](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainTopUrlVisit.md)|调用DescribeDcdnDomainTopUrlVisit获取加速域名某天内的热门URL列表。|
|[DescribeDcdnUserQuota](cn.zh-CN/API参考/数据监控接口/DescribeDcdnUserQuota.md)|调用DescribeDcdnUserQuota查询用户资源上限及已使用情况。|
|[DescribeDcdnDomainRealTimeSrcTrafficData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeSrcTrafficData.md)|调用DescribeDcdnDomainRealTimeSrcTrafficData获取加速域名的1分钟回源流量监控数据，单位bit。|
|[DescribeDcdnDomainRealTimeQpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeQpsData.md)|调用DescribeDcdnDomainRealTimeQpsData获取域名1分钟粒度每秒访问次数数据。|
|[DescribeDcdnDomainRealTimeSrcBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeSrcBpsData.md)|调用DescribeDcdnDomainRealTimeSrcBpsData获取域名一分钟粒度回源带宽数据。|
|[DescribeDcdnDomainRealTimeHttpCodeData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeHttpCodeData.md)|调用DescribeDcdnDomainRealTimeHttpCodeData获取加速域名1分钟粒度的HTTP返回码占比数据。|
|[DescribeDcdnDomainRealTimeByteHitRateData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeByteHitRateData.md)|调用DescribeDcdnDomainRealTimeByteHitRateData获取域名1分钟粒度字节命中率数据。|
|[DescribeDcdnDomainRealTimeBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeBpsData.md)|调用DescribeDcdnDomainRealTimeBpsData获取域名1分钟粒度带宽数据。|
|[DescribeDcdnDomainRealTimeReqHitRateData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainRealTimeReqHitRateData.md)|调用DescribeDcdnDomainRealTimeReqHitRateData获取域名1分钟粒度请求命中率数据。|
|[DescribeDcdnDomainIspData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainIspData.md)|调用DescribeDcdnDomainIspData获取加速域名天粒度的用户运营商分布数据统计。|
|[DescribeDcdnDomainQpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainQpsData.md)|调用DescribeDcdnDomainQpsData获取加速域名的每秒访问次数QPS。|
|[DescribeDcdnDomainBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainBpsData.md)|调用DescribeDcdnDomainBpsData获取加速域名的网络带宽监控数据。|
|[DescribeDcdnDomainTrafficData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainTrafficData.md)|调用DescribeDcdnDomainTrafficData获取加速域名的网络流量监控数据，单位：byte。|
|[DescribeDcdnDomainOriginBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainOriginBpsData.md)|调用DescribeDcdnDomainOriginBpsData获取加速域名的回源带宽监控数据。|
|[DescribeDcdnDomainOriginTrafficData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainOriginTrafficData.md)|调用DescribeDcdnDomainOriginTrafficData获取加速域名的回源流量监控数据，单位：bit。|
|[DescribeDcdnDomainWebsocketHttpCodeData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainWebsocketHttpCodeData.md)|调用DescribeDcdnDomainWebsocketHttpCodeData获取加速域名websocket协议的最小5分钟粒度的HTTP返回码占比数据。|
|[DescribeDcdnDomainWebsocketBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainWebsocketBpsData.md)|调用DescribeDcdnDomainWebsocketBpsData获取加速域名websocket协议的网络带宽监控数据。|
|[DescribeDcdnDomainIpaBpsData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainIpaBpsData.md)|调用DescribeDcdnDomainIpaBpsData获取加速域名四层加速的网络带宽监控数据。|
|[DescribeDcdnDomainWebsocketTrafficData](cn.zh-CN/API参考/数据监控接口/DescribeDcdnDomainWebsocketTrafficData.md)|调用DescribeDcdnDomainWebsocketTrafficData获取加速域名的 websocket 网络流量监控数据，单位：byte。|

## 域名管理接口 {#section_atx_jpl_2sq .section}

|API|描述|
|---|--|
|[StartDcdnDomain](cn.zh-CN/API参考/域名管理接口/StartDcdnDomain.md)|调用StartDcdnDomain启用状态为停用的加速域名，将DomainStatus变更为online。|
|[UpdateDcdnDomain](cn.zh-CN/API参考/域名管理接口/UpdateDcdnDomain.md)|调用UpdateDcdnDomain修改加速域名。|
|[DeleteDcdnDomain](cn.zh-CN/API参考/域名管理接口/DeleteDcdnDomain.md)|调用DeleteDcdnDomain删除已添加的加速域名。|
|[BatchStopDcdnDomain](cn.zh-CN/API参考/域名管理接口/BatchStopDcdnDomain.md)|停用加速域名，将DomainStatus变更为offline。|
|[BatchStartDcdnDomain](cn.zh-CN/API参考/域名管理接口/BatchStartDcdnDomain.md)|调用BatchStartDcdnDomain启用状态为“”停用“”的加速域名，将DomainStatus变更为online。|
|[StopDcdnDomain](cn.zh-CN/API参考/域名管理接口/StopDcdnDomain.md)|调用StopDcdnDomain停用某个加速域名，将DomainStatus变更为offline。|
|[AddDcdnDomain](cn.zh-CN/API参考/域名管理接口/AddDcdnDomain.md)|调用AddDcdnDomain添加全站加速域名，一次只能提交一个加速域名。|
|[DescribeDcdnDomainCname](cn.zh-CN/API参考/域名管理接口/DescribeDcdnDomainCname.md)|调用DescribeDcdnDomainCname检测用户是否完成Cname，支持多个域名。|
|[DescribeDcdnDomainCertificateInfo](cn.zh-CN/API参考/域名管理接口/DescribeDcdnDomainCertificateInfo.md)|调用DescribeDcdnDomainCertificateInfo获取指定加速域名证书信息。|
|[SetDcdnDomainCertificate](cn.zh-CN/API参考/域名管理接口/SetDcdnDomainCertificate.md)|调用SetDcdnDomainCertificate设置某域名下证书功能是否启用，以及修改证书信息。|
|[DescribeDcdnUserDomains](cn.zh-CN/API参考/域名管理接口/DescribeDcdnUserDomains.md)|调用DescribeDcdnUserDomains查询用户名下所有的全站加速域名。支持域名模糊匹配过滤和域名状态过滤。|
|[DescribeDcdnDomainDetail](cn.zh-CN/API参考/域名管理接口/DescribeDcdnDomainDetail.md)|调用DescribeDcdnDomainDetail获取指定加速域名配置的基本信息。|
|[DescribeDcdnCertificateDetail](cn.zh-CN/API参考/域名管理接口/DescribeDcdnCertificateDetail.md)|调用DescribeDcdnCertificateDetail获取证书详细信息。|
|[DescribeDcdnCertificateList](cn.zh-CN/API参考/域名管理接口/DescribeDcdnCertificateList.md)|调用DescribeDcdnCertificateList获取证书列表信息。|

## 日志类接口 {#section_6xh_jqo_s85 .section}

|API|描述|
|---|--|
|[DescribeDcdnDomainLog](cn.zh-CN/API参考/日志类接口/DescribeDcdnDomainLog.md)|调用DescribeDcdnDomainLog获取指定域名的原始访问日志的下载地址。|

## 服务类接口 {#section_xl5_ttb_ajv .section}

|API|描述|
|---|--|
|[DescribeUserDcdnStatus](cn.zh-CN/API参考/服务类接口/DescribeUserDcdnStatus.md)|调用DescribeUserDcdnStatus查询全站加速是否开通，是否欠费。|
|[DescribeDcdnUserResourcePackage](cn.zh-CN/API参考/服务类接口/DescribeDcdnUserResourcePackage.md)|调用DescribeDcdnUserResourcePackage查询DCDN用户当前流量包。|
|[DescribeDcdnService](cn.zh-CN/API参考/服务类接口/DescribeDcdnService.md)|调用DescribeDcdnService查询DCDN服务状态。包括：当前计费类型、服务开通时间、下次生效的计费类型、当前业务状态等。|

## 刷新预热接口 {#section_pqt_lbq_2yg .section}

|API|描述|
|---|--|
|[DescribeDcdnRefreshTasks](cn.zh-CN/API参考/刷新预热接口/DescribeDcdnRefreshTasks.md)|调用DescribeDcdnRefreshTasks查询刷新、预热状态是否在全网生效。|
|[RefreshDcdnObjectCaches](cn.zh-CN/API参考/刷新预热接口/RefreshDcdnObjectCaches.md)|调用RefreshDcdnObjectCaches刷新节点上的文件内容，刷新指定URL内容至Cache节点。支持URL批量刷新。|
|[PreloadDcdnObjectCaches](cn.zh-CN/API参考/刷新预热接口/PreloadDcdnObjectCaches.md)|调用PreloadDcdnObjectCaches将源站的内容主动预热到L2 Cache节点上，用户首次访问可直接命中缓存，缓解源站压力。|
|[DescribeDcdnRefreshQuota](cn.zh-CN/API参考/刷新预热接口/DescribeDcdnRefreshQuota.md)|调用DescribeDcdnRefreshQuota查询当日剩余刷新、预热URL及目录的次数。|

## IPA接口 {#section_ayq_swe_ukh .section}

|API|描述|
|---|--|
|[DescribeDcdnIpaDomainConfigs](cn.zh-CN/API参考/IPA接口/DescribeDcdnIpaDomainConfigs.md)|调用DescribeDcdnIpaDomainConfigs查询域名配置，一次可查询过个功能配置。|
|[StopDcdnIpaDomain](cn.zh-CN/API参考/IPA接口/StopDcdnIpaDomain.md)|调用StopDcdnIpaDomain停用某个加速域名，将DomainStatus变更为offline。|
|[DescribeUserDcdnIpaStatus](cn.zh-CN/API参考/IPA接口/DescribeUserDcdnIpaStatus.md)|调用DescribeUserDcdnIpaStatus查询全站加速IPA是否开通，是否欠费。|
|[DescribeDcdnIpaService](cn.zh-CN/API参考/IPA接口/DescribeDcdnIpaService.md)|调用DescribeDcdnIpaService查询全站加速ipa服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。|
|[ModifyDCdnDomainSchdmByProperty](cn.zh-CN/API参考/IPA接口/ModifyDCdnDomainSchdmByProperty.md)|调用ModifyDCdnDomainSchdmByProperty修改加速域名。|
|[UpdateDcdnIpaDomain](cn.zh-CN/API参考/IPA接口/UpdateDcdnIpaDomain.md)|调用UpdateDcdnIpaDomain修改加速域名。|
|[DeleteDcdnIpaDomain](cn.zh-CN/API参考/IPA接口/DeleteDcdnIpaDomain.md)|调用DeleteDcdnIpaDomain删除已添加的加速域名。|
|[StartDcdnIpaDomain](cn.zh-CN/API参考/IPA接口/StartDcdnIpaDomain.md)|调用StartDcdnIpaDomain启用状态为停用的加速域名，将DomainStatus变更为online。|
|[AddDcdnIpaDomain](cn.zh-CN/API参考/IPA接口/AddDcdnIpaDomain.md)|调用AddDcdnIpaDomain添加IP4层应用加速域名，一次只能提交一个加速域名。|
|[BatchSetDcdnIpaDomainConfigs](cn.zh-CN/API参考/IPA接口/BatchSetDcdnIpaDomainConfigs.md)|调用BatchSetDcdnIpaDomainConfigsIP4层应用加速域名批量配置。|
|[DescribeDcdnIpaUserDomains](cn.zh-CN/API参考/IPA接口/DescribeDcdnIpaUserDomains.md)|调用DescribeDcdnIpaUserDomains查询用户名下所有的IP4层应用加速域名。|
|[DescribeDcdnIpaDomainDetail](cn.zh-CN/API参考/IPA接口/DescribeDcdnIpaDomainDetail.md)|调用DescribeDcdnIpaDomainDetail获取指定加速域名配置的基本信息|

