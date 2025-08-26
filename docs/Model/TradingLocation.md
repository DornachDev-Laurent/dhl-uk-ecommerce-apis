# # TradingLocation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tradingLocationId** | **string** | Unique ID for this customer trading location | [optional]
**status** | **string** | Customer trading location status. active &#x3D; active trading customer, new orders are being accepted without restriction. onStop &#x3D; Customer at trading location is currently on stop, new orders cannot currently be accepted. closed &#x3D; trading location is closed, new orders cannot be accepted. | [optional]
**companyName** | **string** | Name of organisation/trading location | [optional]
**address1** | **string** | Line 1 of the street address | [optional]
**address2** | **string** | Line 2 of the street address | [optional]
**address3** | **string** | Line 3 of the street address | [optional]
**city** | **string** | city | [optional]
**state** | **string** | county, state, province or territory. | [optional]
**postalCode** | **string** | postal code | [optional]
**country** | **string** | Two-character ISO country code. | [optional]
**accounts** | [**\DHLUK\Model\CustomerOperationalAccountsAssociatedWithThisTradingLocationLocation[]**](CustomerOperationalAccountsAssociatedWithThisTradingLocationLocation.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
