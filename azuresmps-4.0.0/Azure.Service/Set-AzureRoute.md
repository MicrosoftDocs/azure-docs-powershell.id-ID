---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: A7DFF559-188D-4CF9-9315-CA327E0C5C0B
online version: ''
schema: 2.0.0
ms.openlocfilehash: a5807f3501155b771a586d8a96689325689cf4c3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142654606"
---
# Set-AzureRoute

## SYNOPSIS
Membuat rute dalam tabel rute.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureRoute -RouteName <String> -AddressPrefix <String> -NextHopType <String> [-NextHopIpAddress <String>]
 -RouteTable <IRouteTable> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRoute** membuat rute dalam tabel rute.
Rute baru diterapkan hampir segera pada mesin virtual yang terkait dengan tabel rute.

## EXAMPLES

### Contoh 1: Tambahkan alat virtual rute hop berikutnya
```
PS C:\> New-AzureRouteTable -Name "ApplianceRouteTable" -Location "Central US" -Label "Appliance Route Table" | Set-AzureRoute -RouteName "ApplianceRoute03" -AddressPrefix "10.0.0.0/24" -NextHopType VirtualAppliance -NextHopIpAddress "10.0.1.5"

Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute}                    AppRT                         Central US                    Appliance Route Table
```

Perintah ini membuat tabel rute bernama ApplianceRouteTable di lokasi yang ditentukan.
Perintah melewati tabel rute ke cmdlet saat ini.
Cmdlet saat ini menambahkan rute bernama ApplianceRoute03, yang merupakan tipe hop VirtualAppliance berikutnya.
Perintah menentukan alamat IP hop berikutnya dan prefiks alamat untuk rute.

### Contoh 2: Tambahkan rute lompatan internet berikutnya
```
PS C:\> Get-AzureRouteTable -Name "ApplianceRouteTable" | Set-AzureRoute -RouteName "InternetRoute" -AddressPrefix "0.0.0.0/0" -NextHopType Internet

Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute, internetroute}     AppRT                         Central US                    Appliance Route Table
```

Perintah ini mendapatkan tabel rute bernama ApplianceRouteTable.
Perintah melewati tabel rute ke cmdlet saat ini.
Cmdlet saat ini menambahkan rute bernama InternetRoute, yang merupakan tipe hop Internet berikutnya.
Perintah menentukan prefiks alamat untuk rute.

## PARAMETERS

### -AddressPrefix
Menentukan prefiks alamat untuk rute baru.

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

### -NextHopIpAddress
Menentukan alamat IP peralatan yang merupakan lompatan berikutnya untuk lalu lintas yang menggunakan rute ini.
Tentukan nilai ini hanya jika Anda menentukan nilai VirtualAppliance untuk parameter *NextHopType* .

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

### -NextHopType
Menentukan tipe hop berikutnya untuk lalu lintas yang menggunakan rute ini.
Nilai yang valid adalah: 

- VPNGateway
- VNETLocal
- Internet
- VirtualAppliance
- Null

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

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -RouteName
Menentukan nama untuk rute baru yang ditambahkan cmdlet ini.

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

### -RouteTable
Menentukan tabel rute tempat cmdlet ini menambahkan rute baru.

```yaml
Type: IRouteTable
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Hapus-AzureRoute](./Remove-AzureRoute.md)


