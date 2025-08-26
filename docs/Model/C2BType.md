# # C2BType

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**shipmentMovementType** | **string** | Use C2B |
**recipientEORINumber** | **string** | An EORI number can be obtained from HMRC note you will need an XI EORI | [optional]
**recipientUKIMSNumber** | **string** | UKIMS number is issued by HMRC and allows you to declare goods not at risk of entering the EU. The UKIMS number must be 32 characters in length. This should correspond to the recipient EORI number | [optional]
**totalValue** | **float** | Sum of all unit value listed as part of the contents. |
**currency** | **string** | Three-letter ISO Currency code. We currently accept only EUR, GBP &amp; USD as valid currencies | [optional]
**reasonForExport** | **string** | Use one of the following gift,commercialSample,commercialSale | [optional]
**numberOfItems** | **int** | Sum of all item quantity listed as part of contents. |
**items** | **object[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
