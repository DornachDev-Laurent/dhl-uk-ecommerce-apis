# DHLUK\AccessTokenApi

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**authV1AccesstokenPost()**](AccessTokenApi.md#authV1AccesstokenPost) | **POST** /auth/v1/accesstoken | Get Token


## `authV1AccesstokenPost()`

```php
authV1AccesstokenPost($clientId, $clientSecret)
```

Get Token

Generate a new token

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\AccessTokenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$clientId = 'clientId_example'; // string
$clientSecret = 'clientSecret_example'; // string

try {
    $apiInstance->authV1AccesstokenPost($clientId, $clientSecret);
} catch (Exception $e) {
    echo 'Exception when calling AccessTokenApi->authV1AccesstokenPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **clientId** | **string**|  | [optional]
 **clientSecret** | **string**|  | [optional]

### Return type

void (empty response body)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
