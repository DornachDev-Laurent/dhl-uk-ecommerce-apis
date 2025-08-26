# DHLUK\ShippingLabelAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**shippingV1AmendmentPost()**](ShippingLabelAPIV1Api.md#shippingV1AmendmentPost) | **POST** /shipping/v1/amendment | Request a shipment amendment and optionally generate labels
[**shippingV1CancellationPost()**](ShippingLabelAPIV1Api.md#shippingV1CancellationPost) | **POST** /shipping/v1/cancellation | Request shipment cancellation
[**shippingV1LabelPost()**](ShippingLabelAPIV1Api.md#shippingV1LabelPost) | **POST** /shipping/v1/label | Create a shipment and optionally a label


## `shippingV1AmendmentPost()`

```php
shippingV1AmendmentPost($shipmentId, $amendRequest, $includeLabel, $format, $pageSize, $labelOrientation, $labelDPI): \DHLUK\Model\PostResponseFormat
```

Request a shipment amendment and optionally generate labels

Conditionally mandatory parameter if you want to include a label. Define label format required ZPL, PDF, PNG, JPG, PNG_RAW or JPG_RAW. PNG or JPG will return a base 64 encoded zip file containing all the label images.PNG_RAW and JPG_RAW will return a base 64 encoded file(Un Zipped format ) in array containing individual label image.Please try to send as many fields in amend request as you can.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ShippingLabelAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$shipmentId = 'shipmentId_example'; // string | shipmentId of the shipment  to be amended
$amendRequest = new \DHLUK\Model\AmendRequest(); // \DHLUK\Model\AmendRequest | Shipment details in defined JSON schema
$includeLabel = false; // bool | Return an amended label?
$format = 'ZPL'; // string | Conditionally mandatory parameter if you want to include a label. Define label format required ZPL, PDF, PNG or JPG.
$pageSize = 'label6x4'; // string | Page size for label returned. Either label6x4 for 6 by 4 inch label (default) or A4 for A6 label in corner of an A4 page. A4 is not available for format ZPL or any Product where labelType is NOT domestic-uk i.e. UK only. Return labels will also only be returned as 6 by 4 inch label.
$labelOrientation = 'portrait'; // string | Label orientation for label returned. Either portrait or landscape
$labelDPI = '203'; // string | DPI(Dots per Inch) for label returned. Either portrait or landscape.

try {
    $result = $apiInstance->shippingV1AmendmentPost($shipmentId, $amendRequest, $includeLabel, $format, $pageSize, $labelOrientation, $labelDPI);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ShippingLabelAPIV1Api->shippingV1AmendmentPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **shipmentId** | **string**| shipmentId of the shipment  to be amended |
 **amendRequest** | [**\DHLUK\Model\AmendRequest**](../Model/AmendRequest.md)| Shipment details in defined JSON schema |
 **includeLabel** | **bool**| Return an amended label? | [optional] [default to false]
 **format** | **string**| Conditionally mandatory parameter if you want to include a label. Define label format required ZPL, PDF, PNG or JPG. | [optional] [default to &#39;ZPL&#39;]
 **pageSize** | **string**| Page size for label returned. Either label6x4 for 6 by 4 inch label (default) or A4 for A6 label in corner of an A4 page. A4 is not available for format ZPL or any Product where labelType is NOT domestic-uk i.e. UK only. Return labels will also only be returned as 6 by 4 inch label. | [optional] [default to &#39;label6x4&#39;]
 **labelOrientation** | **string**| Label orientation for label returned. Either portrait or landscape | [optional] [default to &#39;portrait&#39;]
 **labelDPI** | **string**| DPI(Dots per Inch) for label returned. Either portrait or landscape. | [optional] [default to &#39;203&#39;]

### Return type

[**\DHLUK\Model\PostResponseFormat**](../Model/PostResponseFormat.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `shippingV1CancellationPost()`

```php
shippingV1CancellationPost($requestBody)
```

Request shipment cancellation

Create a cancellation request for a previously created shipments. Shipments that have been handed over to DHL eCommerce UK and scanned cannot be cancelled. If a shipment is cancelled and is then later handed over to DHL eCommerce UK and scanned then it will be automatically recreated.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ShippingLabelAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$requestBody = [{"shipmentId":"JJD49055313895700000010","pickupAccount":"F820579","postalCode":"SL1 4PL","requestingUser":{"id":"test@test.com","name":"tester"}}]; // object[] | Cancellation request details in defined JSON schema

try {
    $apiInstance->shippingV1CancellationPost($requestBody);
} catch (Exception $e) {
    echo 'Exception when calling ShippingLabelAPIV1Api->shippingV1CancellationPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **requestBody** | [**object[]**](../Model/object.md)| Cancellation request details in defined JSON schema |

### Return type

void (empty response body)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `shippingV1LabelPost()`

```php
shippingV1LabelPost($postRequestFormat, $includeLabel, $format, $pageSize, $labelOrientation, $labelDPI): \DHLUK\Model\PostResponseFormat
```

Create a shipment and optionally a label

Create a new DHL eCommerce UK shipment and optionally return label documents in chosen format.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ShippingLabelAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$postRequestFormat = {"pickupAccount":"F020579","dropoffType":"PICKUP","pickup":{"date":"2023-04-28","accountAddress":true},"senderAddress":{"companyName":"A Business","address1":"Unit A1","address2":"A Trading Estate","address3":"Binley","city":"Coventry","state":null,"postalCode":"CV1 1AA","country":"GB","name":"A Despatch Manager","phone":"01215756756","email":"test@email.com"},"shipments":[{"consigneeAddress":{"recipientType":"residential","addressType":"doorstep","companyName":null,"address1":"Dun Roamin Cottage","address2":"12 Long Lane","address3":null,"city":"Chipping Campden","state":"Gloucestershire","postalCode":"GL55 6HU","country":"GB","name":"A Recipient","phone":"078989112233","email":"recipient@email.com","what3words":{"words":"connector.usual.townhouse","geo":{"latitude":-1.776294,"longitude":52.053835}}},"shipmentDetails":{"customerRef1":"Order 1234","customerRef2":"Toys 10GBP","orderedProduct":"210","totalPieces":2,"totalWeight":5,"secureLocation":"Leave in green house at side of house"},"extendedLiability":{"extendedLiabilityUnits":0}}]}; // \DHLUK\Model\PostRequestFormat | Shipment details in defined JSON schema
$includeLabel = 'INCLUDE'; // string | Allows: a) INCLUDE (default). Returns base64 encoded label data in chosen format in response message. b) DEFERRED (no label returned). Label will be created for later retrieval via  Label API. c) DROPOFF - return a shipment drop off barcode ready to be placed in an email for a servicepoint drop off.
$format = 'ZPL'; // string | Conditionally mandatory parameter if you want to include a label. Define label format required ZPL, PDF, PNG, JPG, PNG_RAW or JPG_RAW. PNG or JPG will return a base 64 encoded zip file containing all the label images.PNG_RAW and JPG_RAW will return a base 64 encoded file(Un Zipped format) in array containing individual label image.
$pageSize = 'label6x4'; // string | Page size for label returned. Either label6x4 for 6 by 4 inch label (default) or A4 for A6 label in corner of an A4 page. A4 is not available for format ZPL or any Product where labelType is NOT domestic-uk i.e. UK only. Return labels will also only be returned as 6 by 4 inch label.
$labelOrientation = 'portrait'; // string | Label orientation for label returned. Either portrait or landscape
$labelDPI = '203'; // string | DPI(Dots per Inch) for label returned.

try {
    $result = $apiInstance->shippingV1LabelPost($postRequestFormat, $includeLabel, $format, $pageSize, $labelOrientation, $labelDPI);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ShippingLabelAPIV1Api->shippingV1LabelPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **postRequestFormat** | [**\DHLUK\Model\PostRequestFormat**](../Model/PostRequestFormat.md)| Shipment details in defined JSON schema |
 **includeLabel** | **string**| Allows: a) INCLUDE (default). Returns base64 encoded label data in chosen format in response message. b) DEFERRED (no label returned). Label will be created for later retrieval via  Label API. c) DROPOFF - return a shipment drop off barcode ready to be placed in an email for a servicepoint drop off. | [optional] [default to &#39;INCLUDE&#39;]
 **format** | **string**| Conditionally mandatory parameter if you want to include a label. Define label format required ZPL, PDF, PNG, JPG, PNG_RAW or JPG_RAW. PNG or JPG will return a base 64 encoded zip file containing all the label images.PNG_RAW and JPG_RAW will return a base 64 encoded file(Un Zipped format) in array containing individual label image. | [optional] [default to &#39;ZPL&#39;]
 **pageSize** | **string**| Page size for label returned. Either label6x4 for 6 by 4 inch label (default) or A4 for A6 label in corner of an A4 page. A4 is not available for format ZPL or any Product where labelType is NOT domestic-uk i.e. UK only. Return labels will also only be returned as 6 by 4 inch label. | [optional] [default to &#39;label6x4&#39;]
 **labelOrientation** | **string**| Label orientation for label returned. Either portrait or landscape | [optional] [default to &#39;portrait&#39;]
 **labelDPI** | **string**| DPI(Dots per Inch) for label returned. | [optional] [default to &#39;203&#39;]

### Return type

[**\DHLUK\Model\PostResponseFormat**](../Model/PostResponseFormat.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
