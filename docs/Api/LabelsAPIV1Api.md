# DHLUK\LabelsAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**reprintlabelsV1LabelsGet()**](LabelsAPIV1Api.md#reprintlabelsV1LabelsGet) | **GET** /reprintlabels/v1/labels | Regenerate a label
[**reprintlabelsV1ServicepointDropoffUkGet()**](LabelsAPIV1Api.md#reprintlabelsV1ServicepointDropoffUkGet) | **GET** /reprintlabels/v1/servicepoint-dropoff-uk | Regenerate a servicepoint drop off label/barcode


## `reprintlabelsV1LabelsGet()`

```php
reprintlabelsV1LabelsGet($shipmentId, $format, $pageSize, $labelOrientation, $labelDPI): \DHLUK\Model\LabelResponse
```

Regenerate a label

Regenerate a shipment label in a number of formats

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\LabelsAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$shipmentId = 'shipmentId_example'; // string
$format = 'format_example'; // string
$pageSize = 'label6x4'; // string
$labelOrientation = 'portrait'; // string | Label orientation for label returned. Either portrait or landscape
$labelDPI = '203'; // string | DPI(Dots per Inch) for label returned.

try {
    $result = $apiInstance->reprintlabelsV1LabelsGet($shipmentId, $format, $pageSize, $labelOrientation, $labelDPI);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LabelsAPIV1Api->reprintlabelsV1LabelsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **shipmentId** | **string**|  |
 **format** | **string**|  |
 **pageSize** | **string**|  | [optional] [default to &#39;label6x4&#39;]
 **labelOrientation** | **string**| Label orientation for label returned. Either portrait or landscape | [optional] [default to &#39;portrait&#39;]
 **labelDPI** | **string**| DPI(Dots per Inch) for label returned. | [optional] [default to &#39;203&#39;]

### Return type

[**\DHLUK\Model\LabelResponse**](../Model/LabelResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `reprintlabelsV1ServicepointDropoffUkGet()`

```php
reprintlabelsV1ServicepointDropoffUkGet($shipmentId, $format, $labelOrientation, $labelDPI): \DHLUK\Model\LabelResponse
```

Regenerate a servicepoint drop off label/barcode

Regenerate a servicepoint drop off label/barcode in a number of formats

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\LabelsAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$shipmentId = 'shipmentId_example'; // string
$format = 'format_example'; // string
$labelOrientation = 'portrait'; // string | Label orientation for label returned. Either portrait or landscape
$labelDPI = '203'; // string | DPI(Dots per Inch) for label returned.

try {
    $result = $apiInstance->reprintlabelsV1ServicepointDropoffUkGet($shipmentId, $format, $labelOrientation, $labelDPI);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LabelsAPIV1Api->reprintlabelsV1ServicepointDropoffUkGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **shipmentId** | **string**|  |
 **format** | **string**|  |
 **labelOrientation** | **string**| Label orientation for label returned. Either portrait or landscape | [optional] [default to &#39;portrait&#39;]
 **labelDPI** | **string**| DPI(Dots per Inch) for label returned. | [optional] [default to &#39;203&#39;]

### Return type

[**\DHLUK\Model\LabelResponse**](../Model/LabelResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
