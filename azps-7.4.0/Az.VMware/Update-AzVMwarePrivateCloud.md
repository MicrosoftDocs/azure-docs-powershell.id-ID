---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/update-azvmwareprivatecloud
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Update-AzVMwarePrivateCloud.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Update-AzVMwarePrivateCloud.md
ms.openlocfilehash: 954e9e7769f5d6bf23d46ef8f818574a0b9f9e2b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142419256"
---
# Update-AzVMwarePrivateCloud

## SYNOPSIS
Memperbarui awan pribadi

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzVMwarePrivateCloud -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AvailabilitySecondaryZone <Int32>] [-AvailabilityStrategy <AvailabilityStrategy>]
 [-AvailabilityZone <Int32>] [-EncryptionStatus <EncryptionState>] [-IdentitySource <IIdentitySource[]>]
 [-IdentityType <ResourceIdentityType>] [-Internet <InternetEnum>] [-KeyVaultPropertyKeyName <String>]
 [-KeyVaultPropertyKeyVaultUrl <String>] [-KeyVaultPropertyKeyVersion <String>]
 [-ManagementClusterHost <String[]>] [-ManagementClusterSize <Int32>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzVMwarePrivateCloud -InputObject <IVMwareIdentity> [-AvailabilitySecondaryZone <Int32>]
 [-AvailabilityStrategy <AvailabilityStrategy>] [-AvailabilityZone <Int32>]
 [-EncryptionStatus <EncryptionState>] [-IdentitySource <IIdentitySource[]>]
 [-IdentityType <ResourceIdentityType>] [-Internet <InternetEnum>] [-KeyVaultPropertyKeyName <String>]
 [-KeyVaultPropertyKeyVaultUrl <String>] [-KeyVaultPropertyKeyVersion <String>]
 [-ManagementClusterHost <String[]>] [-ManagementClusterSize <Int32>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui awan pribadi

## EXAMPLES

### Contoh 1: Memperbarui ukuran awan privat menurut nama
```powershell
Update-AzVMwarePrivateCloud -Name azps_test_cloud -ResourceGroupName azps_test_group -ManagementClusterSize 4
```
```output
Location      Name            Type                        ResourceGroupName
--------      ----            ----                        -----------------
australiaeast azps_test_cloud Microsoft.AVS/privateClouds azps_test_group
```

Memperbarui ukuran awan privat menurut nama

### Contoh 2: Memperbarui ukuran cloud pribadi
```powershell
Get-AzVMwarePrivateCloud -ResourceGroupName azps_test_group -Name azps_test_cloud | Update-AzVMwarePrivateCloud -ManagementClusterSize 4
```
```output
Location      Name            Type                        ResourceGroupName
--------      ----            ----                        -----------------
australiaeast azps_test_cloud Microsoft.AVS/privateClouds azps_test_group
```

Perbarui ukuran awan pribadi

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

### -AvailabilitySecondaryZone
Zona ketersediaan sekunder untuk awan pribadi

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

### -AvailabilityStrategy
Strategi ketersediaan untuk cloud pribadi

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.AvailabilityStrategy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailabilityZone
Zona ketersediaan utama untuk awan pribadi

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

### -EncryptionStatus
Status kunci enkripsi yang dikelola pelanggan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.EncryptionState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentitySource
vCenter Single Sign On Identity Sources To construct, see NOTES section for IDENTITYSOURCE properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.IIdentitySource[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Tipe identitas yang digunakan untuk awan pribadi.
Tipe 'SystemAssigned' merujuk pada identitas yang dibuat secara implisit.
Tipe 'Tidak Ada' akan menghapus identitas apa pun dari Awan Pribadi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.ResourceIdentityType
Parameter Sets: (All)
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
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Internet
Konektivitas ke internet diaktifkan atau dinonaktifkan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.InternetEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultPropertyKeyName
Nama kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultPropertyKeyVaultUrl
URL kubah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultPropertyKeyVersion
Versi kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementClusterHost
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

### -ManagementClusterSize
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

### -Nama
Nama awan pribadi

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: PrivateCloudName

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

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.IPrivateCloud

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


IDENTITYSOURCE <IIdentitySource[]>: vCenter Single Sign On Identity Sources
  - `[Alias <String>]`: Nama NetBIOS domain
  - `[BaseGroupDn <String>]`: Nama dasar yang dibedakan untuk grup
  - `[BaseUserDn <String>]`: Nama dasar yang dibedakan untuk pengguna
  - `[Domain <String>]`: Nama dns domain
  - `[Name <String>]`: Nama sumber identitas
  - `[Password <String>]`: Kata sandi pengguna Direktori Aktif dengan minimal akses baca-saja ke DN Dasar untuk pengguna dan grup.
  - `[PrimaryServer <String>]`: URL server utama
  - `[SecondaryServer <String>]`: URL server sekunder
  - `[Ssl <SslEnum?>]`: Melindungi komunikasi LDAP menggunakan sertifikat SSL (LDAPS)
  - `[Username <String>]`: ID pengguna Direktori Aktif dengan minimal akses baca-saja ke DN Dasar untuk pengguna dan grup

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

