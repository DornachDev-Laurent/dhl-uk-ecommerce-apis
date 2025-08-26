# # ServicePoint

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique global id for this Service Point location | [optional]
**servicePointId** | **string** | servicePointId to pass to DHL eCommerce UK Shipping Label API | [optional]
**title** | **string** | Title description of this Service Point ready to display in UI. | [optional]
**address** | [**\DHLUK\Model\ServicePointAddress**](ServicePointAddress.md) |  | [optional]
**latitude** | **float** | Latitude of Service Point location | [optional]
**longitude** | **float** | Longitude of Service Point location | [optional]
**distance** | **int** | Distance in metres from location | [optional]
**parking** | **bool** | Is parking available at this Service Point? | [optional]
**disabledAccess** | **bool** | Is disabled access available at this Service Point? | [optional]
**openingHours** | [**\DHLUK\Model\OpeningHour[]**](OpeningHour.md) | List of Service Point opening hours | [optional]
**closurePeriods** | [**\DHLUK\Model\ClosurePeriod[]**](ClosurePeriod.md) | Periods where the DHL Service Point location is closed in the addition to opening hours. | [optional]
**serviceTypes** | **string[]** | List of DHL services available at this Service Point. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
