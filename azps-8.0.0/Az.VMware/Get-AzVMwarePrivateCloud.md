---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/get-azvmwareprivatecloud
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwarePrivateCloud.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwarePrivateCloud.md
ms.openlocfilehash: 3e0cf9233bff5e081002b2be6cbbf1b482d63425
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146623342"
---
# Get-AzVMwarePrivateCloud

## SYNOPSIS
Mendapatkan cloud privat

## SYNTAX

### List1 (Default)
```
Get-AzVMwarePrivateCloud [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzVMwarePrivateCloud -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVMwarePrivateCloud -InputObject <IVMwareIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzVMwarePrivateCloud -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan cloud privat

## EXAMPLES

### Contoh 1: Mencantumkan cloud privat di bawah langganan
```powershell
Get-AzVMwarePrivateCloud
```
```output
Location      Name            Type
--------      ----            ----
australiaeast azps_test_cloud Microsoft.AVS/privateClouds
```

Mencantumkan cloud privat di bawah langganan

### Contoh 2: Mencantumkan cloud privat di bawah grup sumber daya
```powershell
Get-AzVMwarePrivateCloud -ResourceGroupName azps_test_group
```
```output
Location      Name            Type                        ResourceGroupName
--------      ----            ----                        -----------------
australiaeast azps_test_cloud Microsoft.AVS/privateClouds azps_test_group
```

Mencantumkan cloud privat di bawah grup sumber daya

### Contoh 3: Mendapatkan cloud privat berdasarkan nama
```powershell
Get-AzVMwarePrivateCloud -ResourceGroupName azps_test_group -Name azps_test_cloud
```
```output
Location      Name            Type                        ResourceGroupName
--------      ----            ----                        -----------------
australiaeast azps_test_cloud Microsoft.AVS/privateClouds azps_test_group
```

Mendapatkan cloud privat berdasarkan nama

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama cloud privat

```yaml
Type: System.String
Parameter Sets: Get
Aliases: PrivateCloudName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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
ID langganan target.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.IPrivateCloud

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IVMwareIdentity>`: Parameter Identitas
  - `[AddonName <String>]`: Nama addon untuk cloud privat
  - `[AuthorizationName <String>]`: Nama Otorisasi Sirkuit ExpressRoute di cloud privat
  - `[CloudLinkName <String>]`: Nama sumber daya tautan cloud
  - `[ClusterName <String>]`: Nama kluster di cloud privat
  - `[DatastoreName <String>]`: Nama datastore di kluster cloud privat
  - `[DhcpId <String>]`: Pengidentifikasi NSX DHCP. Umumnya sama dengan nama tampilan DHCP
  - `[DnsServiceId <String>]`: Pengidentifikasi Layanan DNS NSX. Umumnya sama dengan nama tampilan Layanan DNS
  - `[DnsZoneId <String>]`: Pengidentifikasi Zona DNS NSX. Umumnya sama dengan nama tampilan Zona DNS
  - `[GatewayId <String>]`: Pengidentifikasi Gateway NSX. Umumnya sama dengan nama tampilan Gateway
  - `[GlobalReachConnectionName <String>]`: Nama koneksi jangkauan global di cloud privat
  - `[HcxEnterpriseSiteName <String>]`: Nama Situs Perusahaan HCX di cloud privat
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Wilayah Azure
  - `[PlacementPolicyName <String>]`: Nama kebijakan penempatan VMware vSphere Distributed Resource Scheduler (DRS)
  - `[PortMirroringId <String>]`: Pengidentifikasi Pencerminan Port NSX. Umumnya sama dengan nama tampilan Port Mirroring
  - `[PrivateCloudName <String>]`: Nama cloud privat
  - `[PublicIPId <String>]`: Pengidentifikasi Blok IP Publik NSX. Umumnya sama dengan nama tampilan Blok IP Publik
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ScriptCmdletName <String>]`: Nama sumber daya cmdlet skrip dalam paket skrip di cloud privat
  - `[ScriptExecutionName <String>]`: Nama sumber daya eksekusi skrip yang dipanggil pengguna
  - `[ScriptPackageName <String>]`: Nama paket skrip di cloud privat
  - `[SegmentId <String>]`: Pengidentifikasi Segmen NSX. Umumnya sama dengan nama tampilan Segment
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VMGroupId <String>]`: Pengidentifikasi NSX VM Group. Umumnya sama dengan nama tampilan Grup VM
  - `[VirtualMachineId <String>]`: Pengidentifikasi Komputer Virtual

## RELATED LINKS

