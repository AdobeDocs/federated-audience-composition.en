---
audience: end-user
title: Get started with compositions
description: Learn how to start with compositions
exl-id: 92142d16-3483-4f6e-afde-9f88d5d7d1c4
---
# Privacy requests {#track-changes}

<!--TO UPDATE WITH ANSWERS FROM DOCAC-12036-->

Once you created a composition, the resulting audiences are saved into Adobe Experience Platform. You can then make privacy requests to access and/or delete profile data corresponding to these audiences through Adobe Experience Platform **Privacy Service**, which provides a RESTful API and user interface to help you manage customer data requests.

With Privacy Service, you can submit requests to access and delete personal customer data from Adobe Experience Cloud applications, facilitating automated compliance with legal and organizational privacy regulations.

Privacy requests can be created and managed from the **[!UICONTROL Requests]** menu.<!--TBC in FAC-->

![](assets/requests.png)<!--replace with screenshot specific to FAC if any)-->

For more information on the Privacy Service and how to create and manage privacy requests, refer to Adobe Experience Platform documentation:

* [Privacy Service overview](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"}
* [Managing privacy jobs in the Privacy Service UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html){target="_blank"}
* [Privacy Service API Guide](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/api/overview){target="_blank"}

## Managing individual data privacy requests that you can send to Adobe Adobe Federated Audience Composition {#data-privacy-requests}

You can submit individual requests to access and delete consumer data from Adobe Adobe Federated Audience Composition in two ways:

* Through the **Privacy Service UI**. See the documentation [here](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/ui/user-guide#_blank).
* Through the **Privacy Service API**. See the documentation [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/#_blank) and API information [here](https://developer.adobe.com/experience-platform-apis/#_blank).

The Privacy Service supports two types of requests: **data access** and **data deletion**.

>[!NOTE]
>
>To make privacy requests for Adobe Journey Optimizer, refer to this [guide]. If you also plan to make privacy requests for the Platform data lake, refer to this [guide](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/privacy){target="_blank"} in addition to this tutorial. For Real time customer profile, please refer to this [guide](https://experienceleague.adobe.com/en/docs/experience-platform/profile/privacy){target="_blank"} and for Identity service, please refer to this [guide](https://experienceleague.adobe.com/en/docs/experience-platform/identity/privacy){target="_blank"}. For delete and access requests you need to call these individual systems to make sure the requests are handled by each of them. Making a privacy request to Adobe Journey Optimizer will not remove data from all these systems.

For **access requests**, specify "Adobe Federated Audience Composition"?? from the UI (or "FAC" as a product code in the API).

For **delete requests**, in addition to the "Adobe Federated Audience Composition" request, you must also submit delete requests to three upstream services to prevent Federated Audience Composition from reinjecting the deleted data. If these upstream services are not specified, the "Adobe Federated Audience Composition" request will remain in the "processing" state until delete requests for the upstream services are created.

The three upstream services are:

* Profile (product code: "profileService")
* AEP Data Lake (product code: "AdobeCloudPlatform")
* Identity (product code: "identity")

## How to Create Access and Delete Requests

### Prerequisites

To make requests to Access and Delete data for Adobe Federated Audience Composition, you must have:

* an Adobe organization ID
* an Identity identifier of the person you want to act on and the corresponding namespace(s). For more information about identity namespaces Experience Platform, see the [identity namespace overview](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces).

### Required field values in Adobe Adobe Federated Audience Composition for API requests

```json
"companyContexts":
    "namespace": imsOrgID
    "value": <Your Adobe Organization ID Value>

"users":
    "action": either access or delete

    "userIDs":
        "namespace": e.g. email, aaid, ecid, etc.
        "type": standard
        "value": <Data Subject's Identity Identifier>

"include":
    FAC (which is the Adobe product code for Adobe Federated Audience Composition)
    profileService (product code for Profile)
    AdobeCloudPlatform (product code for AEP Data Lake)
    identity (product code for Identity)

"regulation":
    gdpr, ccpa, pdpa, lgpd_bra, or nzpa_nzl (which is the privacy regulation that applies to the request)
```


### GDPR Access Request example:

From the UI:

![](assets/accessrequest.png){width="60%" align="center"}
<!--replace with screenshot specific to FAC if any)-->

Through the API:

```json
// JSON Request
{
   "companyContexts":[
      {
         "namespace":"imsOrgID",
         "value":"745F37C35E4B776E0A49421B@AdobeOrg"
      }
   ],
   "users":[
      {
         "action":[
            "access"
         ],
         "userIDs":[
            {
               "namespace":"ecid",
               "value":"38400000-8cf0-11bd-b23e-10b96e40000d",
               "type":"standard"
            },
            {
               "namespace":"email",
               "value":"johndoe4@gmail.com",
               "type":"standard"
            }
         ]
      }
   ],
   "include":[
      "CJM"
   ],
   "regulation":"gdpr"
}
```

```json
// JSON Response
{
    "requestId": "17163122360480365RX-705",
    "totalRecords": 1,
    "jobs": [
        {
            "jobId": "e709b1f4-1796-11ef-b422-eddd0aebc40d",
            "customer": {
                "user": {
                    "key": "John Doe",
                    "action": [
                        "access"
                    ],
                    "userIDs": [
                        {
                            "namespace": "ecid",
                            "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
                            "type": "standard",
                            "namespaceId": 4,
                            "isDeletedClientSide": false
                        },
                        {
                            "namespace": "email",
                            "value": "johndoe4@gmail.com",
                            "type": "standard",
                            "namespaceId": 6,
                            "isDeletedClientSide": false
                        }
                    ]
                }
            }
        }
    ]
}
```

### GDPR Delete Request example:

From the UI:

![](assets/deleterequest.png){width="60%" align="center"}
<!--replace with screenshot specific to FAC if any)-->

Through the API:

```json
// JSON Request
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "745F37C35E4B776E0A49421B@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
          "delete"
      ],
      "userIDs": [
        {
          "namespace": "ecid",
          "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
          "type": "standard"
        },
                {
          "namespace": "email",
          "value": "johndoe4@gmail.com",
          "type": "standard"
        }
      ]
    }
  ],
  "include": [
    "CJM", "profileService", "AdobeCloudPlatform", "identity"
  ],
  "regulation": "gdpr"
}
```

```json
// JSON Response
{
    "requestId": "17163122360480365RX-705",
    "totalRecords": 1,
    "jobs": [
        {
            "jobId": "e709b1f4-1796-11ef-b422-eddd0aebc40d",
            "customer": {
                "user": {
                    "key": "John Doe",
                    "action": [
                        "delete"
                    ],
                    "userIDs": [
                        {
                            "namespace": "ecid",
                            "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
                            "type": "standard",
                            "namespaceId": 4,
                            "isDeletedClientSide": false
                        },
                        {
                            "namespace": "email",
                            "value": "johndoe4@gmail.com",
                            "type": "standard",
                            "namespaceId": 6,
                            "isDeletedClientSide": false
                        }
                    ]
                }
            }
        }
    ]
}
```
