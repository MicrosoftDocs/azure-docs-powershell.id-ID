---
external help file: ''
Module Name: Az.ConnectedKubernetes
online version: https://docs.microsoft.com/powershell/module/az.connectedkubernetes/get-azconnectedkubernetes
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetes.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetes.md
ms.openlocfilehash: c9b66f6d6b5fc3456a84017b1fd08ce62997b606
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138297947"
---
# Get-AzConnectedKubernetes

## SYNOPSIS
Mengembalikan properti kluster tersambung yang ditentukan, termasuk nama, identitas, properti, dan detail kluster tambahan.

## SYNTAX

### Daftar1 (Default)
```
Get-AzConnectedKubernetes [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedKubernetes -ClusterName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzConnectedKubernetes -InputObject <IConnectedKubernetesIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzConnectedKubernetes -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan properti kluster tersambung yang ditentukan, termasuk nama, identitas, properti, dan detail kluster tambahan.

## EXAMPLES

### Contoh 1: Get all connected k msdns under a subscription
```powershell
PS C:\> Get-AzConnectedKubernetes

Location Name               ResourceGroupName
-------- ----               -----------------
eastus   azps_test_cluster  azps_test_group
eastus   azps_test_cluster1 azps_test_group
eastus   azps_test_cluster2 azps_test_group
```

Perintah ini akan menghubungkan semua grup di bawah langganan.

### Contoh 2: Get all connected ks under the resource group
```powershell
PS C:\> Get-AzConnectedKubernetes -ResourceGroupName azps_test_group

Location Name               ResourceGroupName
-------- ----               -----------------
eastus   azps_test_cluster  azps_test_group
eastus   azps_test_cluster1 azps_test_group
eastus   azps_test_cluster2 azps_test_group
```

Perintah ini menghubungkan semua kontak yang terhubung di bawah grup sumber daya.

### Contoh 3: Get a connected kjadwals
```powershell
PS C:\> Get-AzConnectedKubernetes -ResourceGroupName azps_test_group -Name azps_test_cluster

Location Name              ResourceGroupName
-------- ----              -----------------
eastus   azps_test_cluster azps_test_group
```

Perintah ini memiliki hubungan yang terkoneksi.

### Contoh 4: Get a connected ks by object
```powershell
PS C:\> $conAks = Get-AzConnectedKubernetes -ClusterName azps_test_cluster -ResourceGroupName azps_test_group -Location eastus
PS C:\> Get-AzConnectedKubernetes -InputObject $conAks

Location Name              ResourceGroupName
-------- ----              -----------------
eastus   azps_test_cluster azps_test_group
```

Perintah ini terhubung dengan objek.

## PARAMETERS

### -ClusterName
Nama kluster Kluster tempat get disebut.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.IConnectedKubernetesIdentity
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
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedK cmdlets.Models.IConnectedK cmdletsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedK cmdlets.Models.Api20211001.IConnectedCluster

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedKubernetesIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster Kluster Kedaering yang disebut dengan get.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

