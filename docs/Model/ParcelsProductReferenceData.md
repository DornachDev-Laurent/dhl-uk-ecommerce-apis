# # ParcelsProductReferenceData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**productCode** | **string** | Product code |
**productName** | **string** | Product Name |
**shipmentType** | **string** | Type of shipment this product can be used for |
**sortOrder** | **float** | Sort order used when displaying multiple products, lowest value equals highest sort order in a list. For example sort order 1 would be first item in the list | [optional]
**maximumParcels** | **float** | Maximum number of parcels per shipment when using this product | [optional]
**maximumWeight** | **float** | Maximum weight per shipment when using this product | [optional]
**fixedParcels** | **float** | Does this product have a fixed value for the number of parcels that must be applied if selected e.g. 1. If value is 0 then no fixed value applies | [optional]
**fixedWeight** | **float** | Does this product have a fixed value for weight that must be applied if selected e.g. 5. If value is 0 then no fixed value applies | [optional]
**dimensionsMandatory** | **bool** | Is is mandatory to provide parcel dimensions when using this product? | [optional]
**maximumLength** | **float** | Maximum parcel length when using this product. If value is 0 then no maximum applies | [optional]
**maximumWidth** | **float** | Maximum parcel width when using this product. If value is 0 then no maximum applies | [optional]
**maximumHeight** | **float** | Maximum parcel height when using this product. If value is 0 then no maximum applies | [optional]
**bulkyLength** | **float** | When length of any parcel in shipment is greater than or equal to this value then shipment must be declared as bulky when the shipment is manifested. If value is 0 then this rule does not apply | [optional]
**bulkyWidth** | **float** | When width of any parcel in shipment is greater than or equal to this value then shipment must be declared as bulky when the shipment is manifested. If value is 0 then this rule does not apply | [optional]
**bulkyHeight** | **float** | When height of any parcel in shipment is greater than or equal to this value then shipment must be declared as bulky when the shipment is manifested. If value is 0 then this rule does not apply | [optional]
**bulkyGirth** | **float** | When girth of any parcel in shipment is greater than or equal to this value then shipment must be declared as bulky when the shipment is manifested. If value is 0 then this rule does not apply | [optional]
**accountType** | **string** | Type of account required when creating a shipment for this product |
**shipmentIdentifierType** | **string** | Type of shipment identifier to generate when creating a new shipment for this product |
**labelType** | **string** | Type of label to generate when producing a label for this product, | [optional]
**labelProductName** | **string** | Product name to print on labels when a label for this product is generated | [optional]
**labelSortationName** | **string** | Sortation code to print on labels when a label for this product is generated. For deliveries in the United Kingdom this will be empty and the label sortation code will need to be looked up from the UKPostcodeDistrict resource using the UK delivery postcode | [optional]
**barcodeProductCode** | **string** | Product code to encode into a DHL routing barcode when generating a label | [optional]
**servicePointCollection** | **bool** | Does this product allow collections from ServicePoint&#39;s? | [optional]
**servicePointDelivery** | **bool** | Does this product allow delivery to ServicePoint&#39;s? | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
