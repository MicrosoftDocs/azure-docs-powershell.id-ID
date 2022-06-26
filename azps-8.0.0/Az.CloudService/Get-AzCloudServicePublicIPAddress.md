---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudservicepublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServicePublicIPAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServicePublicIPAddress.md
ms.openlocfilehash: 83d7f6fc2a2193e096e44ce943bfaefe60f66a72
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146619022"
---
# Get-AzCloudServicePublicIPAddress

## SYNOPSIS
Dapatkan alamat IP publik yang ditentukan di layanan awan.

## SYNTAX

### Daftar (Default)
```
Get-AzCloudServicePublicIPAddress -CloudServiceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzCloudServicePublicIPAddress -CloudServiceName <String> -IPConfigurationName <String> -Name <String>
 -NetworkInterfaceName <String> -ResourceGroupName <String> -RoleInstanceName <String>
 [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCloudServicePublicIPAddress -InputObject <ICloudServiceIdentity> [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzCloudServicePublicIPAddress -CloudServiceName <String> -IPConfigurationName <String>
 -NetworkInterfaceName <String> -ResourceGroupName <String> -RoleInstanceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan alamat IP publik yang ditentukan di layanan awan.

## EXAMPLES

### Contoh 1: Dapatkan alamat IP publik tingkat instans untuk nama layanan cloud tertentu.
```powershell
Get-AzCloudServicePublicIPAddress -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
```

Mendapatkan alamat IP publik tingkat instans untuk nama layanan cloud tertentu.

### Contoh 2: Mendapatkan alamat IP publik tingkat instans untuk objek layanan cloud tertentu.
```powershell
$cs = Get-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
Get-AzCloudServicePublicIPAddress -CloudService $cs
```

Mendapatkan alamat IP publik tingkat instans untuk objek layanan cloud tertentu.

## PARAMETERS

### -CloudServiceName
Nama layanan awan.

```yaml
Type: System.String
Parameter Sets: Get, List, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Perluas
Memperluas sumber daya yang dirujuk.

```yaml
Type: System.String
Parameter Sets: Get, GetViaIdentity
Aliases:

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

### -IPConfigurationName
Nama konfigurasi IP.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Alamat IP publik.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: PublicIPAddressName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterfaceName
Nama antarmuka jaringan.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleInstanceName
Nama instans peran.

```yaml
Type: System.String
Parameter Sets: Get, List1
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
Parameter Sets: Get, List, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.IPublicIPAddress

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

