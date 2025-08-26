# # Product

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**productName** | **string** | Name of DHL eCommerce UK Product | [optional]
**productNameForUI** | **string** | Name of DHL eCommerce UK Product to be displayed in UI | [optional]
**productCode** | **string** | DHL eCommerce UK product code | [optional]
**pickupCapabilities** | [**\DHLUK\Model\ProductPickupCapabilities**](ProductPickupCapabilities.md) |  | [optional]
**deliveryCapabilities** | [**\DHLUK\Model\ProductDeliveryCapabilities**](ProductDeliveryCapabilities.md) |  | [optional]
**sortOrder** | **int** | Returns the sort order indicating the best product. The lowest sort order number &#x3D; the best product (Maximum of 2 products will be displayed) | [optional]
**dutiesPaid** | **string** | *** SOON TO BE DEPRECATED, USE dutiesPaidList INSTEAD. *** Recommended value for dutiesPaid when creating a shipment using the Shipping Label API. DDP (Delivered Duties Paid), DAP (Delivered at Place) | [optional]
**dutiesPaidList** | **string[]** | Allowed values for dutiesPaid when creating a shipment using the Shipping Label API for this product. Possible values in the list are DDP (Delivered Duties Paid), DAP (Delivered at Place). | [optional]
**reasonForExportList** | [**\DHLUK\Model\ReasonForExport[]**](ReasonForExport.md) | List of valid reasons for export for this product and country. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
