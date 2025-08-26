# DHLUK\PickupAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**pickupV1PickupGet()**](PickupAPIV1Api.md#pickupV1PickupGet) | **GET** /pickup/v1/pickup | Get pickup by identifier
[**pickupV1PickupPost()**](PickupAPIV1Api.md#pickupV1PickupPost) | **POST** /pickup/v1/pickup | Create a pickup
[**pickupV1PickupsGet()**](PickupAPIV1Api.md#pickupV1PickupsGet) | **GET** /pickup/v1/pickups | Get pickups


## `pickupV1PickupGet()`

```php
pickupV1PickupGet($pickupIdentifier): \DHLUK\Model\Pickup
```

Get pickup by identifier

Get pickup by pickupIdentifier or collectionJobNumber

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\PickupAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$pickupIdentifier = 'pickupIdentifier_example'; // string | pickupIdentifier for a specific driver pick up

try {
    $result = $apiInstance->pickupV1PickupGet($pickupIdentifier);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PickupAPIV1Api->pickupV1PickupGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pickupIdentifier** | **string**| pickupIdentifier for a specific driver pick up | [optional]

### Return type

[**\DHLUK\Model\Pickup**](../Model/Pickup.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pickupV1PickupPost()`

```php
pickupV1PickupPost($pickupRequest): \DHLUK\Model\PickupAccepted
```

Create a pickup

Create a pickup from a customer

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\PickupAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$pickupRequest = new \DHLUK\Model\PickupRequest(); // \DHLUK\Model\PickupRequest | Pickup request details

try {
    $result = $apiInstance->pickupV1PickupPost($pickupRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PickupAPIV1Api->pickupV1PickupPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pickupRequest** | [**\DHLUK\Model\PickupRequest**](../Model/PickupRequest.md)| Pickup request details |

### Return type

[**\DHLUK\Model\PickupAccepted**](../Model/PickupAccepted.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pickupV1PickupsGet()`

```php
pickupV1PickupsGet($customerAccountNumber, $tradingLocationId, $startDate, $endDate): object[]
```

Get pickups

Get pickups

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\PickupAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customerAccountNumber = CUS-049204; // string | customerAccountNumber for pickup requests.
$tradingLocationId = B0V4K000002JMSDUA2; // string | tradingLocationId for pickup requests
$startDate = 2022-03-01; // string | Start date
$endDate = 2023-03-06; // string | Start date

try {
    $result = $apiInstance->pickupV1PickupsGet($customerAccountNumber, $tradingLocationId, $startDate, $endDate);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PickupAPIV1Api->pickupV1PickupsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **customerAccountNumber** | **string**| customerAccountNumber for pickup requests. |
 **tradingLocationId** | **string**| tradingLocationId for pickup requests |
 **startDate** | **string**| Start date |
 **endDate** | **string**| Start date |

### Return type

**object[]**

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
