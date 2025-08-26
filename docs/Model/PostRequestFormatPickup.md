# # PostRequestFormatPickup

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **string** | Pickup date in ISO 8601 date format. |
**accountAddress** | **bool** | Should the shipment be collected from the pickupAccount address? If false then shipment will be collected from the supplied pickupAddress which then becomes mandatory. |
**pickupIdentifier** | **string** | Pickup Identifier for a pickup from an account holder address i.e. accountAddress is true. This will have been returned from a previous call to the Pickup API. Not required if accountAddress is false. | [optional]
**instructions** | **string** | Optional special instructions for driver at pickup | [optional]
**secureLocation** | **string** | Description of a location where the parcels have been left securely for unattended collection | [optional]
**labelRequired** | **bool** | Indicates whether the pickup driver needs to print and apply labels to the parcel at pickup. Not for pickup at accountAddress. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
