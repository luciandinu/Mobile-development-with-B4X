# B4A: Checking for network or internet connection

One common problem on a mobile device is to check if the device has an internet connection or is connected to a WiFi network or maybe if is connected at all.


Checking if the device is connected to internet. This method might not work on all devices.

```xojo
'This code needs the following libs: Phone, Network
'Returns true if the device is connected to internet
Sub IsConnectedToInternet As Boolean
	Dim mResult=False As Boolean
	Dim localAddress = "127.0.0.1" As String
	Dim mPhone As Phone, mServer As ServerSocket'Add a reference to the network library  'Check status: DISCONNECTED 0
	Try
		mServer.Initialize(0, "")
		If mServer.GetMyIP <> localAddress Then mResult = True : Exit
		If mPhone.GetDataState.EqualsIgnoreCase("CONNECTED") And mServer.GetMyWifiIP <> localAddress Then mResult = True: Exit
	Catch
		'If anything is wrong mResult will remain false
	End Try
	Log("Is connected to internet?: " & mResult)
	Return mResult
End Sub
```

Using the great MFLib is quite easy to get the network stare (to see if the device is connected to a network).

```xojo
'This code needs the following libs: MFLib
'You also need to add: AddPermission("android.permission.ACCESS_NETWORK_STATE") in your manifest editor
'This code is actually checks to see if the device is connected to a network
'Returns true if the device is connected to a network: WiFi, Mobile, Bluetooth
Sub IsConnectedToNetwork As Boolean
	Dim mResult=False As Boolean
	Dim mInfo As MF_Info
	If mInfo.IsConnected <> "" Then
		mResult = True
	End If
	Log("Is connected to network?: " & mResult) 
	Return mResult
End Sub
```

This code is particular case of the previeous example where we just check for a WiFi connection.

```xojo
'This code needs the following libs: Phone
'Returns true if WIFI is enabled
Sub IsWIFIEnabled As Boolean
	Dim mPhone As Phone '0 is off, 2 is on, don't know if it's connected, same for 3
	Return mPhone.GetSettings ("wifi_on") =1
End Sub
```