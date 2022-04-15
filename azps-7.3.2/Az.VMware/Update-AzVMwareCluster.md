---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/update-azvmwarecluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Update-AzVMwareCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Update-AzVMwareCluster.md
ms.openlocfilehash: 4e403dfb09840f7a3c13ca913f79337a72e8d2e7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142394999"
---
# Update-AzVMwareCluster

## SYNOPSIS
Memperbarui kluster di awan privat

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.vmware/update-azvmwarecluster) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzVMwareCluster -Name <String> -PrivateCloudName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-ClusterSize <Int32>] [-PropertiesHost <String[]>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzVMwareCluster -InputObject <IVMwareIdentity> [-ClusterSize <Int32>] [-PropertiesHost <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui kluster di awan privat

## EXAMPLES

### Contoh 1: Memperbarui ukuran kluster menurut nama
```powershell
PS C:\> Update-AzVMwareCluster -Name azps_test_cluster -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group -ClusterSize 4

Name              Type                                 ResourceGroupName
----              ----                                 -----------------
azps_test_cluster Microsoft.AVS/privateClouds/clusters azps_test_group
```

Memperbarui ukuran kluster menurut nama

### Contoh 2: Memperbarui ukuran kluster
```powershell
PS C:\> Get-AzVMwareCluster -Name azps_test_cluster -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group | Update-AzVMwareCluster -ClusterSize 4

Name              Type                                 ResourceGroupName
----              ----                                 -----------------
azps_test_cluster Microsoft.AVS/privateClouds/clusters azps_test_group
```

Perbarui ukuran kluster

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Clustersize
Ukuran kluster

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kluster di awan pribadi

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ClusterName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateCloudName
Nama awan pribadi

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertiesHost
Tuan rumah

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: UpdateExpanded
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
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.ICluster

## CATATAN

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

