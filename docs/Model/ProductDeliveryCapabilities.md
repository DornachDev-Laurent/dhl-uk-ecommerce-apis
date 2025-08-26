# # ProductDeliveryCapabilities

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**transitTimeDescription** | **string** | Description of transit time to destination country using this product e.g. 3-5 days. | [optional]
**minTransitTime** | **int** | Minimum transit time to destination country in days. Can be used alongside MaxTransitTime to display a range of estimated delivery dates from date of despatch | [optional]
**maxTransitTime** | **int** | Maximum transit time to destination country in days. Can be used to calculate an estimated maximum delivery date from date of pickup | [optional]
**servicePoint** | **bool** | Given the requested destination and parcel size would a Service Point direct delivery be available with this product? true &#x3D; Yes, false &#x3D; No. An example use case would be to enable servicepoint location finder in a UI. IMPORTANT - To ensure valid parcel sizes, please filter service points in the servicepoint location finder by the locationTypes available in the servicePointLocationTypes list | [optional]
**servicePointLocationTypes** | [**\DHLUK\Model\ProductDeliveryCapabilitiesServicePointLocationTypes[]**](ProductDeliveryCapabilitiesServicePointLocationTypes.md) | If service point delivery is available for this product at the destination then this is a list of service point location types that are available based on the shipment weight and dimensions. | [optional]
**customsDeclaration** | **string** | Level of customs declaration required for this product at the destination. Possible values are none, basic or full. | [optional]
**inBoxReturn** | **bool** | Is an inbox return capability available? | [optional]
**bulky** | **bool** | Given the shipment weight and dimensions, if this product is used, would the shipment be classified as Bulky? | [optional]
**accountType** | **string** | Type of DHL eCommerce UK account required when creating a shipment for this product | [optional]
**neighbourDelivery** | **bool** | Can the shipment be left with a neighbour at delivery? | [optional]
**secureLocationDelivery** | **bool** | Can the shipment be left in a secure location at delivery? | [optional]
**services** | [**\DHLUK\Model\ProductDeliveryCapabilitiesServices[]**](ProductDeliveryCapabilitiesServices.md) |  | [optional]
**iossApplies** | **bool** | Can the IOSS VAT capability be used with this product? A valid IOSS number must be supplied when adding a shipment. | [optional]
**nonIossAllowed** | **bool** | Can this product can still be used under standard terms without using the IOSS VAT capability and not supplying an IOSS number? | [optional]
**iossDutiesPaid** | **string** | Optional parameter to indicate which type of dutiesPaid MUST be used if IOSS is used. DDP (Delivered Duties Paid), DAP (Delivered at Place). | [optional]
**pallets** | **bool** | Is this product for a shipment of pallets where the number of pallets must then be captured to create a shipment? | [optional]
**exchangeOnDelivery** | **bool** | Is exchange on delivery available with this product? | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
