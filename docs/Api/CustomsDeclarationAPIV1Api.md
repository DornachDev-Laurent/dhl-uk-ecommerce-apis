# DHLUK\CustomsDeclarationAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**customsdeclarationV1DocumentsGet()**](CustomsDeclarationAPIV1Api.md#customsdeclarationV1DocumentsGet) | **GET** /customsdeclaration/v1/documents | Get customs documents for a previously created shipment.


## `customsdeclarationV1DocumentsGet()`

```php
customsdeclarationV1DocumentsGet($shipmentId, $ignoreInvoice)
```

Get customs documents for a previously created shipment.

Returns the customs documentation including invoice, for a shipment. This may return a Commercial or Proforma invoice depending on which type is requested for.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\CustomsDeclarationAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$shipmentId = 'shipmentId_example'; // string | The shipmentId to get customs documents for.
$ignoreInvoice = false; // bool | Flag to indicate if Invoice is to be ignored in the document generation

try {
    $apiInstance->customsdeclarationV1DocumentsGet($shipmentId, $ignoreInvoice);
} catch (Exception $e) {
    echo 'Exception when calling CustomsDeclarationAPIV1Api->customsdeclarationV1DocumentsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **shipmentId** | **string**| The shipmentId to get customs documents for. |
 **ignoreInvoice** | **bool**| Flag to indicate if Invoice is to be ignored in the document generation | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/pdf`, `application/xml`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
