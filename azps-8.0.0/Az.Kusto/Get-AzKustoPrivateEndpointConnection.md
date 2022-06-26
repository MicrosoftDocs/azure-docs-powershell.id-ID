---
external help file: ''
Module Name: Az.Kusto
online version: https://docs.microsoft.com/powershell/module/az.kusto/get-azkustoprivateendpointconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoPrivateEndpointConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoPrivateEndpointConnection.md
ms.openlocfilehash: 8abb0be5485897488364963a77576822f78131a2
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146636662"
---
# Get-AzKustoPrivateEndpointConnection

## SYNOPSIS
Mendapatkan koneksi titik akhir privat.

## SYNTAX

### Daftar (Default)
```
Get-AzKustoPrivateEndpointConnection -ClusterName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzKustoPrivateEndpointConnection -ClusterName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzKustoPrivateEndpointConnection -InputObject <IKustoIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan koneksi titik akhir privat.

## EXAMPLES

### Contoh 1: Mencantumkan semua Kusto PrivateEndpointConnection dalam kluster berdasarkan nama
```powershell
Get-AzKustoPrivateEndpointConnection -ClusterName "mycluster" -ResourceGroupName "testrg" -SubscriptionId "12345678-1234-1234-1234-123456789098"
```

```output
Name                                                       Type
----                                                       ----
privateEndpointConnectionName1                             Microsoft.Kusto/Clusters/PrivateEndpointConnections
privateEndpointConnectionName2                             Microsoft.Kusto/Clusters/PrivateEndpointConnections
```

Perintah di atas mengembalikan semua Kusto PrivateEndpointConnection di kluster "mycluster" yang ditemukan di grup sumber daya "testrg".

### Contoh 2: Dapatkan Kusto PrivateEndpointConnection tertentu berdasarkan nama
```powershell
Get-AzKustoPrivateEndpointConnection -ClusterName "mycluster" -ResourceGroupName "testrg" -SubscriptionId "12345678-1234-1234-1234-123456789098" -Name "privateEndpointConnectionName"
```

```output
Name                                                       Type
----                                                       ----
privateEndpointConnectionName                              Microsoft.Kusto/Clusters/PrivateEndpointConnections
```

Perintah di atas mengembalikan Kusto PrivateEndpointConnection bernama "privateEndpointConnectionName" di kluster "mycluster" yang ditemukan di grup sumber daya "testrg".

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Kusto.Models.IKustoIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama koneksi titik akhir privat.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: PrivateEndpointConnectionName

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
Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Kusto. Models.IKustoIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Kusto. Models.Api20220201.IPrivateEndpointConnection

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IKustoIdentity>`: Parameter Identitas
  - `[AttachedDatabaseConfigurationName <String>]`: Nama konfigurasi database terlampir.
  - `[ClusterName <String>]`: Nama kluster Kusto.
  - `[DataConnectionName <String>]`: Nama koneksi data.
  - `[DatabaseName <String>]`: Nama database di kluster Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi (wilayah) Azure.
  - `[ManagedPrivateEndpointName <String>]`: Nama titik akhir privat terkelola.
  - `[OperationId <String>]`: Guid ID operasi
  - `[PrincipalAssignmentName <String>]`: Nama Kusto principalAssignment.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[PrivateLinkResourceName <String>]`: Nama sumber daya tautan privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi kluster Kusto.
  - `[ScriptName <String>]`: Nama skrip database Kusto.
  - `[SubscriptionId <String>]`: Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

