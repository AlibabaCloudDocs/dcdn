# Drag/Drop playback {#concept_lxw_mnd_zdb .concept}

## Introduction {#section_tx2_pnd_zdb .section}

In a video-on-demand scenario, when the playback progress bar is dragged, the end user will send a URL request, such as `http://www.aliyun.com/test.flv?start=10,` to the server. The server returns the data from the key frame prior to the10th second to the client \(if start=10 is not the key frame\).

After receiving such a request from an end user and the Drag/Drop Playback function is enabled, a CDN node can directly return the data from the key frame prior to the10th second \(If start=10 is not the key frame\) \(FLV format\) or from the 10th second to the end user. Files of MP4 and FLV format are supported.

|File Format|Meta Information|start Parameter|Example|
|:----------|:---------------|:--------------|:------|
|MP4|Meta information of an origin site video must be contained in the file header. A video with its meta information contained in the file tail is not supported.|The start parameter specifies the time in seconds. Decimals are supported to indicate milliseconds. For example, start=1.01 indicates that the start time is 1.01s. If the current start is not a key frame, DCDN locates the key frame prior to the time specified by the start parameter.|http: //domain/video.mp4?start=10 requests to play a video from the 10th second.|
|FLV|An origin site video must contain meta information.|The start parameter specifies a byte. If the current start is not a key frame, the DCDN automatically locates the key frame prior to the frame specified by the start parameter.|http:// domain/video.flv?start=10 requests to play a video from the 10th byte.|

## Note {#section_b42_5nd_zdb .section}

-   To use the drag/drop playback feature, an origin site must support Range requests. The origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.
-   Files of MP4 and FLV format are supported.
-   Currently, flv format only supports audio aac and video avc coding formats. Drag and drop are not supported for other coding formats.

## Procedure {#section_vr1_vnd_zdb .section}

1.  On the Domain Names page, select a domain, and click **Configure**.
2.  Go to **Optimization \>** \> **Drag/Drop Playback** to enable this function.

    ![](images/4665_en-US.png)


