---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/get-azvmwarecloudlink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwareCloudLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwareCloudLink.md
ms.openlocfilehash: 5d5de628ff79f2c227f7c6787cefd33e31d82abe
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144221447"
---
# Get-AzVMwareCloudLink

## SYNOPSIS
Mendapatkan tautan cloud berdasarkan nama di cloud privat

## SYNTAX

### Daftar (Default)
```
Get-AzVMwareCloudLink -PrivateCloudName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzVMwareCloudLink -Name <String> -PrivateCloudName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVMwareCloudLink -InputObject <IVMwareIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan tautan cloud berdasarkan nama di cloud privat

## EXAMPLES

### Contoh 1: Mencantumkan tautan cloud di bawah grup sumber daya
```powershell
Get-AzVMwareCloudLink -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group
```
```output
Name                Type                                   ResourceGroupName
----                ----                                   -----------------
azps_test_cloudlink Microsoft.AVS/privateClouds/cloudLinks azps_test_group
```

Mencantumkan tautan cloud di bawah grup sumber daya

### Contoh 2: Mendapatkan tautan cloud berdasarkan nama di cloud privat
```powershell
Get-AzVMwareCloudLink -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group -Name azps_test_cloudlink
```
```output
Name                Type                                   ResourceGroupName
----                ----                                   -----------------
azps_test_cloudlink Microsoft.AVS/privateClouds/cloudLinks azps_test_group
```

Mendapatkan tautan cloud berdasarkan nama di cloud privat

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
Nama sumber daya tautan cloud

```yaml
Type: System.String
Parameter Sets: Get
Aliases: CloudLinkName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateCloudName
Nama cloud privat

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.ICloudLink

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IVMwareIdentity>: Parameter Identitas
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
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[ScriptCmdletName <String>]`: Nama sumber daya cmdlet skrip dalam paket skrip di cloud privat
  - `[ScriptExecutionName <String>]`: Nama sumber daya eksekusi skrip yang dipanggil pengguna
  - `[ScriptPackageName <String>]`: Nama paket skrip di cloud privat
  - `[SegmentId <String>]`: Pengidentifikasi Segmen NSX. Umumnya sama dengan nama tampilan Segment
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VMGroupId <String>]`: Pengidentifikasi NSX VM Group. Umumnya sama dengan nama tampilan Grup VM
  - `[VirtualMachineId <String>]`: Pengidentifikasi Komputer Virtual

## RELATED LINKS

