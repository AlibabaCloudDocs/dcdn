# Benefits {#concept_nw2_vy2_xdb .concept}

Alibaba Cloud’s Dynamic Route for CDN provides dynamic and static acceleration for dynamic and static resources respectively, improving the access speed of websites that use a combination of dynamic and static content, providing clients with a fast, reliable, and smooth experience. Dynamic Route for CDN currently has four major advantages: stability, speed, ease of extension, and cost-effectiveness.

## Stability {#section_uyq_fz2_xdb .section}

-   Alibaba Cloud Content Delivery Network \(CDN\) uses a global network of 2500+ nodes, 80 Gbps single-node bandwidth, and full-network bandwidth capacity of 120 Tbps. This is sufficient to handle sudden surges in traffic, providing stable acceleration services.
-   Advanced distributed system architecture: Server load is balanced across the entire network to ensure node availability.
-   Stable and efficient performance indicators: Over 95% hit rate and millisecond-level response time.
-   Optimized transmission protocols: Supports HTTP/2 and SPDY transmission protocols for fast, efficient, and stable data transmission.

## Speed {#section_gnh_f1f_xdb .section}

-   Accurate cache: Uses a smart object heat-map algorithm and multi-level, hierarchical cache resources for accurate resource acceleration.

-   High-speed cache: High-performance cache system design, balanced use of CPU multi-core processing capabilities, and optimal use and control of random-access memory to maximize the IOPS and throughput of the solid-state drive \(SSD\).

-   High-speed reading/writing: Each node has high-speed read/write SSD storage. With SSD acceleration capabilities, user access latency is reduced dramatically, and availability is improved.

-   Efficient back-to-origin: With the Session persistence function:

    -   Partitions the back-to-origin path based on the client IP to ensure that logon session information is not accessed across sources. This solves the problem of multi-source sites sharing information.
    -   Provides a failover retry function to ensure efficient back-to-origin and information synchronization.
-   Smart scheduling

    -   Multi-level scheduling strategy: Some node failures do not cause unavailability for users.

    -   Multi-system linkage: Coordinates with the security defense system, refresh system, and the CMS to achieve the best performance for each module.

    -   Data scheduling in real time: Supports node-level traffic prediction to improve both the quality and accuracy of scheduling.

    -   Efficient back-to-origin:

        -   Automatically responds to and adjusts for traffic spikes. Dynamic Route for CDN provides a back-to-origin QPS speed limit to protect the availability of the source site.
        -   The Waiting Room solution can customize waiting pages, waiting time, and release rules to optimize the user experience.

## Ease of extension {#section_b4m_f1f_xdb .section}

-   Resource elastic extension: Charges per actual usage. Full coverage across carriers and across regions can be achieved once accessed.

-   Self-management: With the self-service console, you can add, delete, modify, and search for self-configured domain names. It also enhances and simplifies custom configuration options, and supports custom cache strategies, HTTP response headers, and other functions.

-   API interface: Provides services such as service opening, content refreshing, obtaining security monitoring data, downloading distribution logs, and so on.

-   Performance optimization

    -   Smart compression: Intelligently compresses network transmission content, effectively reducing the number of bytes transmitted over the network, shortening data transmission times, and improving acceleration.

    -   Page optimization: Removes redundant content such as spaces, line breaks, tabs, and comments on the page, reduces the size of the page itself, and combines multiple JavaScript/CSS files into one request, thereby reducing the total number of requests.

    -   Refresh/warm up: Provides the ability to refresh the cache and warm up resources for the node in advance.


## Cost-effectiveness {#section_etq_f1f_xdb .section}

-   Optimal linking: Makes routing decisions to select the best back-to-origin path, using source site monitoring, real-time network quality detection, and smart routing technology for dynamic content.

-   Link multiplexing: Edge acceleration nodes receive user connections and establish a long link based on actual back-to-origin requests, effectively reducing the I/O consumption of source sites and relieving pressure on source sites.

    -   Analyzes upstream and downstream traffic conditions to ensure that the terminal is reached within a limited number of hops, avoiding public network failures and network congestion paths.
    -   The last hop adopts BGP/multi-line access nodes to ensure efficient back-to-origin from the same region and the same carrier.

