---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopooldatabaseprincipalassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabasePrincipalAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabasePrincipalAssignment.md
ms.openlocfilehash: 000baf8b8a6bc0a9abf2461174f8827a4adce857
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434958"
---
# Get-AzSynapseKustoPoolDatabasePrincipalAssignment

## SYNOPSIS
Mendapatkan Kusto prinsipal database poolAssignment.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -DatabaseName <String> -KustoPoolName <String>
 -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Mendapatkan
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
Mendapatkan Kusto prinsipal database poolAssignment.

## EXAMPLES

### Contoh 1: Mencantumkan semua Penetapan Prinsipal dalam database kusto menurut nama
```powershell
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase
```

```output
Name                                                  Type
----                                                  ----
testws/testkustopool/mykustodatabase/kustoprincipal1  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
testws/testkustopool/mykustodatabase/kustoprincipal2  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
```

Perintah di atas mengembalikan semua PrincipalAssignments dalam database kusto "mykustodatabase" dalam WorkspaceName "testws" yang ditemukan dalam grup sumber daya "testrg".

### Contoh 2: Dapatkan PrincipalAssignment tertentu dalam database kusto menurut nama
```powershell
Get-AzSynapseKustoPoolDatabasePrincipalAssignment -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase -PrincipalAssignmentName kustoprincipal1
```

```output
Name                                                  Type
----                                                  ----
testws/testkustopool/mykustodatabase/kustoprincipal1  Microsoft.Synapse/workspaces/kustoPools/Databases/PrincipalAssignments
```

Perintah di atas mengembalikan PrincipalAssignment bernama "kustoprincipal1" dalam database kusto "mykustodatabase" dalam WorkspaceName "testws" yang ditemukan dalam grup sumber daya "testrg".

## PARAMETERS

### -DatabaseName
Nama database dalam kumpulan Kusto.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Nama ini tidak peka huruf besar kecil.

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
  - `[DatabaseName <String>]`: Nama database dalam kumpulan Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KustoPoolName <String>]`: Nama kumpulan Kusto.
  - `[Location <String>]`: Nama kawasan Azure.
  - `[PrincipalAssignmentName <String>]`: Nama Kusto principalAssignment.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja

## RELATED LINKS

