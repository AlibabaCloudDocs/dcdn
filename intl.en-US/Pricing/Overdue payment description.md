# Overdue payment description {#concept_qms_jhf_xdb .concept}

## About service suspension {#section_mqp_4hf_xdb .section}

-   If you do not pay the bill for a Dynamic Route for CDN service, the service goes into outstanding payment.
-   If your service remains in arrears for 24 hours, your service is suspended. In the 24 hours before your service is suspended, the system sends an email or an SMS reminding you to pay the overdue bill.

    -   If you top up within 24 hours of your account entering arrears, your service is not suspended.
    -   If you do not top up in time, your Dynamic Route for CDN service is suspended. The cache resources you are then using are released, but your configuration information is retained for 12 months.

## Balance warning prompt { .section}

|Billing method|Judgment basis|Forecast|
|:-------------|:-------------|:-------|
|PayByBandwidth|Amount payable for the last billing cycle \(days\)|Whether the balance in your account sufficient for payment of the next billing cycle \(days\)|
|PayByTraffic|The average amount payable under the bill for the last seven hours|Whether the balance in your account is sufficient for payment of the next three billing cycles|

If the balance in your account is insufficient, the system sends you an SMS or email warning.

**Note:** If you have enabled the balance warning feature, \(**console** \> **Account Management** \> **Balance Warning ON/OFF**\), the system sends you an SMS or email warning when the balance in your account is under the threshold you have set.

