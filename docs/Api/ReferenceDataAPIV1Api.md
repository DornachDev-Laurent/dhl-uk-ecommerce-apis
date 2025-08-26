# DHLUK\ReferenceDataAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**countriesGetcountries()**](ReferenceDataAPIV1Api.md#countriesGetcountries) | **GET** /referencedata/v1/countries | Get all countries
[**countriesGetcountry()**](ReferenceDataAPIV1Api.md#countriesGetcountry) | **GET** /referencedata/v1/country | Get country by either country code or name
[**currenciesGetcurrencies()**](ReferenceDataAPIV1Api.md#currenciesGetcurrencies) | **GET** /referencedata/v1/currencies | Get all currencies
[**currenciesGetcurrency()**](ReferenceDataAPIV1Api.md#currenciesGetcurrency) | **GET** /referencedata/v1/currency | Get currency by either currency code or name
[**getEventStatusDetails()**](ReferenceDataAPIV1Api.md#getEventStatusDetails) | **GET** /referencedata/v1/eventstatuses | Provides a reference list of all shipment status messages that can be returned in the shipment tracking API
[**getReferencedataProducts()**](ReferenceDataAPIV1Api.md#getReferencedataProducts) | **GET** /referencedata/v2/products | Get all products
[**getUsstates()**](ReferenceDataAPIV1Api.md#getUsstates) | **GET** /referencedata/v1/usstates | Get all USState
[**postcodedistrictGetpostcode()**](ReferenceDataAPIV1Api.md#postcodedistrictGetpostcode) | **GET** /referencedata/v1/ukpostcodedistrict | Get UK Postcode District by postcode
[**postcodedistrictGetpostcodedistricts()**](ReferenceDataAPIV1Api.md#postcodedistrictGetpostcodedistricts) | **GET** /referencedata/v1/ukpostcodedistricts | Get all UK Postcode Districts
[**publicHolidayGetpublicHolidays()**](ReferenceDataAPIV1Api.md#publicHolidayGetpublicHolidays) | **GET** /referencedata/v1/publicholiday | Get Public Holiday data.
[**referencedataV1ProductcountryfeatureGet()**](ReferenceDataAPIV1Api.md#referencedataV1ProductcountryfeatureGet) | **GET** /referencedata/v1/productcountryfeature | Get ProductCountryFeature
[**referencedataV1ServicesGet()**](ReferenceDataAPIV1Api.md#referencedataV1ServicesGet) | **GET** /referencedata/v1/services | Get all services


## `countriesGetcountries()`

```php
countriesGetcountries(): \DHLUK\Model\CountryResponse
```

Get all countries

Get country data such as abbreviation codes, post code details, etc

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->countriesGetcountries();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->countriesGetcountries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\DHLUK\Model\CountryResponse**](../Model/CountryResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `countriesGetcountry()`

```php
countriesGetcountry($code, $name): \DHLUK\Model\Country
```

Get country by either country code or name

Get country by either country code or name parameter, you must send one of the parameters in your request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$code = 'USA'; // string | ISO 2 character or 3 character country code
$name = 'name_example'; // string | country name

try {
    $result = $apiInstance->countriesGetcountry($code, $name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->countriesGetcountry: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **string**| ISO 2 character or 3 character country code | [optional] [default to &#39;USA&#39;]
 **name** | **string**| country name | [optional]

### Return type

[**\DHLUK\Model\Country**](../Model/Country.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `currenciesGetcurrencies()`

```php
currenciesGetcurrencies(): \DHLUK\Model\CurrencyResponse
```

Get all currencies

Get currency data such as code, name and symbol.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->currenciesGetcurrencies();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->currenciesGetcurrencies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\DHLUK\Model\CurrencyResponse**](../Model/CurrencyResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `currenciesGetcurrency()`

```php
currenciesGetcurrency($code, $name): \DHLUK\Model\Currency
```

Get currency by either currency code or name

Get currency by either currency code or name parameter, you must send one of the parameters in your request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$code = 'USD'; // string | Optional parameter to filter by the ISO currency code
$name = 'name_example'; // string | Optional parameter to filter by the currency name

try {
    $result = $apiInstance->currenciesGetcurrency($code, $name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->currenciesGetcurrency: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **string**| Optional parameter to filter by the ISO currency code | [optional] [default to &#39;USD&#39;]
 **name** | **string**| Optional parameter to filter by the currency name | [optional]

### Return type

[**\DHLUK\Model\Currency**](../Model/Currency.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getEventStatusDetails()`

```php
getEventStatusDetails(): \DHLUK\Model\EventStatus[]
```

Provides a reference list of all shipment status messages that can be returned in the shipment tracking API

List all shipment status messages

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getEventStatusDetails();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->getEventStatusDetails: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\DHLUK\Model\EventStatus[]**](../Model/EventStatus.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/vnd.api+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReferencedataProducts()`

```php
getReferencedataProducts($code, $name, $shipmentType): \DHLUK\Model\ParcelsProductReferenceData
```

Get all products

Get all products

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$code = 'code_example'; // string | Optional product code to filter products by
$name = 'name_example'; // string | Optional product name to filter products by
$shipmentType = 'shipmentType_example'; // string | Shipment type to filter products by

try {
    $result = $apiInstance->getReferencedataProducts($code, $name, $shipmentType);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->getReferencedataProducts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **string**| Optional product code to filter products by | [optional]
 **name** | **string**| Optional product name to filter products by | [optional]
 **shipmentType** | **string**| Shipment type to filter products by | [optional]

### Return type

[**\DHLUK\Model\ParcelsProductReferenceData**](../Model/ParcelsProductReferenceData.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsstates()`

```php
getUsstates($code, $name): \DHLUK\Model\USStateReferenceData
```

Get all USState

All USState

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$code = 'code_example'; // string | Optional countryCode to filter USState by
$name = 'name_example'; // string | Optional productCode to filter USState by

try {
    $result = $apiInstance->getUsstates($code, $name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->getUsstates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **string**| Optional countryCode to filter USState by | [optional]
 **name** | **string**| Optional productCode to filter USState by | [optional]

### Return type

[**\DHLUK\Model\USStateReferenceData**](../Model/USStateReferenceData.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postcodedistrictGetpostcode()`

```php
postcodedistrictGetpostcode($postcode): \DHLUK\Model\UkPostcodeDistrict
```

Get UK Postcode District by postcode

Get one UK Postcode District by postcode

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$postcode = 'postcode_example'; // string | Mandatory query parameter postcode for which you want postcode disctrict data

try {
    $result = $apiInstance->postcodedistrictGetpostcode($postcode);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->postcodedistrictGetpostcode: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **postcode** | **string**| Mandatory query parameter postcode for which you want postcode disctrict data | [optional]

### Return type

[**\DHLUK\Model\UkPostcodeDistrict**](../Model/UkPostcodeDistrict.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postcodedistrictGetpostcodedistricts()`

```php
postcodedistrictGetpostcodedistricts(): \DHLUK\Model\UkPostcodeDistrictResponse
```

Get all UK Postcode Districts

Get all UK Postcode Districts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->postcodedistrictGetpostcodedistricts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->postcodedistrictGetpostcodedistricts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\DHLUK\Model\UkPostcodeDistrictResponse**](../Model/UkPostcodeDistrictResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publicHolidayGetpublicHolidays()`

```php
publicHolidayGetpublicHolidays($countryCode, $date, $region): \DHLUK\Model\PublicHolidayResponse
```

Get Public Holiday data.

Public holidays filtered by parameters countryCode and optionally date and region

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'GB'; // string | Mandatory query paramater. Currently only supports value GB
$date = 'date_example'; // string | Optional parameter to filter by date - YYYY-MM-DD
$region = 'region_example'; // string | Optional parameter to filter by region. Best used in combination with a country code. Uk examples: england-and-wales, scotland and northern-ireland.

try {
    $result = $apiInstance->publicHolidayGetpublicHolidays($countryCode, $date, $region);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->publicHolidayGetpublicHolidays: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **countryCode** | **string**| Mandatory query paramater. Currently only supports value GB | [optional] [default to &#39;GB&#39;]
 **date** | **string**| Optional parameter to filter by date - YYYY-MM-DD | [optional]
 **region** | **string**| Optional parameter to filter by region. Best used in combination with a country code. Uk examples: england-and-wales, scotland and northern-ireland. | [optional]

### Return type

[**\DHLUK\Model\PublicHolidayResponse**](../Model/PublicHolidayResponse.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `referencedataV1ProductcountryfeatureGet()`

```php
referencedataV1ProductcountryfeatureGet($countryCode, $productCode, $recipientType, $addressType, $locationType): \DHLUK\Model\ProductCountryFeatureData
```

Get ProductCountryFeature

Get ProductCountryFeature reference data, either all or optionally filtered.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$countryCode = 'countryCode_example'; // string | Optional countryCode to filter ProductCountryFeature by
$productCode = 'productCode_example'; // string | Optional productCode to filter ProductCountryFeature by
$recipientType = 'recipientType_example'; // string | Optional recipientType to filter ProductCountryFeature by
$addressType = 'addressType_example'; // string | Optional addressType to filter ProductCountryFeature by
$locationType = 'locationType_example'; // string | Optional service point locationType to filter ProductCountryFeature by

try {
    $result = $apiInstance->referencedataV1ProductcountryfeatureGet($countryCode, $productCode, $recipientType, $addressType, $locationType);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->referencedataV1ProductcountryfeatureGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **countryCode** | **string**| Optional countryCode to filter ProductCountryFeature by | [optional]
 **productCode** | **string**| Optional productCode to filter ProductCountryFeature by | [optional]
 **recipientType** | **string**| Optional recipientType to filter ProductCountryFeature by | [optional]
 **addressType** | **string**| Optional addressType to filter ProductCountryFeature by | [optional]
 **locationType** | **string**| Optional service point locationType to filter ProductCountryFeature by | [optional]

### Return type

[**\DHLUK\Model\ProductCountryFeatureData**](../Model/ProductCountryFeatureData.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `referencedataV1ServicesGet()`

```php
referencedataV1ServicesGet($code, $productCode): \DHLUK\Model\ParcelsServiceReferenceData
```

Get all services

Get services optionally filtered by either service code or product code

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ReferenceDataAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$code = 'code_example'; // string | Optional service code to filter services by
$productCode = 'productCode_example'; // string | Optional product code to filter services by

try {
    $result = $apiInstance->referencedataV1ServicesGet($code, $productCode);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReferenceDataAPIV1Api->referencedataV1ServicesGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **string**| Optional service code to filter services by | [optional]
 **productCode** | **string**| Optional product code to filter services by | [optional]

### Return type

[**\DHLUK\Model\ParcelsServiceReferenceData**](../Model/ParcelsServiceReferenceData.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
