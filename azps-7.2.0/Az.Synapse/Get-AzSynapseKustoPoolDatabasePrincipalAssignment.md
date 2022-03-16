---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopooldatabaseprincipalassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabasePrincipalAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabasePrincipalAssignment.md
ms.openlocfilehash: b3297b5e90dbaf737e170d50dc478679dd8d6774
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140047577"
---
# Get-AzSynapseKustoPoolDatabasePrincipalAssignment

## SYNOPSIS
Mendapatkan prinsipal database kusto poolAssignment.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.synapse/get-azsynapsekustopooldatabaseprincipalassignment) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -DatabaseName <String> -KustoPoolName <String>
 -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -DatabaseName <String> -KustoPoolName <String>
 -PrincipalAssignmentName <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -InputObject <ISynapseIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan prinsipal database kusto poolAssignment.

## EXAMPLES

### Contoh 1: List all PrincipalAssignments in a kusto database by name
```powershell
PS C:\> Get-AzSynapseKustoPoolDatabasePrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase

Name                                                  Type
----                                                  ----
testws/testkustopool/mykustodatabase/kustoprincipal1  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
testws/testkustopool/mykustodatabase/kustoprincipal2  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
```

Perintah di atas mengembalikan semua PrincipalAssignments dalam database kusto "mykustodatabase" dalam WorkspaceName "testws" yang ditemukan di grup sumber daya "testrg".

### Contoh 2: Dapatkan PrincipalAssignment tertentu dalam database kusto menurut nama
```powershell
PS C:\>  Get-AzSynapseKustoPoolDatabasePrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase -PrincipalAssignmentName kustoprincipal1

Name                                                  Type
----                                                  ----
testws/testkustopool/mykustodatabase/kustoprincipal1  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
```

Perintah di atas mengembalikan PrincipalAssignment bernama "kustoprincipal1" dalam database kusto "mykustodatabase" di WorkspaceName "testws" yang ditemukan di grup sumber daya "testrg".

## PARAMETERS

### -DatabaseName
Nama database di dalam kolam Kusto.

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
Nama pool Kusto.

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
Nama principalAssignment Kusto.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.ISynapseIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IDatabasePrincipalAssignment

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ISynapseIdentity>: Parameter Identitas
  - `[AttachedDatabaseConfigurationName <String>]`: Nama konfigurasi database yang dilampirkan.
  - `[DataConnectionName <String>]`: Nama koneksi data.
  - `[DatabaseName <String>]`: Nama database di kolam Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KustoPoolName <String>]`: Nama kolam Kusto.
  - `[Location <String>]`: Nama kawasan Azure.
  - `[PrincipalAssignmentName <String>]`: Nama principalAssignment Kusto.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja

## RELATED LINKS

