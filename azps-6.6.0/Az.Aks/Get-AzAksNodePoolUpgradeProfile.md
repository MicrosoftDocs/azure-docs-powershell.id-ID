---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/get-azaksnodepoolupgradeprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksNodePoolUpgradeProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksNodePoolUpgradeProfile.md
ms.openlocfilehash: 5ab96e2749c4abd283db741dd3d8da1228312a64
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136337787"
---
# Get-AzAksNodePoolUpgradeProfile

## SYNOPSIS
Mendapatkan detail profil pemutakhiran untuk kelompok agen dengan grup sumber daya tertentu dan nama kluster yang dikelola.

## SYNTAX

### Dapatkan (Default)
```
Get-AzAksNodePoolUpgradeProfile -AgentPoolName <String> -ClusterName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzAksNodePoolUpgradeProfile -InputObject <IAksIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail profil pemutakhiran untuk kelompok agen dengan grup sumber daya tertentu dan nama kluster yang dikelola.

## EXAMPLES

### Contoh 1: Dapatkan profil pemutakhiran kumpulan node Aks dengan nama grup sumber daya dan nama kluster
```powershell
PS C:\> Get-AzAksNodePoolUpgradeProfile -ResourceGroupName group -ClusterName myCluster -AgentPoolName default

Name    Type
----    ----
default Microsoft.ContainerService/managedClusters/agentPools/upgradeProfiles
```

Dapatkan profil pemutakhiran kumpulan node Aks dengan nama grup sumber daya dan nama kluster.

## PARAMETERS

### -AgentPoolName
Nama agen kolam renang.

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

### -ClusterName
Nama sumber daya kluster yang dikelola.

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

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.Api20200901.IAgentPoolUpgradeProfile

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAksIdentity> : Parameter Identitas
  - `[AgentPoolName <String>]`: Nama agen kolam renang.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ResourceName <String>]`: Nama sumber daya kluster terkelola.
  - `[RoleName <String>]`: Nama peran untuk sumber daya accessProfile kluster terkelola.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

