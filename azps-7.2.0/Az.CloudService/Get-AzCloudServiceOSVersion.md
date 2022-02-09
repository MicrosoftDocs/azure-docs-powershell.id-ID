---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudserviceosversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceOSVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceOSVersion.md
ms.openlocfilehash: f239ae0988cc85065c6c1b4e9056310d15e8de0f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138269484"
---
# Get-AzCloudServiceOSVersion

## SYNOPSIS
Mendapatkan properti versi sistem operasi tamu yang dapat ditentukan dalam konfigurasi layanan XML (.cscfg) untuk layanan awan.

## SYNTAX

### Daftar (Default)
```
Get-AzCloudServiceOSVersion -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzCloudServiceOSVersion -Location <String> -OSVersionName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCloudServiceOSVersion -InputObject <ICloudServiceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti versi sistem operasi tamu yang dapat ditentukan dalam konfigurasi layanan XML (.cscfg) untuk layanan awan.

## EXAMPLES

### Contoh 1: Dapatkan semua versi OS di suatu lokasi
```powershell
PS C:\> Get-AzCloudServiceOSVersion -location 'westus2'

Name                        Label                                            IsDefault IsActive Family FamilyLabel
----                        -----                                            --------- -------- ------ -----------
WA-GUEST-OS-6.7_201905-01   Windows Azure Guest OS 6.7 (Release 201905-01)   False     False    6      Windows Server 2019
WA-GUEST-OS-3.21_201411-01  Windows Azure Guest OS 3.21 (Release 201411-01)  False     False    3      Windows Server 2012
WA-GUEST-OS-3.34_201512-01  Windows Azure Guest OS 3.34 (Release 201512-01)  False     False    3      Windows Server 2012
WA-GUEST-OS-3.26_201504-01  Windows Azure Guest OS 3.26 (Release 201504-01)  False     False    3      Windows Server 2012
WA-GUEST-OS-2.46_201512-01  Windows Azure Guest OS 2.46 (Release 201512-01)  False     False    2      Windows Server 2008 R2
```

Perintah ini mendapatkan semua versi OS di lokasi westus2

### Contoh 2: Dapatkan versi OS
```powershell
PS C:\> Get-AzCloudServiceOSVersion -location 'westus2' -OSVersionName 'WA-GUEST-OS-6.7_201905-01'

Name                      Label                                          IsDefault IsActive Family FamilyLabel
----                      -----                                          --------- -------- ------ -----------
WA-GUEST-OS-6.7_201905-01 Windows Azure Guest OS 6.7 (Release 201905-01) False     False    6      Windows Server 2019
```

Perintah ini mendapatkan versi OS yang bernama WA-GUEST-OS-6.7_201905-01 yang terletak di westus2.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Nama lokasi yang terkait dengan versi OS.

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

### -OSVersionName
Nama versi OS.

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.IOSVersion

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICloudServiceIdentity>: Parameter Identitas
  - `[CloudServiceName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi yang terkait dengan versi OS.
  - `[OSFamilyName <String>]`: Nama keluarga OS.
  - `[OSVersionName <String>]`: Nama versi OS.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Nama contoh peran.
  - `[RoleName <String>]`: Nama peran.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[UpdateDomain <Int32?>]`: Menentukan nilai bilangan bulat yang mengidentifikasi domain pembaruan. Update domains are identified with a zero-based index: the first update domain has an ID of 0, the second has an ID of 1, and so on.

## RELATED LINKS

