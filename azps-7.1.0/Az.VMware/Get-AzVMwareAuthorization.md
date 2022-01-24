---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.vmware/get-azvmwareauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwareAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/Get-AzVMwareAuthorization.md
ms.openlocfilehash: 20896cac72020637426d63ae0ddbfde7ecf7fca4
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136698882"
---
# Get-AzVMwareAuthorization

## SYNOPSIS
Dapatkan Otorisasi Sirkuit ExpressRoute berdasarkan nama di cloud pribadi

## SYNTAX

### Daftar (Default)
```
Get-AzVMwareAuthorization -PrivateCloudName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzVMwareAuthorization -Name <String> -PrivateCloudName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVMwareAuthorization -InputObject <IVMwareIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Otorisasi Sirkuit ExpressRoute berdasarkan nama di cloud pribadi

## EXAMPLES

### Contoh 1: Otorisasi daftar di bawah grup sumber daya
```powershell
PS C:\> Get-AzVMwareAuthorization -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group

Name                    Type                                       ResourceGroupName
----                    ----                                       -----------------
azps_test_authorization Microsoft.AVS/privateClouds/authorizations azps_test_group
```

Otorisasi daftar di bawah grup sumber daya

### Contoh 2: Dapatkan otorisasi menurut nama di awan pribadi
```powershell
PS C:\> Get-AzVMwareAuthorization -PrivateCloudName azps_test_cloud -ResourceGroupName azps_test_group -Name azps_test_authorization

Name                    Type                                       ResourceGroupName
----                    ----                                       -----------------
azps_test_authorization Microsoft.AVS/privateClouds/authorizations azps_test_group
```

Dapatkan otorisasi berdasarkan nama di awan pribadi

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
Nama Otorisasi Sirkuit ExpressRoute di awan pribadi

```yaml
Type: System.String
Parameter Sets: Get
Aliases: AuthorizationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateCloudName
Nama awan privat

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
Namanya peka huruf besar/huruf.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.IVMwareIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.IExpressRouteAuthorization

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IVMwareIdentity> : Parameter Identitas
  - `[AddonName <String>]`: Nama add-on untuk awan privat
  - `[AuthorizationName <String>]`: Nama Otorisasi Sirkuit ExpressRoute di awan pribadi
  - `[CloudLinkName <String>]`: Nama sumber daya tautan awan
  - `[ClusterName <String>]`: Nama kluster di awan privat
  - `[DatastoreName <String>]`: Nama datastore dalam kluster awan privat
  - `[DhcpId <String>]`: Pengidentifikasi DHCP NSX. Secara umum sama seperti nama tampilan DHCP
  - `[DnsServiceId <String>]`: Pengidentifikasi Layanan DNS NSX. Secara umum sama seperti nama tampilan Layanan DNS
  - `[DnsZoneId <String>]`: Pengidentifikasi Zona DNS NSX. Secara umum sama seperti nama tampilan Zona DNS
  - `[GatewayId <String>]`: Pengidentifikasi Gateway NSX. Secara umum sama seperti nama tampilan Gateway
  - `[GlobalReachConnectionName <String>]`: Nama koneksi jangkauan global di awan privat
  - `[HcxEnterpriseSiteName <String>]`: Nama Situs ENTERPRISE PORTALX di awan pribadi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Azure kawasan
  - `[PortMirroringId <String>]`: Pengidentifikasi Pencerminan Port NSX. Biasanya sama seperti nama tampilan Pencerminan Port
  - `[PrivateCloudName <String>]`: Nama awan privat
  - `[PublicIPId <String>]`: Pengidentifikasi Blokir IP Publik NSX. Secara umum sama seperti nama tampilan Blok IP Publik
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ScriptCmdletName <String>]`: Nama sumber daya cmdlet skrip dalam paket skrip di awan privat
  - `[ScriptExecutionName <String>]`: Nama sumber daya eksekusi skrip yang diminta pengguna
  - `[ScriptPackageName <String>]`: Nama paket skrip di awan privat
  - `[SegmentId <String>]`: Pengidentifikasi Segmen NSX. Biasanya sama seperti nama tampilan Segmen
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VMGroupId <String>]`: Pengidentifikasi NSX VM Group. Biasanya sama seperti nama tampilan VM Group
  - `[VirtualMachineId <String>]`: Pengidentifikasi Mesin Virtual

## RELATED LINKS

