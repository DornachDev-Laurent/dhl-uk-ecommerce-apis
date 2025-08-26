# DHLUK\ServicepointsApi

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**servicepointV1FindByAddressGet()**](ServicepointsApi.md#servicepointV1FindByAddressGet) | **GET** /servicepoint/v1/find-by-address | Find nearest DHL Service Point locations to an address
[**servicepointV1FindByGeoGet()**](ServicepointsApi.md#servicepointV1FindByGeoGet) | **GET** /servicepoint/v1/find-by-geo | Search for DHL Service Point locations by geo coordinates
[**servicepointV1ServicepointsIdGet()**](ServicepointsApi.md#servicepointV1ServicepointsIdGet) | **GET** /servicepoint/v1/servicepoints/{id} | Retrieve one DHL Service Point location by its ID


## `servicepointV1FindByAddressGet()`

```php
servicepointV1FindByAddressGet($country, $postalCode, $address1, $city, $locationTypes, $serviceType, $radius, $limit): \DHLUK\Model\ServicePoint[]
```

Find nearest DHL Service Point locations to an address

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ServicepointsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$country = 'country_example'; // string | Two character ISO country code of address.
$postalCode = 'postalCode_example'; // string | Postal code of address. Either postalCode, address1 or city must be supplied.
$address1 = 'address1_example'; // string | Address line 1 of address. Either postalCode, address1 or city must be supplied.
$city = 'city_example'; // string | Name of town or city of address. Either postalCode, address1 or city must be supplied.
$locationTypes = array('locationTypes_example'); // string[] | A list of requested Servicepoint location types for the parcel size, weight and country. This will have previously been returned by the Product Capabilities API as deliveryCapabilities -> servicePointLocationTypes.
$serviceType = 'serviceType_example'; // string | Each location can offer more than one service. This parameter can be added multiple times in each API request. The response will include only locations with at least all of the serviceTypes requested.
$radius = 500; // float | Specifies the radius in metres around the provided location, to search within. Maximum radius: 25 000 metres. Default radius: 500 metres.
$limit = 15; // float | Number specifying the maximum amount of locations included in the results. Maximum limit: 50 locations. Default limit: 15 locations.

try {
    $result = $apiInstance->servicepointV1FindByAddressGet($country, $postalCode, $address1, $city, $locationTypes, $serviceType, $radius, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ServicepointsApi->servicepointV1FindByAddressGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **country** | **string**| Two character ISO country code of address. |
 **postalCode** | **string**| Postal code of address. Either postalCode, address1 or city must be supplied. | [optional]
 **address1** | **string**| Address line 1 of address. Either postalCode, address1 or city must be supplied. | [optional]
 **city** | **string**| Name of town or city of address. Either postalCode, address1 or city must be supplied. | [optional]
 **locationTypes** | [**string[]**](../Model/string.md)| A list of requested Servicepoint location types for the parcel size, weight and country. This will have previously been returned by the Product Capabilities API as deliveryCapabilities -&gt; servicePointLocationTypes. | [optional]
 **serviceType** | **string**| Each location can offer more than one service. This parameter can be added multiple times in each API request. The response will include only locations with at least all of the serviceTypes requested. | [optional]
 **radius** | **float**| Specifies the radius in metres around the provided location, to search within. Maximum radius: 25 000 metres. Default radius: 500 metres. | [optional] [default to 500]
 **limit** | **float**| Number specifying the maximum amount of locations included in the results. Maximum limit: 50 locations. Default limit: 15 locations. | [optional] [default to 15]

### Return type

[**\DHLUK\Model\ServicePoint[]**](../Model/ServicePoint.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `servicepointV1FindByGeoGet()`

```php
servicepointV1FindByGeoGet($latitude, $longitude, $locationTypes, $serviceType, $radius, $limit): \DHLUK\Model\ServicePoint[]
```

Search for DHL Service Point locations by geo coordinates

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ServicepointsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$latitude = 3.4; // float | Latitude (only accepts values between -90 to 90 )
$longitude = 3.4; // float | Longitude (only accepts values between -180 to 180)
$locationTypes = array('locationTypes_example'); // string[] | A list of requested Servicepoint location types for the parcel size, weight and country. This will have previously been returned by the Product Capabilities API as deliveryCapabilities -> servicePointLocationTypes.
$serviceType = 'serviceType_example'; // string | Each location can offer more than one service. This parameter can be added multiple times in each API request. The response will include only locations with at least all of the serviceTypes requested.
$radius = 25000; // float | Specifies the radius in metres around the provided location, to search within. Maximum radius: 25 000 metres. Default radius: 500 metres.
$limit = 15; // float | Number specifying the maximum amount of locations included in the results. Maximum limit: 50 locations. Default limit: 15 locations.

try {
    $result = $apiInstance->servicepointV1FindByGeoGet($latitude, $longitude, $locationTypes, $serviceType, $radius, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ServicepointsApi->servicepointV1FindByGeoGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **latitude** | **float**| Latitude (only accepts values between -90 to 90 ) |
 **longitude** | **float**| Longitude (only accepts values between -180 to 180) |
 **locationTypes** | [**string[]**](../Model/string.md)| A list of requested Servicepoint location types for the parcel size, weight and country. This will have previously been returned by the Product Capabilities API as deliveryCapabilities -&gt; servicePointLocationTypes. | [optional]
 **serviceType** | **string**| Each location can offer more than one service. This parameter can be added multiple times in each API request. The response will include only locations with at least all of the serviceTypes requested. | [optional]
 **radius** | **float**| Specifies the radius in metres around the provided location, to search within. Maximum radius: 25 000 metres. Default radius: 500 metres. | [optional] [default to 25000]
 **limit** | **float**| Number specifying the maximum amount of locations included in the results. Maximum limit: 50 locations. Default limit: 15 locations. | [optional] [default to 15]

### Return type

[**\DHLUK\Model\ServicePoint[]**](../Model/ServicePoint.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `servicepointV1ServicepointsIdGet()`

```php
servicepointV1ServicepointsIdGet($id): \DHLUK\Model\ServicePoint
```

Retrieve one DHL Service Point location by its ID

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ServicepointsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | ID of the DHL Service Point location.

try {
    $result = $apiInstance->servicepointV1ServicepointsIdGet($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ServicepointsApi->servicepointV1ServicepointsIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| ID of the DHL Service Point location. |

### Return type

[**\DHLUK\Model\ServicePoint**](../Model/ServicePoint.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
