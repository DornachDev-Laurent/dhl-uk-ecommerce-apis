# # PostRequestFormat

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pickupAccount** | **string** | The DHL eCommerce UK account number. You will receive this after doing the onboarding with DHL sales. |
**dropOffType** | **string** | Specify how shipments will be handed over to DHL. PICKUP is for a driver pickup from your account address or a specified adhoc pickup address if a carriageForward. DROPOFF is for service point drop off, DEPOT is a DHL Parcel Depot or Hub drop off, before DROPOFF or DEPOT please check this has been enabled on your account via your account manager. |
**pickup** | [**\DHLUK\Model\PostRequestFormatPickup**](PostRequestFormatPickup.md) |  | [optional]
**pickupAddress** | [**\DHLUK\Model\PostRequestFormatPickupAddress**](PostRequestFormatPickupAddress.md) |  | [optional]
**senderAddress** | [**\DHLUK\Model\PostRequestFormatSenderAddress**](PostRequestFormatSenderAddress.md) |  |
**shipments** | [**\DHLUK\Model\PostRequestFormatShipments[]**](PostRequestFormatShipments.md) | Shipment to be created. Has a consigneeAddress and potentially multiple pieces. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
