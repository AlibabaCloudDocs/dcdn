# Websocket {#concept_dpc_q4q_kfb .concept}

This document describes the technical details, benefits, and applicable scenarios of Websocket and how to use Websocket.

## What is Websocket {#section_q1j_rcn_mfb .section}

WebSocket is a protocol for creating a bi-directional message exchange between browsers and servers over a persistent TCP connection. WebSocket supports full-duplex communications that allow the server to send data to the client actively. Therefore, WebSockets requires only one handshake to establish a bi-directional, full-duplex, persistent connection from a web browser to a server. This makes the message exchange between clients and servers much simpler.

## Benefits {#section_ics_mdn_mfb .section}

-   Short header: The data exchanged between clients and servers contains a very short header. The header has a minimum size of 2 Bytes.
-   Instead of returning data after receiving a request from the browser, the server actively pushes data to the browser when new data is available.

Many websites are using Ajax polling to facilitate push technologies. With the polling technique, the browser sends HTTP requests to the server at specific intervals, for example, every one second, and the server returns the most recent data to the browser of the client.

The disadvantage of this model is that the browser has to send the HTTP request to the server every time a request occurs. However, the HTTP request can have a long header, and the valid data can be only a small part of the header. Sending such HTTP requests is a waste of bandwidth and other resources. The WebSocket protocol defined by HTML5 can conserve server resources and bandwidth, and facilitate real-time communication.

The WebSocket protocol defined by HTML5 can conserve server resources and bandwidth, and facilitate real-time communication.

## Scenarios {#section_gf5_dfn_mfb .section}

-   Live comments

    End user A sends a live comment through a mobile phone. At the same time, the user A wants to view live comments sent by other clients on the mobile phone. In this scenario, you can use Websocket to push the live comments sent by other clients to the mobile phone of the user A. So the user A can also view the live comments sent by other users.

-   Online education

    In one-to-many online education, the teacher can use Websocket to push the notes and syllabuses edited on the teacher's client to the students' clients in real time.

-   Real-time quotes for financial products

    The price of financial products such as stocks and gold changes quickly. With Websocket, the real-time price of financial products can be pushed to clients around the world to help traders make quick trading decisions.

-   Live sportscast

    Live sportscast is the top concern for numerous sports lovers all over the world. Websocket allows for real-time updates in live sportscast to ensure the best viewing experience.

-   Video conferences

    Video conferences are widely used in multiple scenarios. In a video conference, participants join the conference through multiple ends. Websocket helps to deliver real-time information to these participants.

-   Geo-location-based applications

    An increasing number of developers are using the GPS feature of mobile devices to facilitate geo-location-based applications. If you have kept a record of the end user's location, for example, the user's movement trails recorded by an app, you can use Websocket to collect more detailed data.


## Activate Websocket {#section_r3v_d3n_mfb .section}

You must first specify the billing method of Websocket and wait until the billing method takes effect before you use Websocket.

1.  Log on to the [DCDN console](https://dcdn.console.aliyun.com).
2.  Click **Change Billing Method**.
3.  Click **Activate** to activate Websocket.
4.  Wait until Websocket is activated.

    **Note:** 

    -   If you are a new user, the billing of Websocket takes effect immediately.
    -   If you have purchased Websocket before, when the billing method is **Pay By Day**, Websocket takes effect on the next natural day. When the billing type is **Pay By Month**, Websocket takes effect at 00:00 on the first day of the next month. Keep the current billing items if the billing method has not changed.

For more information about Websocket billing, see [Billing methods](https://www.alibabacloud.com/product/cdn/pricing?spm=a2c63.p38356.a3.4.106168d8IxL0Wg).

## Use Websocket {#section_ymp_p4n_mfb .section}

You can configure Websocket after it takes effect.

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  In the left-side navigation pane, click **Websocket**.
3.  Click the Websocket toggle, and set the interval for sending and receiving heartbeats and specify the protocol used for sending back-to-origin requests.

    **Note:** The interval is set to 60 seconds by default. The protocol used for sending back-to-origin requests is not specified by default. Specify it based on your needs.

    -   Heartbeat interval: A heartbeat is a periodic signal generated to indicate normal operation. The client sends a message to the server at intervals to indicate the status of the client. The server returns a message to the client to indicate the status of the server. In this way, the client and the server can know whether the other end is connected properly. The time between heartbeat flows is referred to as a heartbeat interval.
    -   The protocol type used for sending back-to-origin requests can be HTTP, HTTPS, or Follow.

## Websocket statistics {#section_u2f_msn_mfb .section}

Granularity supported by different statistics types on multiple time dimensions are as follows:

|Type of statistics|Within 3 days|4 - 31 days|Greater than or equal to 32 days|
|------------------|-------------|-----------|--------------------------------|
|Bandwidth and traffic statistics|Five minutes or one hour|One hour or one day|One day|
|HTTP code statistics|

Queries by region, service provider, domain name, and time range are supported. You can query a maximum time range of three months.

