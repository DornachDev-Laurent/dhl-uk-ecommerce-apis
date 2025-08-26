# DHLUK\TrackingAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getImage()**](TrackingAPIV1Api.md#getImage) | **GET** /tracking/v1/images/{imageId} | Retrieve a specific digital asset (signature scan, photo or other image)
[**getShipmentsPiece()**](TrackingAPIV1Api.md#getShipmentsPiece) | **GET** /tracking/v1/pieces | Track a piece in a shipment
[**getShipmentsTrackingnumberTrackingnumber()**](TrackingAPIV1Api.md#getShipmentsTrackingnumberTrackingnumber) | **GET** /tracking/v1/shipments | Track a shipment


## `getImage()`

```php
getImage($imageId): object
```

Retrieve a specific digital asset (signature scan, photo or other image)

Retrieve an image

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\TrackingAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$imageId = photo__jobAttempt_a1bc2de3-4612-4721-88ae-e0bcdd95085c_1.jpeg; // string | Image identifier as provided in the Tracking API V1 Track as Shipment, in Proof of Delivery section

try {
    $result = $apiInstance->getImage($imageId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TrackingAPIV1Api->getImage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **imageId** | **string**| Image identifier as provided in the Tracking API V1 Track as Shipment, in Proof of Delivery section |

### Return type

**object**

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `image/jpeg`, `image/gif`, `image/png`, `image/tiff`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getShipmentsPiece()`

```php
getShipmentsPiece($trackingNumber, $pieceNumber, $service, $requesterCountryCode, $originCountryCode, $recipientPostalCode, $language): \DHLUK\Model\LocalmodelPieceEvents
```

Track a piece in a shipment

Retrieves the tracking information for a parcel (piece) within a shipments. The pieces are identified using the required `pieceNumber` query parameter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\TrackingAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$trackingNumber = 'BA160855092DE'; // string | The tracking number of the shipment for which to return the information.
$pieceNumber = 'BA160855092DE001'; // string | The piece number of the parcel within a shipment for which to return the information.
$service = 'service_example'; // string | Hint which service (provider) should be used to resolve the tracking number.
$requesterCountryCode = 'requesterCountryCode_example'; // string | Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code represents country of the consumer of the API response. It optimizes the return of the API response.
$originCountryCode = 'originCountryCode_example'; // string | Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the shipment origin to further qualify the shipment tracking number (`trackingNumber`) parameter of the request. This parameter is necessary to search for the shipment in dsc service.
$recipientPostalCode = 'recipientPostalCode_example'; // string | Postal code of the destination address to * further qualify the shipment piece number (pieceNumber) parameter of the request or * parcel-nl and parcel-de services to display full set of data in the response.
$language = 'en'; // string | ISO 639-1 2-character language code for the response. This parameter serves as an indication of the client preferences ONLY. Language availability depends on the service used. The actual response language is indicated by the Content-Language header.

try {
    $result = $apiInstance->getShipmentsPiece($trackingNumber, $pieceNumber, $service, $requesterCountryCode, $originCountryCode, $recipientPostalCode, $language);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TrackingAPIV1Api->getShipmentsPiece: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **trackingNumber** | **string**| The tracking number of the shipment for which to return the information. | [default to &#39;BA160855092DE&#39;]
 **pieceNumber** | **string**| The piece number of the parcel within a shipment for which to return the information. | [default to &#39;BA160855092DE001&#39;]
 **service** | **string**| Hint which service (provider) should be used to resolve the tracking number. | [optional]
 **requesterCountryCode** | **string**| Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code represents country of the consumer of the API response. It optimizes the return of the API response. | [optional]
 **originCountryCode** | **string**| Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the shipment origin to further qualify the shipment tracking number (&#x60;trackingNumber&#x60;) parameter of the request. This parameter is necessary to search for the shipment in dsc service. | [optional]
 **recipientPostalCode** | **string**| Postal code of the destination address to * further qualify the shipment piece number (pieceNumber) parameter of the request or * parcel-nl and parcel-de services to display full set of data in the response. | [optional]
 **language** | **string**| ISO 639-1 2-character language code for the response. This parameter serves as an indication of the client preferences ONLY. Language availability depends on the service used. The actual response language is indicated by the Content-Language header. | [optional] [default to &#39;en&#39;]

### Return type

[**\DHLUK\Model\LocalmodelPieceEvents**](../Model/LocalmodelPieceEvents.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getShipmentsTrackingnumberTrackingnumber()`

```php
getShipmentsTrackingnumberTrackingnumber($trackingNumber, $service, $requesterCountryCode, $originCountryCode, $recipientPostalCode, $language, $offset, $limit): \DHLUK\Model\SupermodelIoLogisticsTrackingShipments
```

Track a shipment

Retrieves the tracking information for shipments(s). The shipments are identified using the required `trackingNumber` query parameter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\TrackingAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$trackingNumber = 'BA160855092DE'; // string | The tracking number of the shipment for which to return the information.
$service = 'service_example'; // string | Hint which service (provider) should be used to resolve the tracking number.
$requesterCountryCode = 'requesterCountryCode_example'; // string | Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code represents country of the consumer of the API response. It optimizes the return of the API response.
$originCountryCode = 'originCountryCode_example'; // string | Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the shipment origin to further qualify the shipment tracking number (`trackingNumber`) parameter of the request. This parameter is necessary to search for the shipment in dsc service.
$recipientPostalCode = 'recipientPostalCode_example'; // string | Postal code of the destination address to * further qualify the shipment tracking number (trackingNumber) parameter of the request or * parcel-nl and parcel-de services to display full set of data in the response.
$language = 'en'; // string | ISO 639-1 2-character language code for the response. This parameter serves as an indication of the client preferences ONLY. Language availability depends on the service used. The actual response language is indicated by the Content-Language header.
$offset = 0; // float | Pagination parameter. Offset from the start of the result set at which to retrieve the remainder of the results (if any).
$limit = 5; // float | Pagination parameter. Maximal number of results to retireve.

try {
    $result = $apiInstance->getShipmentsTrackingnumberTrackingnumber($trackingNumber, $service, $requesterCountryCode, $originCountryCode, $recipientPostalCode, $language, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TrackingAPIV1Api->getShipmentsTrackingnumberTrackingnumber: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **trackingNumber** | **string**| The tracking number of the shipment for which to return the information. | [default to &#39;BA160855092DE&#39;]
 **service** | **string**| Hint which service (provider) should be used to resolve the tracking number. | [optional]
 **requesterCountryCode** | **string**| Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code represents country of the consumer of the API response. It optimizes the return of the API response. | [optional]
 **originCountryCode** | **string**| Optional [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the shipment origin to further qualify the shipment tracking number (&#x60;trackingNumber&#x60;) parameter of the request. This parameter is necessary to search for the shipment in dsc service. | [optional]
 **recipientPostalCode** | **string**| Postal code of the destination address to * further qualify the shipment tracking number (trackingNumber) parameter of the request or * parcel-nl and parcel-de services to display full set of data in the response. | [optional]
 **language** | **string**| ISO 639-1 2-character language code for the response. This parameter serves as an indication of the client preferences ONLY. Language availability depends on the service used. The actual response language is indicated by the Content-Language header. | [optional] [default to &#39;en&#39;]
 **offset** | **float**| Pagination parameter. Offset from the start of the result set at which to retrieve the remainder of the results (if any). | [optional] [default to 0]
 **limit** | **float**| Pagination parameter. Maximal number of results to retireve. | [optional] [default to 5]

### Return type

[**\DHLUK\Model\SupermodelIoLogisticsTrackingShipments**](../Model/SupermodelIoLogisticsTrackingShipments.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
