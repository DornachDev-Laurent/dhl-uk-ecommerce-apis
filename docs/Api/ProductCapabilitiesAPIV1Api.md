# DHLUK\ProductCapabilitiesAPIV1Api

All URIs are relative to https://api-uat.dhl.com/parceluk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**productcapabilitiesGetproducts()**](ProductCapabilitiesAPIV1Api.md#productcapabilitiesGetproducts) | **GET** /referencedata/v1/productcapabilities | Get available products


## `productcapabilitiesGetproducts()`

```php
productcapabilitiesGetproducts($originCountryCode, $originPostalCode, $destinationCountryCode, $destinationPostalCode, $destinationRecipientType, $parcels, $weight, $destinationAddressType, $length, $width, $height, $diameter, $internationalProductFilter, $accountTypes, $doorstepDeliveryTypes, $currency, $totalValue, $pickupAccount, $exchangeOnDelivery): \DHLUK\Model\Products
```

Get available products

Get available products and services by address and size

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: OAuth2
$config = DHLUK\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new DHLUK\Api\ProductCapabilitiesAPIV1Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$originCountryCode = '1'; // string | ISO 2 character country code of origin address (Currently only GB supported)
$originPostalCode = 'AB'; // string | Postal code of origin address (Currently only GB postal codes supported)
$destinationCountryCode = 'gb'; // string | ISO 2 character country code of destination address
$destinationPostalCode = 'gu16'; // string | Postal code of destination address
$destinationRecipientType = 'business'; // string | Recipient type, either business or residential.
$parcels = 3.4; // float | Number of parcels being sent in this shipment
$weight = 3.4; // float | Gross weight of the shipment including packaging
$destinationAddressType = 'doorstep'; // string | Optional type of address required for delivery. For example if servicePoint then only service point products will be returned if available.
$length = 3.4; // float | Total length of the shipment including packaging
$width = 3.4; // float | Total width of the shipment including packaging
$height = 3.4; // float | Total height of the shipment including packaging
$diameter = 3.4; // float | Total diameter of the shipment including packaging
$internationalProductFilter = 'full'; // string | Optional filter for international export products, either best or full. best = best available Air and Road products returned. Maximum of one air and one road product will be returned. full = full list of available products will be returned.
$accountTypes = array('accountTypes_example'); // string[] | Optionally supply one or more accountTypes to filter products by
$doorstepDeliveryTypes = array('doorstepDeliveryTypes_example'); // string[] | Optionally supply one or more doorstepDeliveryTypes to filter products by. doorstepOnly will only return products where neighbourDelivery and secureLocationDelivery are not enabled. neighbourDelivery will only return products where neighbourDelivery is available. secureLocationDelivery will only return products where secureLocationDelivery is available. Using doorstepOnly in combination with neighbourDelivery or secureLocationDelivery is not recommended as no products will be returned
$currency = 'currency_example'; // string | ISO currency code for shipment total value. Required for countries where IOSS VAT rules apply (European Union).
$totalValue = 3.4; // float | Total value of shipment in currency specified. Required for countries where IOSS VAT rules apply (European Union).
$pickupAccount = 'pickupAccount_example'; // string | Optional specific pickup account number
$exchangeOnDelivery = True; // bool | Is an exchange on delivery required?

try {
    $result = $apiInstance->productcapabilitiesGetproducts($originCountryCode, $originPostalCode, $destinationCountryCode, $destinationPostalCode, $destinationRecipientType, $parcels, $weight, $destinationAddressType, $length, $width, $height, $diameter, $internationalProductFilter, $accountTypes, $doorstepDeliveryTypes, $currency, $totalValue, $pickupAccount, $exchangeOnDelivery);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductCapabilitiesAPIV1Api->productcapabilitiesGetproducts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **originCountryCode** | **string**| ISO 2 character country code of origin address (Currently only GB supported) | [default to &#39;1&#39;]
 **originPostalCode** | **string**| Postal code of origin address (Currently only GB postal codes supported) | [default to &#39;AB&#39;]
 **destinationCountryCode** | **string**| ISO 2 character country code of destination address | [default to &#39;gb&#39;]
 **destinationPostalCode** | **string**| Postal code of destination address | [default to &#39;gu16&#39;]
 **destinationRecipientType** | **string**| Recipient type, either business or residential. | [default to &#39;business&#39;]
 **parcels** | **float**| Number of parcels being sent in this shipment |
 **weight** | **float**| Gross weight of the shipment including packaging |
 **destinationAddressType** | **string**| Optional type of address required for delivery. For example if servicePoint then only service point products will be returned if available. | [optional] [default to &#39;doorstep&#39;]
 **length** | **float**| Total length of the shipment including packaging | [optional]
 **width** | **float**| Total width of the shipment including packaging | [optional]
 **height** | **float**| Total height of the shipment including packaging | [optional]
 **diameter** | **float**| Total diameter of the shipment including packaging | [optional]
 **internationalProductFilter** | **string**| Optional filter for international export products, either best or full. best &#x3D; best available Air and Road products returned. Maximum of one air and one road product will be returned. full &#x3D; full list of available products will be returned. | [optional] [default to &#39;full&#39;]
 **accountTypes** | [**string[]**](../Model/string.md)| Optionally supply one or more accountTypes to filter products by | [optional]
 **doorstepDeliveryTypes** | [**string[]**](../Model/string.md)| Optionally supply one or more doorstepDeliveryTypes to filter products by. doorstepOnly will only return products where neighbourDelivery and secureLocationDelivery are not enabled. neighbourDelivery will only return products where neighbourDelivery is available. secureLocationDelivery will only return products where secureLocationDelivery is available. Using doorstepOnly in combination with neighbourDelivery or secureLocationDelivery is not recommended as no products will be returned | [optional]
 **currency** | **string**| ISO currency code for shipment total value. Required for countries where IOSS VAT rules apply (European Union). | [optional]
 **totalValue** | **float**| Total value of shipment in currency specified. Required for countries where IOSS VAT rules apply (European Union). | [optional]
 **pickupAccount** | **string**| Optional specific pickup account number | [optional]
 **exchangeOnDelivery** | **bool**| Is an exchange on delivery required? | [optional]

### Return type

[**\DHLUK\Model\Products**](../Model/Products.md)

### Authorization

[OAuth2](../../README.md#OAuth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
