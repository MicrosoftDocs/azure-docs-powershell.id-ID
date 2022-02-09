---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopooldatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDatabase.md
ms.openlocfilehash: 94523042d14f8ccf1175604465ab80214289a43a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138277531"
---
# Get-AzSynapseKustoPoolDatabase

## SYNOPSIS
Mengembalikan sebuah database.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolDatabase -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzSynapseKustoPoolDatabase -DatabaseName <String> -KustoPoolName <String> -ResourceGroupName <String>
 -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSynapseKustoPoolDatabase -InputObject <ISynapseIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan sebuah database.

## EXAMPLES

### Contoh 1: List all Kusto databases in a workspace by name
```powershell
PS C:\> Get-AzSynapseKustoPoolDatabase -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool

Kind      Location  Name                                                                                                                                                                                                
----      --------  ----                                  
ReadWrite East US 2 testws/testnewkustopool/mykustodatabase
```

Perintah di atas mengembalikan semua database Kusto di "testkustopool" di ruang kerja "testws" yang ditemukan dalam grup sumber daya "testrg".

### Contoh 2: Dapatkan database Kusto spesifik menurut nama
```powershell
PS C:\> Get-AzSynapseKustoPoolDatabase -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase

Kind      Location  Name                                                                                            
----      --------  ----                                  
ReadWrite East US 2 testws/testnewkustopool/mykustodatabase
```

Perintah di atas mengembalikan database Kusto bernama "mykustodatabase" di Kumpulan Kusto "testkustopool" di WorkspaceName "testws" yang ditemukan di grup sumber daya "testrg".

## PARAMETERS

### -DatabaseName
Nama database di dalam kolam Kusto.

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

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IDatabase

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

