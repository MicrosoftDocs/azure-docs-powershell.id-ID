---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/new-azvmwareprivatecloudvcenterpassword
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePrivateCloudVcenterPassword.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePrivateCloudVcenterPassword.md
ms.openlocfilehash: 2b56e0d7f8cfdabb47c9af11840b056f18bf585b
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146594725"
---
# New-AzVMwarePrivateCloudVcenterPassword

## SYNOPSIS
Memutar kata sandi vCenter Server

## SYNTAX

### Putar (Default)
```
New-AzVMwarePrivateCloudVcenterPassword -PrivateCloudName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### RotateViaIdentity
```
New-AzVMwarePrivateCloudVcenterPassword -InputObject <IVMwareIdentity> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memutar kata sandi vCenter Server

## EXAMPLES

### Contoh 1: Memutar kata sandi vCenter Server
```powershell
New-AzVMwarePrivateCloudVcenterPassword -ResourceGroupName azps_test_group -PrivateCloudName azps_test_cloud -PassThru
```
```output
True
```

Memutar kata sandi vCenter Server

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Parameter Sets: RotateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -PassThru
Mengembalikan true saat perintah berhasil

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
Nama cloud privat

```yaml
Type: System.String
Parameter Sets: Rotate
Aliases:

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
Parameter Sets: Rotate
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
Parameter Sets: Rotate
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### System.Boolean

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

