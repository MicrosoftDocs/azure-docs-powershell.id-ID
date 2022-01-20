---
external help file: ''
Module Name: Az.CustomLocation
online version: https://docs.microsoft.com/powershell/module/az.customlocation/get-azcustomlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocation.md
ms.openlocfilehash: b9f5c7d96b43de33b01ac8e33af45ca537ad8427
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136394517"
---
# Get-AzCustomLocation

## SYNOPSIS
Mendapatkan detail customLocation dengan grup dan nama sumber daya yang ditentukan.

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
Mendapatkan detail customLocation dengan grup dan nama sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1: List the details of the customLocation.
```powershell
PS C:\> Get-AzCustomLocation

Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

List the details of the customLocation.

### Contoh 2: List the details of the customLocation with a specified resource group.
```powershell
PS C:\> Get-AzCustomLocation -ResourceGroupName azps_test_group

Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

List the details of the customLocation with a specified resource group.

### Contoh 3: Mendapatkan detail lokasikasi kustom dengan nama dan grup sumber daya yang ditentukan.
```powershell
PS C:\> Get-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster

Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Mendapatkan detail customLocation dengan grup dan nama sumber daya yang ditentukan.

### Contoh 4: Gets the details of the customLocation.
```powershell
PS C:\> New-AzCustomLocation -ResourceGroupName azps_test_group -Name azps_test_cluster -Location eastus -ClusterExtensionId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster/providers/Microsoft.KubernetesConfiguration/extensions/azps_test_extension" -HostResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azps_test_group/providers/Microsoft.Kubernetes/connectedClusters/azps_test_cluster" -Namespace arc | Get-AzCustomLocation

Location Name              Namespace
-------- ----              ----
eastus   azps_test_cluster arc
```

Mendapatkan detail lokasi kustom.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity
Parameter Sets: GetViaIdentity
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
Namanya peka huruf besar/huruf.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.ICustomLocationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.Api20210815.ICustomLocation

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICustomLocationIdentity> : Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ResourceName <String>]`: Nama Lokasi Kustom.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

