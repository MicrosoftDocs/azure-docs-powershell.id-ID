---
external help file: ''
Module Name: Az.Kusto
online version: https://docs.microsoft.com/powershell/module/az.kusto/get-azkustoscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoScript.md
ms.openlocfilehash: 78cf6462920b316adc091c3da6704a92fb84daeb
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138283388"
---
# Get-AzKustoScript

## SYNOPSIS
Mendapatkan skrip database kluster Kusto.

## SYNTAX

### Daftar (Default)
```
Get-AzKustoScript -ClusterName <String> -DatabaseName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzKustoScript -ClusterName <String> -DatabaseName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzKustoScript -InputObject <IKustoIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan skrip database kluster Kusto.

## EXAMPLES

### Contoh 1: List all Kusto cluster database scripts

```powershell
PS C:\> Get-AzKustoScript -ClusterName testnewkustocluster -ResourceGroupName testrg -DatabaseName mykustodatabase

Name                                               Type
----                                               ----
testnewkustocluster/mykustodatabase/newkustoscript Microsoft.Kusto/Clusters/Databases/Scripts
```

Perintah di atas mengembalikan semua skrip database kluster Kusto dalam kluster "testnewkustocluster" yang ditemukan dalam grup sumber daya "testrg".

### Contoh 2: Dapatkan skrip database Kusto spesifik menurut nama
```powershell
PS C:\> Get-AzKustoScript -ClusterName testnewkustocluster -ResourceGroupName testrg -DatabaseName mykustodatabase -Name newkustoscript

Name                                               Type
----                                               ----
testnewkustocluster/mykustodatabase/newkustoscript Microsoft.Kusto/Clusters/Databases/Scripts
```

Perintah di atas mengembalikan skrip database Kusto yang bernama "newkustoscript" dalam kluster "testnewkustocluster" yang ditemukan dalam grup sumber daya "testrg".

## PARAMETERS

### -ClusterName
Nama kluster Kusto.

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

### -DatabaseName
Nama database dalam kluster Kusto.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Kusto.Models.IKustoIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama skrip database Kusto.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ScriptName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi kluster Kusto.

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
Mendapatkan kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Kusto.Models.IKustoIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Kusto.Models.Api202101.IScript

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IKustoIdentity>: Parameter Identitas
  - `[AttachedDatabaseConfigurationName <String>]`: Nama konfigurasi database yang dilampirkan.
  - `[ClusterName <String>]`: Nama kluster Kusto.
  - `[DataConnectionName <String>]`: Nama koneksi data.
  - `[DatabaseName <String>]`: Nama database dalam kluster Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi Azure (kawasan).
  - `[OperationId <String>]`: Guid ID operasi
  - `[PrincipalAssignmentName <String>]`: Nama principalAssignment Kusto.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi kluster Kusto.
  - `[ScriptName <String>]`: Nama skrip database Kusto.
  - `[SubscriptionId <String>]`: Mendapatkan kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

