# # B2BType

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**shipmentMovementType** | **string** | Use B2B |
**sendersEORINumber** | **string** | An EORI number can be obtained from HMRC note you will need an XI EORI. Mandatory if UKIMS is provided | [optional]
**sendersUKIMSNumber** | **string** | UKIMS number (UK Internal Market Scheme number) is issued by HMRC and allows you to declare goods not at risk of entering the EU The UKIMS number must be 32 characters in length.This should correspond to the senders EORI number | [optional]
**recipientEORINumber** | **string** | An EORI number can be obtained from HMRC note you will need an XI EORI | [optional]
**recipientUKIMSNumber** | **string** | UKIMS number is issued by HMRC and allows you to declare goods not at risk of entering the EU The UKIMS number must be 32 characters in length. This should correspond to the recipients EORI number | [optional]
**totalValue** | **float** | Sum of all unit value listed as part of the contents. |
**currency** | **string** | Three-letter ISO Currency code. We currently accept only EUR, GBP &amp; USD as valid currencies | [optional]
**reasonForExport** | **string** | Use one of the following gift,commercialSample,commercialSale |
**numberOfItems** | **int** | Sum of all item quantity listed as part of contents. |
**items** | **object[]** |  | [optional]
**sendersDefermentAccount** | **string** | If blank and shipment movement type is B2B red lane then DHL deferment account will be applied | [optional]
**recipientEORINumber** | **string** | An EORI number can be obtained from HMRC note you will need an XI EORI. Mandatory for B2B Red Lane | [optional]
**shippingCharges** | **float** | The amount paid to ship the item. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
