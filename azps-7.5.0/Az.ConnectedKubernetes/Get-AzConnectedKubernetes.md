---
external help file: ''
Module Name: Az.ConnectedKubernetes
online version: https://docs.microsoft.com/powershell/module/az.connectedkubernetes/get-azconnectedkubernetes
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetes.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetes.md
ms.openlocfilehash: c8f3a6b3771a2c61c2a2d5256a1077da3ed7111f
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145797686"
---
# Get-AzConnectedKubernetes

## SYNOPSIS
Mengembalikan properti kluster terhubung yang ditentukan, termasuk nama, identitas, properti, dan detail kluster tambahan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.connectedkubernetes/get-azconnectedkubernetes) untuk informasi terbaru.

## SYNTAX

### List1 (Default)
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
Mengembalikan properti kluster terhubung yang ditentukan, termasuk nama, identitas, properti, dan detail kluster tambahan.

## EXAMPLES

### Contoh 1: Dapatkan semua kubernetes yang terhubung di bawah langganan
```powershell
Get-AzConnectedKubernetes
```

```output
Location Name               ResourceGroupName
-------- ----               -----------------
eastus   azps_test_cluster  azps_test_group
eastus   azps_test_cluster1 azps_test_group
eastus   azps_test_cluster2 azps_test_group
```

Perintah ini mendapatkan semua kubernetes yang terhubung di bawah langganan.

### Contoh 2: Dapatkan semua kubernetes yang terhubung di bawah grup sumber daya
```powershell
Get-AzConnectedKubernetes -ResourceGroupName azps_test_group
```

```output
Location Name               ResourceGroupName
-------- ----               -----------------
eastus   azps_test_cluster  azps_test_group
eastus   azps_test_cluster1 azps_test_group
eastus   azps_test_cluster2 azps_test_group
```

Perintah ini mendapatkan semua kubernetes yang terhubung di bawah grup sumber daya.

### Contoh 3: Dapatkan kubernetes yang terhubung
```powershell
Get-AzConnectedKubernetes -ResourceGroupName azps_test_group -Name azps_test_cluster
```

```output
Location Name              ResourceGroupName
-------- ----              -----------------
eastus   azps_test_cluster azps_test_group
```

Perintah ini mendapatkan kubernetes yang terhubung.

### Contoh 4: Dapatkan kubernetes yang terhubung berdasarkan objek
```powershell
$conAks = Get-AzConnectedKubernetes -ClusterName azps_test_cluster -ResourceGroupName azps_test_group
Get-AzConnectedKubernetes -InputObject $conAks
```

```output
Location Name              ResourceGroupName
-------- ----              -----------------
eastus   azps_test_cluster azps_test_group
```

Perintah ini mendapatkan kubernetes yang terhubung berdasarkan objek.

## PARAMETERS

### -ClusterName
Nama kluster Kubernetes tempat dipanggil.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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
Nama ini tidak peka huruf besar/kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.IConnectedKubernetesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.Api20211001.IConnectedCluster

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedKubernetesIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster Kubernetes tempat dipanggil.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

