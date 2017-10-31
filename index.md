---

copyright:
  years: 2017
lastupdated: "2017-09-12"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Getting started with Zelle® {{site.data.keyword.real_time_payments_short}} 
{: #getting_started_real_time_payments_short}

The Zelle® {{site.data.keyword.real_time_payments_short}} service leverages IBM Financial Transaction Manager's sophisticated capabilities to manage participants, tokens and receivers, to initiate payments and payment requests and to view the status of the payments hub.
{:shortdesc}

IBM Financial Transaction Manager is trusted by the world's largest financial institutions to meet their payment processing needs. 

The APIs and Zelle® {{site.data.keyword.real_time_payments_short}} are real services hosted in Bluemix that you can test with. Other supporting systems such as the accounting system and network responses are simulated. So, some responses may differ from a full production system.

## Before you begin

The following steps show you how to obtain access to the Zelle® {{site.data.keyword.real_time_payments_short}} service and invoke API methods. To use the Zelle® {{site.data.keyword.real_time_payments_short}} REST API, it is important that you understand the basics of RESTful web services and JSON representations.

You must install cURL before you can use the service.

## Step 1: Getting your credentials

1. Create an instance of the service.
2. Review the service instance access credentials, similar to the following example:
```
{
  "accessToken": "<api-key>",
  "uri": "<service-url>"
}
```

## Step 2: Call the REST API

To use the following example, replace api-key with your service key and service-url with the URL for your service.

```
curl -X GET -H "Accept: application/json" -H "X-IBM-Access-Token: <api-key>" <service-url>/fxh/svc/inboundtransactions/
```

{:codeblock}

The following is an example of a response to a successful request:

```
[
  {
    "accountNumber": null,
    "amount": {
      "currency": "USD",
      "value": 1.01
    },
    "bankCode": null,
    "batchId": 1087,
    "batchType": "FTM Batch",
    "currency": "USD",
    "destination": "123456780",
    "destinationAccountNumber": "222333444",
    "destinationBankCode": "123456780",
    "entryDate": null,
    "filename": "PaymentFile",
    "messageStandard": "RTP",
    "messageType": "RTP_Orig",
    "methodOfPayment": "Y",
    "originator": "ZImfQ1",
    "outboundMessageStandard": "NACHA",
    "outboundMessageType": "CCD",
    "paymentState": "3",
    "paymentType": "D",
    "productCode": "ACH",
    "received": "2017-09-12T18:37:39.508+0000",
    "receiver": "FGB FGB",
    "recordType": 125,
    "referenceNumber": "FGB000000705",
    "rejectsAndWarnings": 0,
    "transactionId": 705,
    "transactionType": "C",
    "transmissionId": 476,
    "transmissionType": "RTP",
    "validationResults": 0
  }
]

```

{:codeblock}
