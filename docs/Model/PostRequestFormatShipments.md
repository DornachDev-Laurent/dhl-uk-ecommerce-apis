# # PostRequestFormatShipments

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**consigneeAddress** | [**\DHLUK\Model\PostRequestFormatConsigneeAddress**](PostRequestFormatConsigneeAddress.md) |  |
**recipientAddress** | [**\DHLUK\Model\PostRequestFormatRecipientAddress**](PostRequestFormatRecipientAddress.md) |  | [optional]
**shipmentDetails** | [**\DHLUK\Model\PostRequestFormatShipmentDetails**](PostRequestFormatShipmentDetails.md) |  |
**customsDetails** | [**\DHLUK\Model\PostRequestFormatCustomsDetails[]**](PostRequestFormatCustomsDetails.md) | Customs details for all commodities contained in shipment. Only applicable if orderedProduct is an International Product. Recommended to provide customs at shipment level. | [optional]
**pieces** | [**\DHLUK\Model\PostRequestFormatPieces[]**](PostRequestFormatPieces.md) | One or more pieces which constitute a shipment. Each piece is the physical box/parcel using its own tracking number, label, ID, list of commodities, VAS. | [optional]
**customsInvoice** | [**\DHLUK\Model\PostRequestFormatCustomsInvoice**](PostRequestFormatCustomsInvoice.md) |  | [optional]
**return** | [**\DHLUK\Model\PostRequestFormatReturn**](PostRequestFormatReturn.md) |  | [optional]
**extendedLiability** | [**\DHLUK\Model\PostRequestFormatExtendedLiability**](PostRequestFormatExtendedLiability.md) |  | [optional]
**senderCustomsRegistrations** | **object[]** | An array of customs registrations | [optional]
**recipientCustomsRegistrations** | [**\DHLUK\Model\PostRequestFormatRecipientCustomsRegistrations[]**](PostRequestFormatRecipientCustomsRegistrations.md) | An array of recipient customs registrations | [optional]
**customerPrice** | [**\DHLUK\Model\PostRequestFormatCustomerPrice**](PostRequestFormatCustomerPrice.md) |  | [optional]
**clearanceDeclaration** | [**\DHLUK\Model\ClearanceDeclaration**](ClearanceDeclaration.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
