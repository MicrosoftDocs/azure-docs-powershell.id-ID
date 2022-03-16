---
external help file: ''
Module Name: Az.CustomLocation
online version: https://docs.microsoft.com/powershell/module/az.customlocation/update-azcustomlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Update-AzCustomLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Update-AzCustomLocation.md
ms.openlocfilehash: 135f62e8c72b22b62d38f347c3189a5d25d93195
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140209485"
---
# Update-AzCustomLocation

## SYNOPSIS
Memperbarui Lokasi Kustom dengan Nama Sumber Daya yang ditentukan dalam Grup Sumber Daya dan Langganan yang ditentukan.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzCustomLocation -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AuthenticationType <String>] [-AuthenticationValue <String>] [-ClusterExtensionId <String[]>]
 [-DisplayName <String>] [-HostResourceId <String>] [-IdentityType <ResourceIdentityType>]
 [-Namespace <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzCustomLocation -InputObject <ICustomLocationIdentity> [-AuthenticationType <String>]
 [-AuthenticationValue <String>] [-ClusterExtensionId <String[]>] [-DisplayName <String>]
 [-HostResourceId <String>] [-IdentityType <ResourceIdentityType>] [-Namespace <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Lokasi Kustom dengan Nama Sumber Daya yang ditentukan dalam Grup Sumber Daya dan Langganan yang ditentukan.

## EXAMPLES

### Contoh 1: Memperbarui Lokasi Kustom dengan Nama Sumber Daya yang ditentukan dalam Grup Sumber Daya dan Langganan yang ditentukan.
```powershell
PS C:\> Update-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster_1 -ClusterExtensionId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster/providers/Microsoft.KubernetesConfiguration/extensions/azps_test_extension" -HostResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster" -Namespace arc

Location Name                Namespace
-------- ----                ----
eastus   azps_test_cluster_1 arc
```

Memperbarui Lokasi Kustom dengan Nama Sumber Daya yang ditentukan dalam Grup Sumber Daya dan Langganan yang ditentukan.

### Contoh 2: Memperbarui Lokasi Kustom.
```powershell
PS C:\> Get-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster | Update-AzCustomLocation

Location Name                Namespace
-------- ----                ----
eastus   azps_test_cluster_1 arc
```

Memperbarui Lokasi Kustom.

## PARAMETERS

### -AuthenticationType
Tipe autentikasi Lokasi Kustom

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

### -AuthenticationValue
Nilai kubeconfig.

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

### -ClusterExtensionId
Berisi referensi ke add-on yang berisi bagan untuk menggunakan CRD dan operator.

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

### -DisplayName
Nama tampilan untuk lokasi Lokasi Kustom.

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

### -HostResourceId
Kluster Tersambung atau Kluster AKS.
Lokasi Kustom RP akan melakukan API checkAccess untuk izin listAdminCredentials.

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

### -IdentityType
Tipe identitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Support.ResourceIdentityType
Parameter Sets: (All)
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
Type: Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Lokasi Kustom.

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

### -Namespace
Ruang nama ruang layanan yang akan dibuat pada kluster yang ditentukan.

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.Api20210815.ICustomLocation

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICustomLocationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ResourceName <String>]`: Nama Lokasi Kustom.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

