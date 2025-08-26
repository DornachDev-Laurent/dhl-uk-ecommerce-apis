# # ProductCountryFeatureData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**productCode** | **string** | Product code. |
**countryCode** | **string** | ISO 2 character country code. |
**effectiveFrom** | **string** | Date and time this product country feature rule should apply from. | [optional]
**effectiveTo** | **string** | Date and time this product country feature rule should apply to. | [optional]
**recipientType** | **string** | Type of recipient being delivered to. |
**addressType** | **string** | Type of address being delivered to. |
**locationType** | **string** | If addressType is servicePoint then the type of service point this rule should apply to. | [optional]
**transitTimeDescription** | **string** | Description of the estimated transit time when this product, country, recipientType, addressType and locationType are selected. | [optional]
**minTransitTime** | **float** | Estimated minimum number of days transit time when this product, country, recipientType, addressType and locationType are selected. | [optional]
**maxTransitTime** | **float** | Estimated maximum number of days transit time when this product, country, recipientType, addressType and locationType are selected. | [optional]
**customsLevel** | **string** | What level of customs information is needed when this product , country, recipientType, addressType and locationType are selected. | [optional]
**standardParcels** | **bool** | Are standard non bulky parcels accepted for this product country feature rule? | [optional]
**bulkyParcels** | **bool** | Are bulky parcels accepted for this product country feature rule? | [optional]
**standardDims** | **bool** | Are standard product dimensions used for this product country feature rule? | [optional]
**maximumParcels** | **float** | Maximum number of parcels per shipment when using this product country feature rule. | [optional]
**maximumLength** | **float** | Maximum parcel length when using this product country feature rule. If null then no limit applies. | [optional]
**maximumWidth** | **float** | Maximum parcel width when using this product country feature rule. If null then no limit applies. | [optional]
**maximumHeight** | **float** | Maximum parcel height when using this product country feature rule. If null then no limit applies. | [optional]
**maximumGirth** | **float** | Maximum parcel girth when using this product country feature rule. If null then no limit applies. | [optional]
**maximumWeight** | **float** | Maximum weight per shipment when using this product country feature rule. | [optional]
**maximumDiameter** | **float** | Maximum parcel diameter when using this product country feature rule. If null then no limit applies. | [optional]
**maximumLengthGirth** | **float** | Maximum parcel length girth when using this product country feature rule. If null then no limit applies. | [optional]
**minimumLength** | **float** | Minimum parcel length when using this product country feature rule. If null then no limit applies. | [optional]
**minimumWidth** | **float** | Minimum parcel width when using this product country feature rule. If null then no limit applies. | [optional]
**minimumHeight** | **float** | Minimum parcel height when using this product country feature rule. If null then no limit applies. | [optional]
**minimumWeight** | **float** | Minimum weight per shipment when using this product country feature rule. | [optional]
**bulkyLength** | **float** | When length of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**bulkyWidth** | **float** | When width of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**bulkyHeight** | **float** | When height of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**bulkyGirth** | **float** | When girth of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**bulkyWeight** | **float** | When weight of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**bulkyDiameter** | **float** | When diameter of any parcel in shipment is greater than or equal to this value then shipment will be classified as bulky. If null then no bulky limit applies when using this product country feature rule. | [optional]
**postnummerRequired** | **bool** | Is a recipient postnummer type idNumber required when using this product country feature rule? | [optional]
**labelPersonalData** | **bool** | If true then personal data such as phone number and email can be included when the label is generated. If false then no personal data should be included on the label when generated for this product, country, recipientType, addressType and locationType. | [optional]
**returns** | **bool** | If true then inbox returns is available for this product, country, recipientType, addressType and locationType combination. | [optional]
**dutiesPaid** | **string** | *** SOON TO BE DEPRECATED, USE dutiesPaidList INSTEAD. *** Optional parameter to indicate which type of dutiesPaid MUST be used with this product for a customs declaration using the Shipping label API. DDP (Delivered Duties Paid), DAP (Delivered at Place). | [optional]
**exportExcludePostcodesBeginWith** | **string[]** | Beginning of postcodes in country where product should be excluded for exports from UK. | [optional]
**importExcludePostcodesBeginWith** | **string[]** | Beginning of postcodes in UK where product should be excluded for imports. | [optional]
**deliveryGateway** | **string[]** | List of delivery gateway&#39;s a shipment may be routed through. This feild is deprecated. Please refer transitGateway to get the list of list of transit gateway&#39;s a shipment may be routed through. | [optional]
**barcodeRoutingDateCode** | **string** | When this country and address type are used for a label, then when the contents of the routing barcode are generated use this value to encode into the Date field with the MH10 routing barcode. | [optional]
**customsLevelOverrides** | [**\DHLUK\Model\CustomsLevelOverride[]**](CustomsLevelOverride.md) | List of optional customs level overrides that should apply dependant on sender and consignee postcode | [optional]
**iossApplies** | **bool** | Do IOSS VAT rules apply when this product country feature rule applies? | [optional]
**iossValueLimits** | [**\DHLUK\Model\IossValueLimit[]**](IossValueLimit.md) | List of optional ioss value limits when iossApplies. | [optional]
**productAllowedIfIossLimitExceeded** | **bool** | Allow this product when total value exceeds the matching ioss value limit? Also if total value is below the ioss value limit then duties paid should override with the value of iossDutiesPaid. If total value is above the ioss value limit then do not override the duties paid. | [optional]
**iossDutiesPaid** | **string** | Optional parameter to indicate which type of dutiesPaid MUST be used if IOSS applies. DDP (Delivered Duties Paid), DAP (Delivered at Place). | [optional]
**nonIossAllowed** | **bool** | This product country feature can still be used under standard terms without using IOSS and having to supply an IOSS number. | [optional]
**maximumWeightPerParcel** | **float** | Maximum weight or average wight per parcel when using this product country feature rule. | [optional]
**maximumPallets** | **float** | Maximum number of pallets when using this product country feature rule. | [optional]
**dutiesPaidList** | **string[]** | Optional list of dutiesPaid values for a customs declaration that are allowed when using this product country feature rule. If defined one of these values MUST be used when creating a new shipment via the Shipping label API. Possible values in the list are DDP (Delivered Duties Paid), DAP (Delivered at Place). | [optional]
**limitedReasonForExportList** | [**\DHLUK\Model\ReasonForExport[]**](ReasonForExport.md) | Limited list of valid reasons for export for this product and country feature. | [optional]
**fullReasonForExportList** | [**\DHLUK\Model\ReasonForExport[]**](ReasonForExport.md) | Full list of valid reasons for export for this product and country feature. | [optional]
**serviceProviderCodes** | **string[]** | List of Sevice Providers for DHL eCommerce UK Product. | [optional]
**serviceProviderProductCode** | **string** | Service Provider Product code used for DHL eCommerce UK Product. | [optional]
**transitGateways** | **string[]** | List of transit gateway&#39;s a shipment may be routed through. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
