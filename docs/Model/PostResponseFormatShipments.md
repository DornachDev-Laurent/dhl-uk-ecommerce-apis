# # PostResponseFormatShipments

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**shipmentId** | **string** | shipment identifier for shipment created. |
**returnShipmentId** | **string** | shipment identifier for return shipment created if inBoxReturn was set to true. | [optional]
**labels** | **string[]** | List of labels. If label format is PNG or JPG then all labels will be returned as one label entry in zip format encoded as Base64 | [optional]
**paperlessTrade** | **bool** | Indicates if paperless trade was applied for shipment. This flag is applicable for international shipments outside UK and returned only for products that support paperless trade. Paperless Trade allows the clearance of an international shipment using data only. This removes the need for physical signed invoices to be attached to each shipment. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
