---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopooldataconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDataConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolDataConnection.md
ms.openlocfilehash: a7524a48ce56f053832c0049cc7d01ec500ecdc3
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607412"
---
# Get-AzSynapseKustoPoolDataConnection

## SYNOPSIS
Mengembalikan koneksi data.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolDataConnection -DatabaseName <String> -KustoPoolName <String>
 -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzSynapseKustoPoolDataConnection -DatabaseName <String> -DataConnectionName <String>
 -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSynapseKustoPoolDataConnection -InputObject <ISynapseIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan koneksi data.

## EXAMPLES

### Contoh 1: Mencantumkan semua koneksi data dalam database tertentu
```powershell
Get-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase
```

```output
Kind     Location  Name                                                                                                              
----     --------  ----                                             
EventHub East US 2 testws/testkustopool/mykustodatabase/eventhubdc
```

Perintah di atas mengembalikan semua koneksi Kusto di ruang kerja "testws" yang ditemukan di grup sumber daya "testrg".

### Contoh 2: Mendapatkan koneksi data tertentu berdasarkan nama
```powershell
Get-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName mykustodatabase -DataConnectionName mykustodataconnection
```

```output
Kind     Location  Name                                                                                                             
----     --------  ----                                             
EventHub East US 2 testws/testkustopool/mykustodatabase/mykustodataconnection
```

Perintah di atas mengembalikan koneksi data bernama "mykustodataconnection" dalam database "mykustodatabase" di ruang kerja "testws" yang ditemukan di grup sumber daya "testrg".

## PARAMETERS

### -DatabaseName
Nama database di kumpulan Kusto.

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

### -DataConnectionName
Nama koneksi data.

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

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IDataConnection

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

