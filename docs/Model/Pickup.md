# # Pickup

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pickupIdentifier** | **string** | pickupIdentifier for the pickup | [optional]
**pickupType** | **string** | Type of pickup | [optional]
**status** | **string** | Pickup status | [optional]
**customerAccountNumber** | **string** | customerAccountNumber for customer. | [optional]
**tradingLocationId** | **string** | Unique ID for customer trading location | [optional]
**requestedPickupDate** | **string** | Requested date for driver pickup. Format: yyyy-MM-dd | [optional]
**timeReady** | **string** | Time shipments will be ready for pickup. Format hh:mm | [optional]
**latestTime** | **string** | Latest time shipments can be picked up. Format hh:mm | [optional]
**instructions** | **string** | Any special instructions for the pickup driver | [optional]
**collectionJobNumber** | **string** | Confirmed collection job number | [optional]
**plannedPickupDate** | **string** | Planned date of next pickup attempt. Format: yyyy-MM-dd | [optional]
**driverId** | **string** | driverId of driver who will attempt the pickup | [optional]
**lastAttemptDateTime** | **string** | Date and time pickup completed. | [optional]
**success** | **bool** | Was the driver pickup successful? Were shipments collected? | [optional]
**qtyParcels** | **int** | Quantity of parcels collected at pickup | [optional]
**failureReasonCode** | **string** | failure reason code | [optional]
**failueReasonDescription** | **string** | failure reason description | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
