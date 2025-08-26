# DHLUK Api Client


The DHL eCommerce UK API allows customers and partners to:
 - Get available products based on delivery address and parcel size.
 - Find servicepoints in the UK or worldwide.
 - Create new shipments and optionally return labels.
 - Get shipment customs documents.
 - Request shipment cancellation.
 - Request shipment amendment.
 - Regenerate labels ready for reprinting.
 - Get details of customer trading locations.
 - Request a driver pickup from a customer trading location.
 - Get information about driver pickups already requested.
 - Track shipments.
 - Get DHL eCommerce UK reference data to help you provide valid shipment data from your applications.
 - Add a What 3 Words to a domestic shipment.
 - Find a DHL Parcels Depot.


**`API Authentications:`** All API operations require an access token to be passed in the Authorization Header for each request. The token type is an OAuth 2.0 Bearer token. To get the token you have to call the Authentication operation of this API and provide **client_id** and **client_secret**. The Access Token is valid for defined amount of time so it is not necessary to request the token for each request. Developers should implement the client application in a way that the token will be requested again only after it expires.

**`Access Token Lifecycle:`** When you receive an Access Token, it is valid for 60 minutes. During this time, you don't have to request new token per each request, but you can simply reuse the same token to access API resources, until the token expires. The invalid token or token expiration will be indicated by HTTP Status Code 401 Unauthorized, then your application has to request new Access Token.

  **Recommended sequence for creating a shipment with the Shipping Label API is as follows:**
    
  1.  Use client_id and client_secret to authenticate and obtain an access token using /auth/v1/accesstoken (see details below). A client_id and client_secret can be obtained by registering on the DHL developer portal and then registering an app in the user dashboard.
  2.  Prepare valid JSON request as per Shipping Label API POST request schema (see examples below). Use data above depending on your use-case.
  3.  Send an API request the correct API endpoint for test/UAT or live/production:
  
      test: https://api-uat.dhl.com/parceluk/shipping/v1/label
      
      live: https://api.dhl.com/parceluk/shipping/v1/label
  
      If the shipment request is valid and accepted then a new shipmentId and optionally labels will be returned in the response.

**Sample Pickup Accounts And Product codes:**

  To test using the Shipping Label API, you may use the following accounts and additional settings.
    
  UK Domestic Shipping | Codes  | Comments
  ---|---|---
  pickupAccount      | F020579  | DHL eCommerce UK domestic labels
  orderedProduct            | 220      | Signature At Address Only - Next Day

  International Road Shipping | Codes  | Comments
  ---|---|---
  pickupAccount      | F820579  | DHL eCommerce UK Parcel Connect labels
  orderedProduct             | 206      | Parcel Connect         
  
  International Air Shipping | Codes  | Comments
  ---|---|---
  pickupAccount      | F520579 | DHL eCommerce UK International Labels
  orderedProduct             | 101     | Worldwide Air
      


## Installation & Usage

### Requirements

PHP 7.2 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/DHLUK Api Client/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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

## API Endpoints

