---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopoolprincipalassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolPrincipalAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolPrincipalAssignment.md
ms.openlocfilehash: c9cb369720b9fae56a774afeb0a79ca8f76bc213
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146635456"
---
# Get-AzSynapseKustoPoolPrincipalAssignment

## SYNOPSIS
Mendapatkan Kusto pool principalAssignment.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsekustopoolprincipalassignment) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolPrincipalAssignment -KustoPoolName <String> -ResourceGroupName <String>
 -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzSynapseKustoPoolPrincipalAssignment -KustoPoolName <String> -PrincipalAssignmentName <String>
 -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSynapseKustoPoolPrincipalAssignment -InputObject <ISynapseIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Kusto pool principalAssignment.

## EXAMPLES

### Contoh 1: Mencantumkan semua Kusto principalAssignments
```powershell
Get-AzSynapseKustoPoolPrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool
```

```output
Name                                 Type
----                                 ----
testws/testkustopool/kustoprincipal1 Microsoft.Synapse/workspaces/kustoPools/PrincipalAssignments
```

Perintah di atas mencantumkan semua principalAssignments di ruang kerja "testws".

### Contoh 2: Mendapatkan Kusto principalAssignment berdasarkan nama
```powershell
Get-AzSynapseKustoPoolPrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -PrincipalAssignmentName kustoprincipal1
```

```output
Name                                 Type
----                                 ----
testws/testkustopool/kustoprincipal1 Microsoft.Synapse/workspaces/kustoPools/PrincipalAssignments
```

Perintah di atas mengembalikan Kusto principalAssignment bernama "kustoprincipal1" di ruang kerja "testws".

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.ISynapseIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KustoPoolName
Nama kumpulan Kusto.

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

### -PrincipalAssignmentName
Nama Kusto principalAssignment.

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
Nama tidak peka huruf besar/kecil.

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

### -WorkspaceName
Nama ruang kerja

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.ISynapseIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IClusterPrincipalAssignment

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<ISynapseIdentity>`: Parameter Identitas
  - `[AttachedDatabaseConfigurationName <String>]`: Nama konfigurasi database terlampir.
  - `[DataConnectionName <String>]`: Nama koneksi data.
  - `[DatabaseName <String>]`: Nama database di kumpulan Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KustoPoolName <String>]`: Nama kumpulan Kusto.
  - `[Location <String>]`: Nama wilayah Azure.
  - `[PrincipalAssignmentName <String>]`: Nama Kusto principalAssignment.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja

## RELATED LINKS

