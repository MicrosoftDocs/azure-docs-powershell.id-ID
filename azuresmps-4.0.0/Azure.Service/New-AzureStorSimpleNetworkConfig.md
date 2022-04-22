---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 99D9EFA6-3506-4B0E-ACB5-C6EDBCB5A130
online version: ''
schema: 2.0.0
ms.openlocfilehash: b30f6d6c316a596810cc6439d5a7556bee68be0f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142980805"
---
# New-AzureStorSimpleNetworkConfig

## SYNOPSIS
Menyiapkan objek konfigurasi jaringan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleNetworkConfig -InterfaceAlias <String> [-EnableIscsi <Boolean>] [-EnableCloud <Boolean>]
 [-Controller0IPv4Address <String>] [-Controller1IPv4Address <String>] [-IPv6Gateway <String>]
 [-IPv4Gateway <String>] [-IPv4Address <String>] [-IPv6Prefix <String>] [-IPv4Netmask <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorSimpleNetworkConfig** menyiapkan objek konfigurasi jaringan untuk lolos ke cmdlet **Set-AzureStorSimpleDevice** .
Atur parameter *Controller0IPAddress* dan *parameter Controller1IPAddress* hanya pada antarmuka Data0.
Data0 hanya mendukung tiga pengaturan: *Controller0IPAddress*, *Controller1IPAdress*, dan *EnableIscsi*.

## EXAMPLES

### Contoh 1: Mengonfigurasi antarmuka Data0
```
PS C:\>New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49"
VERBOSE: ClientRequestId: 0621d220-a460-48ec-84ec-02a3a82f88b2_PS


IsIscsiEnabled         : True
IsCloudEnabled         : 
Controller0IPv4Address : 10.67.64.48
Controller1IPv4Address : 10.67.64.49
IPv6Gateway            : 
IPv4Gateway            : 
IPv4Address            : 
IPv6Prefix             : 
IPv4Netmask            : 
InterfaceAlias         : Data0

VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
```

Perintah ini membuat konfigurasi jaringan untuk antarmuka Data0.
Perintah ini menentukan parameter *Controller0IPv4Address*, *Controller1IPv4Address*, dan *EnableIscsi* .
Cmdlet ini hanya dapat mengonfigurasi Data0 untuk ketiga parameter ini.

### Contoh 2: Mengonfigurasi antarmuka selain Data0 an
```
PS C:\>New-AzureStorSimpleNetworkConfig -InterfaceAlias Data1 -EnableIscsi $True -EnableCloud $True -IPv6Gateway "db8:421e:9a8::a4:1c50" -IPv4Gateway "10.67.64.1" -IPv4Address "10.67.64.48" -IPv6Prefix "2001:db8:a::123/64" -IPv4Netmask "255.255.0.0"
VERBOSE: ClientRequestId: 3a15ff0e-b769-4329-9147-676b1e0acd7d_PS


IsIscsiEnabled         : True
IsCloudEnabled         : True
Controller0IPv4Address : 
Controller1IPv4Address : 
IPv6Gateway            : db8:421e:9a8::a4:1c50
IPv4Gateway            : 10.67.64.1
IPv4Address            : 10.67.64.48
IPv6Prefix             : 2001:db8:a::123/64
IPv4Netmask            : 255.255.0.0
InterfaceAlias         : Data1
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data1
```

Perintah ini mengonfigurasi antarmuka Data1.

### Contoh 3: Mengubah konfigurasi untuk perangkat
```
PS C:\>$NetworkConfigData0 = New-AzureStorSimpleNetworkConfig -InterfaceAlias Data0 -EnableIscsi $True -Controller0IPv4Address "10.67.64.48" -Controller1IPv4Address "10.67.64.49"
$OnlineDevice = @(Get-AzureStorSimpleDevice | Where { $_.Status -eq "Online"})[0]
$UpdatedDetails = Set-AzureStorSimpleDevice -DeviceId $OnlineDevice.DeviceId -StorSimpleNetworkConfig $NetworkConfigData0
VERBOSE: ClientRequestId: 0f163163-5ad0-4635-a7b5-870d47297f66_PS
VERBOSE: Successfully created a StorSimple Network Configuration for interface Data0
VERBOSE: ClientRequestId: 552e4a6c-7006-4015-a20b-9def6428a85e_PS
VERBOSE: ClientRequestId: f31cc84c-bc8a-404a-9da6-4670a7999e75_PS
VERBOSE: 1 StorSimple device found! 
VERBOSE: ClientRequestId: 545bc1a9-3c1b-4e50-89a6-9678aefe79e5_PS
VERBOSE: ClientRequestId: f114ad08-47f5-4fb8-8a01-1ea7f1ed1b98_PS
VERBOSE: About to configure the device : newDeviceName ! 
VERBOSE: ClientRequestId: 6afe7927-1c19-48d3-ac22-68148fd056b8_PS
VERBOSE: The task created for your Setup operation has completed successfully. 
VERBOSE: ClientRequestId: 467c142c-90da-4d75-82a4-c114afce953d_PS
VERBOSE: Successfully updated configuration for device newDeviceName with id 865e68f6-1e71-47b6-80d5-15d3a23bd2b0
```

Perintah pertama membuat konfigurasi jaringan untuk antarmuka Data0.
Perintah ini menentukan parameter *Controller0IPv4Address*, *Controller1IPv4Address*, dan *EnableIscsi* .
Perintah menyimpan hasil dalam variabel $NetworkConfigData 0.

Perintah kedua menggunakan cmdlet **Get-AzureStorSimpleDevice** dan cmdlet inti **Where-Object** untuk mendapatkan perangkat StorSimple online, lalu menyimpannya dalam variabel $OnlineDevice.

Perintah akhir mengubah konfigurasi untuk perangkat yang memiliki ID perangkat tertentu menggunakan cmdlet **Set-AzureStorSimpleDevice** .
Perintah menggunakan objek konfigurasi yang dibuat cmdlet saat ini dalam perintah pertama.

## PARAMETERS

### -Controller0IPv4Address
Menentukan alamat IPv4 untuk pengontrol 0.
Tentukan parameter ini hanya untuk antarmuka Data0.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Controller1IPv4Address
Menentukan alamat IPv4 untuk pengontrol 1.
Tentukan parameter ini hanya untuk antarmuka Data0.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCloud
Menunjukkan apakah akan mengaktifkan antarmuka cloud.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableIscsi
Menunjukkan apakah akan mengaktifkan Internet SCSI (ISCSI) untuk antarmuka.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Menentukan alias antarmuka yang menyediakan pengaturan cmdlet ini.
Nilai yang valid adalah dari Data0 ke Data5.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Menentukan alamat IPv4 untuk antarmuka.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Gateway
Menentukan alamat IPv4 gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Netmask
Menentukan netmask IPv4 untuk antarmuka.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Gateway
Menentukan gateway IPv6 untuk antarmuka.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Prefix
Menentukan prefiks IPv6 untuk antarmuka.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### NetworkConfig
Cmdlet ini mengembalikan objek NetworkConfig yang berisi properti berikut: 

- **IsIscsiEnabled** (**Boolean**) 
- **IsCloudEnabled** (**Boolean**)
- **Controller0IPv4Address** (**IPAddress**) 
- **Controller1IPv4Address** (**IPAddress**) 
- **IPv6Gateway** (**IPAddress**) 
- **IPv4Gateway** (**IPAddress**) 
- **IPv4Address** (**IPAddress**) 
- **IPv6Prefix** (**String**)
- **IPv4Netmask** (**IPAddress**) 
- **InterfaceAlias** (**NetInterfaceId**)

## NOTES

## RELATED LINKS

[Set-AzureStorSimpleDevice](./Set-AzureStorSimpleDevice.md)

[Get-AzureStorSimpleDevice](./Get-AzureStorSimpleDevice.md)