All URIs are relative to *https://api-uat.dhl.com/parceluk*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccessTokenApi* | [**authV1AccesstokenPost**](docs/Api/AccessTokenApi.md#authv1accesstokenpost) | **POST** /auth/v1/accesstoken | Get Token
*CustomerAPIV1Api* | [**customerV1TradingLocationsGet**](docs/Api/CustomerAPIV1Api.md#customerv1tradinglocationsget) | **GET** /customer/v1/tradingLocations | Get customer trading locations
*CustomsDeclarationAPIV1Api* | [**customsdeclarationV1DocumentsGet**](docs/Api/CustomsDeclarationAPIV1Api.md#customsdeclarationv1documentsget) | **GET** /customsdeclaration/v1/documents | Get customs documents for a previously created shipment.
*LabelsAPIV1Api* | [**reprintlabelsV1LabelsGet**](docs/Api/LabelsAPIV1Api.md#reprintlabelsv1labelsget) | **GET** /reprintlabels/v1/labels | Regenerate a label
*LabelsAPIV1Api* | [**reprintlabelsV1ServicepointDropoffUkGet**](docs/Api/LabelsAPIV1Api.md#reprintlabelsv1servicepointdropoffukget) | **GET** /reprintlabels/v1/servicepoint-dropoff-uk | Regenerate a servicepoint drop off label/barcode
*PickupAPIV1Api* | [**pickupV1PickupGet**](docs/Api/PickupAPIV1Api.md#pickupv1pickupget) | **GET** /pickup/v1/pickup | Get pickup by identifier
*PickupAPIV1Api* | [**pickupV1PickupPost**](docs/Api/PickupAPIV1Api.md#pickupv1pickuppost) | **POST** /pickup/v1/pickup | Create a pickup
*PickupAPIV1Api* | [**pickupV1PickupsGet**](docs/Api/PickupAPIV1Api.md#pickupv1pickupsget) | **GET** /pickup/v1/pickups | Get pickups
*ProductCapabilitiesAPIV1Api* | [**productcapabilitiesGetproducts**](docs/Api/ProductCapabilitiesAPIV1Api.md#productcapabilitiesgetproducts) | **GET** /referencedata/v1/productcapabilities | Get available products
*ReferenceDataAPIV1Api* | [**countriesGetcountries**](docs/Api/ReferenceDataAPIV1Api.md#countriesgetcountries) | **GET** /referencedata/v1/countries | Get all countries
*ReferenceDataAPIV1Api* | [**countriesGetcountry**](docs/Api/ReferenceDataAPIV1Api.md#countriesgetcountry) | **GET** /referencedata/v1/country | Get country by either country code or name
*ReferenceDataAPIV1Api* | [**currenciesGetcurrencies**](docs/Api/ReferenceDataAPIV1Api.md#currenciesgetcurrencies) | **GET** /referencedata/v1/currencies | Get all currencies
*ReferenceDataAPIV1Api* | [**currenciesGetcurrency**](docs/Api/ReferenceDataAPIV1Api.md#currenciesgetcurrency) | **GET** /referencedata/v1/currency | Get currency by either currency code or name
*ReferenceDataAPIV1Api* | [**getEventStatusDetails**](docs/Api/ReferenceDataAPIV1Api.md#geteventstatusdetails) | **GET** /referencedata/v1/eventstatuses | Provides a reference list of all shipment status messages that can be returned in the shipment tracking API
*ReferenceDataAPIV1Api* | [**getReferencedataProducts**](docs/Api/ReferenceDataAPIV1Api.md#getreferencedataproducts) | **GET** /referencedata/v2/products | Get all products
*ReferenceDataAPIV1Api* | [**getUsstates**](docs/Api/ReferenceDataAPIV1Api.md#getusstates) | **GET** /referencedata/v1/usstates | Get all USState
*ReferenceDataAPIV1Api* | [**postcodedistrictGetpostcode**](docs/Api/ReferenceDataAPIV1Api.md#postcodedistrictgetpostcode) | **GET** /referencedata/v1/ukpostcodedistrict | Get UK Postcode District by postcode
*ReferenceDataAPIV1Api* | [**postcodedistrictGetpostcodedistricts**](docs/Api/ReferenceDataAPIV1Api.md#postcodedistrictgetpostcodedistricts) | **GET** /referencedata/v1/ukpostcodedistricts | Get all UK Postcode Districts
*ReferenceDataAPIV1Api* | [**publicHolidayGetpublicHolidays**](docs/Api/ReferenceDataAPIV1Api.md#publicholidaygetpublicholidays) | **GET** /referencedata/v1/publicholiday | Get Public Holiday data.
*ReferenceDataAPIV1Api* | [**referencedataV1ProductcountryfeatureGet**](docs/Api/ReferenceDataAPIV1Api.md#referencedatav1productcountryfeatureget) | **GET** /referencedata/v1/productcountryfeature | Get ProductCountryFeature
*ReferenceDataAPIV1Api* | [**referencedataV1ServicesGet**](docs/Api/ReferenceDataAPIV1Api.md#referencedatav1servicesget) | **GET** /referencedata/v1/services | Get all services
*ServicepointsApi* | [**servicepointV1FindByAddressGet**](docs/Api/ServicepointsApi.md#servicepointv1findbyaddressget) | **GET** /servicepoint/v1/find-by-address | Find nearest DHL Service Point locations to an address
*ServicepointsApi* | [**servicepointV1FindByGeoGet**](docs/Api/ServicepointsApi.md#servicepointv1findbygeoget) | **GET** /servicepoint/v1/find-by-geo | Search for DHL Service Point locations by geo coordinates
*ServicepointsApi* | [**servicepointV1ServicepointsIdGet**](docs/Api/ServicepointsApi.md#servicepointv1servicepointsidget) | **GET** /servicepoint/v1/servicepoints/{id} | Retrieve one DHL Service Point location by its ID
*ShippingLabelAPIV1Api* | [**shippingV1AmendmentPost**](docs/Api/ShippingLabelAPIV1Api.md#shippingv1amendmentpost) | **POST** /shipping/v1/amendment | Request a shipment amendment and optionally generate labels
*ShippingLabelAPIV1Api* | [**shippingV1CancellationPost**](docs/Api/ShippingLabelAPIV1Api.md#shippingv1cancellationpost) | **POST** /shipping/v1/cancellation | Request shipment cancellation
*ShippingLabelAPIV1Api* | [**shippingV1LabelPost**](docs/Api/ShippingLabelAPIV1Api.md#shippingv1labelpost) | **POST** /shipping/v1/label | Create a shipment and optionally a label
*TrackingAPIV1Api* | [**getImage**](docs/Api/TrackingAPIV1Api.md#getimage) | **GET** /tracking/v1/images/{imageId} | Retrieve a specific digital asset (signature scan, photo or other image)
*TrackingAPIV1Api* | [**getShipmentsPiece**](docs/Api/TrackingAPIV1Api.md#getshipmentspiece) | **GET** /tracking/v1/pieces | Track a piece in a shipment
*TrackingAPIV1Api* | [**getShipmentsTrackingnumberTrackingnumber**](docs/Api/TrackingAPIV1Api.md#getshipmentstrackingnumbertrackingnumber) | **GET** /tracking/v1/shipments | Track a shipment

## Models

- [AmendRequest](docs/Model/AmendRequest.md)
- [AmendRequestRecipient](docs/Model/AmendRequestRecipient.md)
- [AmendRequestShipmentDetails](docs/Model/AmendRequestShipmentDetails.md)
- [B2BGreenLaneType](docs/Model/B2BGreenLaneType.md)
- [B2BRedLaneType](docs/Model/B2BRedLaneType.md)
- [B2BType](docs/Model/B2BType.md)
- [B2CType](docs/Model/B2CType.md)
- [C2BType](docs/Model/C2BType.md)
- [C2CType](docs/Model/C2CType.md)
- [ClearanceDeclaration](docs/Model/ClearanceDeclaration.md)
- [ClosurePeriod](docs/Model/ClosurePeriod.md)
- [Country](docs/Model/Country.md)
- [CountryResponse](docs/Model/CountryResponse.md)
- [Currency](docs/Model/Currency.md)
- [CurrencyResponse](docs/Model/CurrencyResponse.md)
- [CustomerOperationalAccountsAssociatedWithThisTradingLocationLocation](docs/Model/CustomerOperationalAccountsAssociatedWithThisTradingLocationLocation.md)
- [CustomsLevelOverride](docs/Model/CustomsLevelOverride.md)
- [EventStatus](docs/Model/EventStatus.md)
- [IossValueLimit](docs/Model/IossValueLimit.md)
- [LabelResponse](docs/Model/LabelResponse.md)
- [LabelResponseLabels](docs/Model/LabelResponseLabels.md)
- [LocalmodelPieceEvent](docs/Model/LocalmodelPieceEvent.md)
- [LocalmodelPieceEvents](docs/Model/LocalmodelPieceEvents.md)
- [OpeningHour](docs/Model/OpeningHour.md)
- [ParcelsProductReferenceData](docs/Model/ParcelsProductReferenceData.md)
- [ParcelsServiceReferenceData](docs/Model/ParcelsServiceReferenceData.md)
- [Pickup](docs/Model/Pickup.md)
- [PickupAccepted](docs/Model/PickupAccepted.md)
- [PickupRequest](docs/Model/PickupRequest.md)
- [PostRequestFormat](docs/Model/PostRequestFormat.md)
- [PostRequestFormatConsigneeAddress](docs/Model/PostRequestFormatConsigneeAddress.md)
- [PostRequestFormatConsigneeAddressWhat3words](docs/Model/PostRequestFormatConsigneeAddressWhat3words.md)
- [PostRequestFormatConsigneeAddressWhat3wordsGeo](docs/Model/PostRequestFormatConsigneeAddressWhat3wordsGeo.md)
- [PostRequestFormatCustomerPrice](docs/Model/PostRequestFormatCustomerPrice.md)
- [PostRequestFormatCustomsDetails](docs/Model/PostRequestFormatCustomsDetails.md)
- [PostRequestFormatCustomsInvoice](docs/Model/PostRequestFormatCustomsInvoice.md)
- [PostRequestFormatExtendedLiability](docs/Model/PostRequestFormatExtendedLiability.md)
- [PostRequestFormatPickup](docs/Model/PostRequestFormatPickup.md)
- [PostRequestFormatPickupAddress](docs/Model/PostRequestFormatPickupAddress.md)
- [PostRequestFormatPieces](docs/Model/PostRequestFormatPieces.md)
- [PostRequestFormatRecipientAddress](docs/Model/PostRequestFormatRecipientAddress.md)
- [PostRequestFormatRecipientCustomsRegistrations](docs/Model/PostRequestFormatRecipientCustomsRegistrations.md)
- [PostRequestFormatReturn](docs/Model/PostRequestFormatReturn.md)
- [PostRequestFormatSenderAddress](docs/Model/PostRequestFormatSenderAddress.md)
- [PostRequestFormatShipmentDetails](docs/Model/PostRequestFormatShipmentDetails.md)
- [PostRequestFormatShipments](docs/Model/PostRequestFormatShipments.md)
- [PostResponseFormat](docs/Model/PostResponseFormat.md)
- [PostResponseFormatShipments](docs/Model/PostResponseFormatShipments.md)
- [Product](docs/Model/Product.md)
- [ProductCountryFeatureData](docs/Model/ProductCountryFeatureData.md)
- [ProductDeliveryCapabilities](docs/Model/ProductDeliveryCapabilities.md)
- [ProductDeliveryCapabilitiesServicePointLocationTypes](docs/Model/ProductDeliveryCapabilitiesServicePointLocationTypes.md)
- [ProductDeliveryCapabilitiesServices](docs/Model/ProductDeliveryCapabilitiesServices.md)
- [ProductPickupCapabilities](docs/Model/ProductPickupCapabilities.md)
- [Products](docs/Model/Products.md)
- [PublicHoliday](docs/Model/PublicHoliday.md)
- [PublicHolidayResponse](docs/Model/PublicHolidayResponse.md)
- [ReasonForExport](docs/Model/ReasonForExport.md)
- [ServicePoint](docs/Model/ServicePoint.md)
- [ServicePointAddress](docs/Model/ServicePointAddress.md)
- [SupermodelIoLogisticsSupportingOrganization](docs/Model/SupermodelIoLogisticsSupportingOrganization.md)
- [SupermodelIoLogisticsSupportingPerson](docs/Model/SupermodelIoLogisticsSupportingPerson.md)
- [SupermodelIoLogisticsSupportingPlace](docs/Model/SupermodelIoLogisticsSupportingPlace.md)
- [SupermodelIoLogisticsSupportingPlaceAddress](docs/Model/SupermodelIoLogisticsSupportingPlaceAddress.md)
- [SupermodelIoLogisticsSupportingProduct](docs/Model/SupermodelIoLogisticsSupportingProduct.md)
- [SupermodelIoLogisticsSupportingTimestamp](docs/Model/SupermodelIoLogisticsSupportingTimestamp.md)
- [SupermodelIoLogisticsTrackingDgfAirport](docs/Model/SupermodelIoLogisticsTrackingDgfAirport.md)
- [SupermodelIoLogisticsTrackingDgfLocation](docs/Model/SupermodelIoLogisticsTrackingDgfLocation.md)
- [SupermodelIoLogisticsTrackingDgfRoute](docs/Model/SupermodelIoLogisticsTrackingDgfRoute.md)
- [SupermodelIoLogisticsTrackingProofOfDelivery](docs/Model/SupermodelIoLogisticsTrackingProofOfDelivery.md)
- [SupermodelIoLogisticsTrackingShipment](docs/Model/SupermodelIoLogisticsTrackingShipment.md)
- [SupermodelIoLogisticsTrackingShipmentDetails](docs/Model/SupermodelIoLogisticsTrackingShipmentDetails.md)
- [SupermodelIoLogisticsTrackingShipmentDetailsDimensions](docs/Model/SupermodelIoLogisticsTrackingShipmentDetailsDimensions.md)
- [SupermodelIoLogisticsTrackingShipmentDetailsReferences](docs/Model/SupermodelIoLogisticsTrackingShipmentDetailsReferences.md)
- [SupermodelIoLogisticsTrackingShipmentEstimatedDeliveryTimeFrame](docs/Model/SupermodelIoLogisticsTrackingShipmentEstimatedDeliveryTimeFrame.md)
- [SupermodelIoLogisticsTrackingShipmentEvent](docs/Model/SupermodelIoLogisticsTrackingShipmentEvent.md)
- [SupermodelIoLogisticsTrackingShipments](docs/Model/SupermodelIoLogisticsTrackingShipments.md)
- [SupermodelIoSchemaorgDate](docs/Model/SupermodelIoSchemaorgDate.md)
- [SupermodelIoSchemaorgDateTime](docs/Model/SupermodelIoSchemaorgDateTime.md)
- [SupermodelIoSchemaorgPropertiesIataCode](docs/Model/SupermodelIoSchemaorgPropertiesIataCode.md)
- [SupermodelIoSchemaorgText](docs/Model/SupermodelIoSchemaorgText.md)
- [TradingLocation](docs/Model/TradingLocation.md)
- [TradingLocationsResponse](docs/Model/TradingLocationsResponse.md)
- [USStateReferenceData](docs/Model/USStateReferenceData.md)
- [UkPostcodeDistrict](docs/Model/UkPostcodeDistrict.md)
- [UkPostcodeDistrictResponse](docs/Model/UkPostcodeDistrictResponse.md)

## Authorization

### OAuth2

- **Type**: `OAuth`
- **Flow**: `application`
- **Authorization URL**: ``
- **Scopes**: N/A

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.3.8`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
