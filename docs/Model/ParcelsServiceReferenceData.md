# # ParcelsServiceReferenceData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **string** | Service code. This code needs to be passed as Ordered Product in Shipping label API. |
**productCode** | **string** | Product code for the product this service relates to |
**description** | **string** | Short service description |
**longDescription** | **string** | Longer service description | [optional]
**labelDescription** | **string** | Service description to print on labels if this service is selected | [optional]
**serviceLevel** | **string** |  |
**bulkyAllowed** | **bool** | Are bulky parcels allowed for this service? | [optional]
**deliveryWindowStart** | **string** | Standard delivery window start time for this service on the day of delivery | [optional]
**deliveryWindowEnd** | **string** | Standard delivery window end time for this service on the day of delivery | [optional]
**servicePoint** | **bool** | Is service point delivery permitted with this service? | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
