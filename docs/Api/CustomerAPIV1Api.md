# DHLUK\CustomerAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**customerV1TradingLocationsGet()**](CustomerAPIV1Api.md#customerV1TradingLocationsGet) | **GET** /customer/v1/tradingLocations | Get customer trading locations


## `customerV1TradingLocationsGet()`

```php
customerV1TradingLocationsGet($customerAccountNumber, $accountId, $tradingLocationId): \DHLUK\Model\TradingLocationsResponse
```

Get customer trading locations

Get list of trading locations associated with a customer

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\CustomerAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customerAccountNumber = CUS-049204; // string | customerAccountNumber for customer trading locations.
$accountId = F020579; // string | Unique Id for operational account
$tradingLocationId = 'tradingLocationId_example'; // string | Unique ID for customer trading location

try {
    $result = $apiInstance->customerV1TradingLocationsGet($customerAccountNumber, $accountId, $tradingLocationId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomerAPIV1Api->customerV1TradingLocationsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **customerAccountNumber** | **string**| customerAccountNumber for customer trading locations. |
 **accountId** | **string**| Unique Id for operational account | [optional]
 **tradingLocationId** | **string**| Unique ID for customer trading location | [optional]

### Return type

[**\DHLUK\Model\TradingLocationsResponse**](../Model/TradingLocationsResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
