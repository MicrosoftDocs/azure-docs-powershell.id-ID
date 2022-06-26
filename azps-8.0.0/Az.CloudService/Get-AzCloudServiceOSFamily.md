---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudserviceosfamily
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceOSFamily.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceOSFamily.md
ms.openlocfilehash: a684f5b67891c0390a9835e257f2736193d32e89
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146608564"
---
# Get-AzCloudServiceOSFamily

## SYNOPSIS
Mendapatkan properti dari keluarga sistem operasi tamu yang dapat ditentukan dalam konfigurasi layanan XML (.cscfg) untuk layanan cloud.

## SYNTAX

### Daftar (Default)
```
Get-AzCloudServiceOSFamily -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzCloudServiceOSFamily -Location <String> -OSFamilyName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCloudServiceOSFamily -InputObject <ICloudServiceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti dari keluarga sistem operasi tamu yang dapat ditentukan dalam konfigurasi layanan XML (.cscfg) untuk layanan cloud.

## EXAMPLES

### Contoh 1: Mendapatkan semua keluarga OS di lokasi
```powershell
Get-AzCloudServiceOSFamily -location 'westus2'
```

```output
Name Label
---- -----
5    Windows Server 2016
4    Windows Server 2012 R2
6    Windows Server 2019
3    Windows Server 2012
2    Windows Server 2008 R2
```

Perintah ini mendapatkan semua keluarga OS di lokasi westus2

### Contoh 2: Dapatkan keluarga OS
```powershell
Get-AzCloudServiceOSFamily -location 'westus2' -OSFamilyName 5
```

```output
Name Label
---- -----
5    Windows Server 2016
```

Perintah ini mendapatkan keluarga OS bernama 5 yang terletak di westus2.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama lokasi yang berkaitan dengan keluarga OS.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSFamilyName
Nama keluarga OS.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.IOSFamily

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<ICloudServiceIdentity>`: Parameter Identitas
  - `[CloudServiceName <String>]`: 
  - `[IPConfigurationName <String>]`: Nama konfigurasi IP.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi yang berkaitan dengan versi OS.
  - `[NetworkInterfaceName <String>]`: Nama antarmuka jaringan.
  - `[OSFamilyName <String>]`: Nama keluarga OS.
  - `[OSVersionName <String>]`: Nama versi OS.
  - `[PublicIPAddressName <String>]`: Nama Alamat IP publik.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Nama instans peran.
  - `[RoleName <String>]`: Nama peran.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[UpdateDomain <Int32?>]`: Menentukan nilai bilangan bulat yang mengidentifikasi domain pembaruan. Domain pembaruan diidentifikasi dengan indeks berbasis nol: domain pembaruan pertama memiliki ID 0, yang kedua memiliki ID 1, dan sebagainya.

## RELATED LINKS

