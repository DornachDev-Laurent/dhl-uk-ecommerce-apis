# # B2BRedLaneType

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**shipmentMovementType** | **string** | Use B2B |
**sendersDefermentAccount** | **string** | If blank and shipment movement type is B2B red lane then DHL deferment account will be applied | [optional]
**recipientEORINumber** | **string** | An EORI number can be obtained from HMRC note you will need an XI EORI. Mandatory for B2B Red Lane | [optional]
**totalValue** | **float** | Sum of all unit value listed as part of the contents. |
**currency** | **string** | Three-letter ISO Currency code. We currently accept only EUR, GBP &amp; USD as valid currencies | [optional]
**reasonForExport** | **string** | Use one of the following gift,commercialSample,commercialSale |
**shippingCharges** | **float** | The amount paid to ship the item. |
**numberOfItems** | **int** | Sum of all item quantity listed as part of contents. |
**items** | **object[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
