---
external help file: ''
Module Name: Az.CustomLocation
online version: https://docs.microsoft.com/powershell/module/az.customlocation/get-azcustomlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocation.md
ms.openlocfilehash: a4b53e99f574e84251f78dac1d3b05780eeeed66
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205367"
---
# Get-AzCustomLocation

## SYNOPSIS
Mendapatkan detail customLocation dengan grup sumber daya dan nama tertentu.

## SYNTAX

### Daftar (Default)
```
Get-AzCustomLocation [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzCustomLocation -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCustomLocation -InputObject <ICustomLocationIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzCustomLocation -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail customLocation dengan grup sumber daya dan nama tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan detail customLocation.
```powershell
Get-AzCustomLocation
```

```output
Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Mencantumkan detail customLocation.

### Contoh 2: Mencantumkan detail customLocation dengan grup sumber daya tertentu.
```powershell
Get-AzCustomLocation -ResourceGroupName azps_test_group
```

```output
Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Cantumkan detail customLocation dengan grup sumber daya tertentu.

### Contoh 3: Mendapatkan detail customLocation dengan grup dan nama sumber daya tertentu.
```powershell
Get-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster
```

```output
Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Mendapatkan detail customLocation dengan grup sumber daya dan nama tertentu.

### Contoh 4: Mendapatkan detail customLocation.
```powershell
New-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster -Location eastus -ClusterExtensionId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster/providers/Microsoft.KubernetesConfiguration/extensions/azps_test_extension" -HostResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster" -Namespace arc | Get-AzCustomLocation
```

```output
Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Mendapatkan detail customLocation.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Lokasi Kustom.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.Api20210815.ICustomLocation

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICustomLocationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama Lokasi Kustom.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

