---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudservicenetworkinterface
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterface.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterface.md
ms.openlocfilehash: 2bf2a5408a42adc628a79cffa6350cf434ff348e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140382244"
---
# Get-AzCloudServiceNetworkInterface

## SYNOPSIS
Dapatkan antarmuka jaringan tertentu di layanan awan.

## SYNTAX

### Daftar1 (Default)
```
Get-AzCloudServiceNetworkInterface -CloudServiceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzCloudServiceNetworkInterface -CloudServiceName <String> -Name <String> -ResourceGroupName <String>
 -RoleInstanceName <String> [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCloudServiceNetworkInterface -InputObject <ICloudServiceIdentity> [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzCloudServiceNetworkInterface -CloudServiceName <String> -ResourceGroupName <String>
 -RoleInstanceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan antarmuka jaringan tertentu di layanan awan.

## EXAMPLES

### Contoh 1: Dapatkan antarmuka jaringan dengan nama layanan cloud
```powershell
Get-AzCloudServiceNetworkInterface -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
```

Mendapatkan semua antarmuka jaringan untuk nama layanan awan tertentu.

### Contoh 2: Dapatkan antarmuka jaringan dengan objek layanan awan
```powershell
$cs = Get-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
Get-AzCloudServiceNetworkInterface -CloudService $cs
```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan tertentu.

### Contoh 3: Dapatkan antarmuka jaringan dengan objek layanan cloud dan nama contoh peran.
```powershell
Get-AzCloudServiceNetworkInterface -CloudServiceName $cs -RoleInstanceName WebRole1_IN_0
```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan dan nama contoh peran yang diberikan.

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
Memperluas sumber daya yang direferensikan.

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

### -Nama
Nama antarmuka jaringan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: NetworkInterfaceName

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
Nama contoh peran.

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

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.INetworkInterface

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICloudServiceIdentity>: Parameter Identitas
  - `[CloudServiceName <String>]`: 
  - `[IPConfigurationName <String>]`: Nama konfigurasi IP.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi yang terkait dengan versi OS.
  - `[NetworkInterfaceName <String>]`: Nama antarmuka jaringan.
  - `[OSFamilyName <String>]`: Nama keluarga OS.
  - `[OSVersionName <String>]`: Nama versi OS.
  - `[PublicIPAddressName <String>]`: Nama Alamat IP publik.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Nama contoh peran.
  - `[RoleName <String>]`: Nama peran.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[UpdateDomain <Int32?>]`: Menentukan nilai bilangan bulat yang mengidentifikasi domain pembaruan. Update domains are identified with a zero-based index: the first update domain has an ID of 0, the second has an ID of 1, and so on.

## RELATED LINKS

