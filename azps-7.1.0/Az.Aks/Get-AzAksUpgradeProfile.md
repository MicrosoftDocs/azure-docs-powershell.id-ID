---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/get-azaksupgradeprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksUpgradeProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksUpgradeProfile.md
ms.openlocfilehash: 1fa1721c74960695e5b429d2b80aa4253e31440f
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136745925"
---
# Get-AzAksUpgradeProfile

## SYNOPSIS
Mendapatkan detail profil pemutakhiran untuk kluster terkelola dengan grup dan nama sumber daya yang ditentukan.

## SYNTAX

### Dapatkan (Default)
```
Get-AzAksUpgradeProfile -ClusterName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzAksUpgradeProfile -InputObject <IAksIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail profil pemutakhiran untuk kluster terkelola dengan grup dan nama sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan profil pemutakhiran Aks dengan nama grup sumber daya dan nama kluster
```powershell
PS C:\> Get-AzAksUpgradeProfile -ResourceGroupName group -Name myCluster

Name    Type
----    ----
default Microsoft.ContainerService/managedClusters/upgradeprofiles
```

Dapatkan profil pemutakhiran Aks dengan nama grup sumber daya dan nama kluster.

## PARAMETERS

### -ClusterName
Nama sumber daya kluster yang dikelola.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: Name

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.IAksIdentity
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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.IAksIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.Api20200901.IManagedClusterUpgradeProfile

## CATATAN

ALIAS

Get-AzAksClusterUpgradeProfile

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAksIdentity> : Parameter Identitas
  - `[AgentPoolName <String>]`: Nama agen kolam renang.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure yang didukung.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ResourceName <String>]`: Nama sumber daya kluster terkelola.
  - `[RoleName <String>]`: Nama peran untuk sumber daya accessProfile kluster terkelola.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

