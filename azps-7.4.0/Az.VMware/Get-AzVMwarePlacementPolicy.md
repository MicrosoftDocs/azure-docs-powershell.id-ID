---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/get-azvmwareplacementpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwarePlacementPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwarePlacementPolicy.md
ms.openlocfilehash: dd115d2bc0889fe8e512ee397c32284c5f363bc8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142669258"
---
# Get-AzVMwarePlacementPolicy

## SYNOPSIS
Dapatkan kebijakan penempatan berdasarkan nama di kluster cloud privat

## SYNTAX

### Daftar (Default)
```
Get-AzVMwarePlacementPolicy -ClusterName <String> -PrivateCloudName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzVMwarePlacementPolicy -ClusterName <String> -Name <String> -PrivateCloudName <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVMwarePlacementPolicy -InputObject <IVMwareIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan kebijakan penempatan berdasarkan nama di kluster cloud privat

## EXAMPLES

### Contoh 1: Kebijakan penempatan daftar menurut kluster cloud privat
```powershell
Get-AzVMwarePlacementPolicy -ClusterName cluster1 -PrivateCloudName cloud1 -ResourceGroupName group1
```
```output
Name    ResourceGroupName
----    -----------------
policy1 group1
policy2 group1
```

Kebijakan penempatan daftar menurut kluster cloud privat

### Contoh 2: Dapatkan kebijakan penempatan menurut nama di kluster cloud privat
```powershell
Get-AzVMwarePlacementPolicy -ClusterName cluster1 -Name policy1 -PrivateCloudName cloud1 -ResourceGroupName group1
```
```output
Name    ResourceGroupName
----    -----------------
policy1 group1
```

Dapatkan kebijakan penempatan berdasarkan nama di kluster cloud privat

## PARAMETERS

### -ClusterName
Nama kluster di awan pribadi

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
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kebijakan penempatan VMware vSphere Distributed Resource Scheduler (DRS)

```yaml
Type: System.String
Parameter Sets: Get
Aliases: PlacementPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateCloudName
Nama awan pribadi

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
Nama ini tidak peka huruf besar kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.IPlacementPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IVMwareIdentity>: Parameter Identitas
  - `[AddonName <String>]`: Nama add-on untuk awan pribadi
  - `[AuthorizationName <String>]`: Nama Otorisasi Sirkuit ExpressRoute di awan pribadi
  - `[CloudLinkName <String>]`: Nama sumber daya tautan awan
  - `[ClusterName <String>]`: Nama kluster di cloud pribadi
  - `[DatastoreName <String>]`: Nama datastore di kluster cloud privat
  - `[DhcpId <String>]`: Pengidentifikasi DHCP NSX. Umumnya sama dengan nama tampilan DHCP
  - `[DnsServiceId <String>]`: Pengidentifikasi Layanan DNS NSX. Umumnya sama dengan nama tampilan Layanan DNS
  - `[DnsZoneId <String>]`: Pengidentifikasi Zona DNS NSX. Umumnya sama dengan nama tampilan Zona DNS
  - `[GatewayId <String>]`: Pengidentifikasi Gateway NSX. Umumnya sama dengan nama tampilan Gateway
  - `[GlobalReachConnectionName <String>]`: Nama koneksi jangkauan global di awan pribadi
  - `[HcxEnterpriseSiteName <String>]`: Nama Situs HCX Enterprise di awan pribadi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Kawasan Azure
  - `[PlacementPolicyName <String>]`: Nama kebijakan penempatan VMware vSphere Distributed Resource Scheduler (DRS)
  - `[PortMirroringId <String>]`: Pengidentifikasi Pencerminan Port NSX. Umumnya sama dengan nama tampilan Port Mirroring
  - `[PrivateCloudName <String>]`: Nama awan pribadi
  - `[PublicIPId <String>]`: Pengidentifikasi Blok IP Publik NSX. Umumnya sama dengan nama tampilan Blok IP Publik
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[ScriptCmdletName <String>]`: Nama sumber daya cmdlet skrip dalam paket skrip di awan pribadi
  - `[ScriptExecutionName <String>]`: Nama sumber eksekusi skrip yang diminta pengguna
  - `[ScriptPackageName <String>]`: Nama paket skrip di awan pribadi
  - `[SegmentId <String>]`: Pengidentifikasi Segmen NSX. Umumnya sama dengan nama tampilan Segmen
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VMGroupId <String>]`: Pengidentifikasi Grup VM NSX. Umumnya sama dengan nama tampilan Grup VM
  - `[VirtualMachineId <String>]`: Pengidentifikasi Mesin Virtual

## RELATED LINKS

