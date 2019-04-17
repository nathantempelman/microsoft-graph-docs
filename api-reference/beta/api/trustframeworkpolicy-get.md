---
title: "Get trustFrameworkPolicy Content"
description: "This operation retrieves the content of an existing trustFrameworkPolicy object from an Azure AD B2C tenant."
localization_priority: Normal
author: "valnav"
ms.prod: "microsoft-identity-platform"
---
# Get trustFrameworkPolicy Content

>**Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

Retrieve the contents of an existing [trustFrameworkPolicy](../resources/trustframeworkpolicy.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference.md).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account)|Policy.Read.TrustFramework, Policy.Read.All|
|Delegated (personal Microsoft account)| Not supported.|
|Application|Not supported.|

The work or school account must be a global administrator of the tenant.

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
GET /trustFramework/policies/{id}/$value
```

## Optional query parameters

This method supports the $select, and $expand [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers

|Name|Description|
|:---------------|:----------|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns `200 OK` response code and an XML representation of the [trustFrameworkPolicy](../resources/trustFrameworkpolicy.md) in the response body.  **Note:** the response content type will be `application/xml`.

## Example

The following example retrieves a specific **trustFrameworkPolicy**.

##### Request

<!-- {
  "blockType": "request",
  "name": "get_trustFramework"
}-->
```http
https://graph.microsoft.com/beta/trustFramework/policies/B2C_1A_Test/$value
```

##### Response

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.trustFramework.policy"
} -->
```http
HTTP/1.1 200 OK
Content-Type application/xml
<TrustFrameworkPolicy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/online/cpim/schemas/2013/06" PolicySchemaVersion="0.3.0.0" TenantId="tenantName.onmicrosoft.com" PolicyId="B2C_1A_Test" PublicPolicyUri="http://tenantName.onmicrosoft.com/B2C_1A_Test">
	.....
	....
	<!---PolicyContent-->
	....
	....
</TrustFrameworkPolicy>
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get trustFramework policy",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->