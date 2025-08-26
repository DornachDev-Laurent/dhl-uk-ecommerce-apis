# # PostRequestFormatConsigneeAddress

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**recipientType** | **string** | Type of recipient being delivered to |
**addressType** | **string** | Type of address being delivered to |
**companyName** | **string** | Optional Name of the organisation receiving the shipment. If addressType is servicePoint, then this is the companyName returned from the Service Point Finder API. | [optional]
**address1** | **string** | Line 1 of the consignee&#39;s street address or delivery location. If addressType is servicePoint, then this is the title returned from the Service Point Finder API. |
**address2** | **string** | Line 2 of the consignee&#39;s street address or delivery location. If addressType is servicePoint, then this is the address1 returned from the Service Point Finder API. | [optional]
**address3** | **string** | Line 3 of the consignee&#39;s street address or delivery location - typically used for addresses to designate province, district, or neighborhood. If addressType is servicePoint, then this is the address2 returned from the Service Point Finder API. | [optional]
**city** | **string** | Consignee&#39;s city. If addressType is servicePoint, then this is the city returned from the Service Point Finder API. |
**state** | **string** | Consignee&#39;s county, state, province or territory. If addressType is servicePoint, then this is the state returned from the Service Point Finder API. | [optional]
**postalCode** | **string** | Consignee&#39;s postal code. If addressType is servicePoint, then this is the postalCode returned from the Service Point Finder API. |
**country** | **string** | Two-character ISO consignee address country code. If addressType is servicePoint, then this is the country returned from the Service Point Finder API. |
**what3words** | [**\DHLUK\Model\PostRequestFormatConsigneeAddressWhat3words**](PostRequestFormatConsigneeAddressWhat3words.md) |  | [optional]
**name** | **string** | Name of the person receiving the shipment |
**email** | **string** | Consignee&#39;s email address. Please supply to allow pre delivery notifications. | [optional]
**phone** | **string** | Consignee&#39;s phone number | [optional]
**locationId** | **string** | If addressType is servicePoint, then this is the servicePointId returned from the Service Point Finder API | [optional]
**locationType** | **string** | If addressType is servicePoint, then address type of service point: Parcel Shop (More types added in future) | [optional]
**idNumber** | **string** | Consignee&#39;s identification number | [optional]
**idType** | **string** | Denotes the type of identification number provided by the consignee for customs clearance and delivery. Note: Provide if available for DHL Parcel International Direct to S. Korea and China | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
