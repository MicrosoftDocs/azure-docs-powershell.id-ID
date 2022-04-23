---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainerinstancecontainergroupoutboundnetworkdependencyendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint.md
ms.openlocfilehash: 22b02f0445e0ea3a0e134fed7c724999785721b7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143229797"
---
# Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint

## SYNOPSIS
Mendapatkan semua dependensi jaringan untuk grup kontainer ini untuk memungkinkan kontrol penuh pengaturan dan konfigurasi jaringan.
Untuk grup wadah, ini akan selalu menjadi daftar kosong.

## SYNTAX

### Dapatkan (Default)
```
Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint -ContainerGroupName <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint
 -InputObject <IContainerInstanceIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan semua dependensi jaringan untuk grup kontainer ini untuk memungkinkan kontrol penuh pengaturan dan konfigurasi jaringan.
Untuk grup wadah, ini akan selalu menjadi daftar kosong.

## EXAMPLES

### Contoh 1: Dapatkan daftar dependensi jaringan keluar
```powershell
Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint -ResourceGroupName test-rg -ContainerGroupName test-cg
```

```output
[]
```

Perintah ini mengembalikan daftar dependensi jaringan keluar untuk Container Instances.
Container Instances tidak memiliki dependensi jaringan keluar, sehingga daftar ini akan kosong.

## PARAMETERS

### -ContainerGroupName
Nama grup wadah.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.IContainerInstanceIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.IContainerInstanceIdentity

## OUTPUTS

### System.String

## NOTES

ALIAS

Get-AzContainerGroupOutboundNetworkDependencyEndpoint

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IContainerInstanceIdentity>: Parameter Identitas
  - `[ContainerGroupName <String>]`: Nama grup wadah.
  - `[ContainerName <String>]`: Nama instans kontainer.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Pengidentifikasi untuk lokasi azure fisik.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

