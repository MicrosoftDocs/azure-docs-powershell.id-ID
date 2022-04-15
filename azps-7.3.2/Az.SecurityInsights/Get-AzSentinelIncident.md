---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelincident
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelIncident.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelIncident.md
ms.openlocfilehash: bc62b2525ed694386a98ab11945ddb5d635a6639
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142402613"
---
# Get-AzSentinelIncident

## SYNOPSIS
Mendapatkan satu atau beberapa Insiden Azure Sentinel.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/get-azsentinelincident) untuk informasi terbaru.

## SYNTAX

### Ruang KerjaScope (Default)
```
Get-AzSentinelIncident -ResourceGroupName <String> -WorkspaceName <String> [-Filter <String>]
 [-OrderBy <String>] [-Max <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IncidentId
```
Get-AzSentinelIncident -ResourceGroupName <String> -WorkspaceName <String> [-IncidentId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzSentinelIncident -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelIncident** mendapatkan Insiden tertentu atau beberapa insiden dari ruang kerja tertentu.
Jika Anda menentukan parameter *IncidentId* , sebuah objek **Insiden** dikembalikan.
Jika Anda tidak menentukan parameter *IncidentId* , array yang berisi Insiden dalam ruang kerja tertentu akan dikembalikan.
Default, modul mengembalikan 1000 insiden. Untuk mengambil lebih dari 1000, gunakan parameter -Max.
Anda dapat menggunakan objek **Insiden** untuk memperbarui Insiden. Misalnya, Anda dapat menambahkan komentar, mengubah tingkat keparahan, menetapkan pemilik, dll. ke **Insiden**.

*Catatan: Id Insiden berada dalam format berikut: c464bcd7-daee-47ff-ac58-1fbb73cf1d6b dan tidak sama dengan ID Insiden (angka) seperti dalam tampilan Insiden Azure Sentinel. IncidentId dapat ditemukan dalam tampilan detail insiden, dalam bidang "Tautan insiden", yang dinyatakan di bagian terakhir tautan https.*

## EXAMPLES

### Contoh 1
Dapatkan semua Insiden Azure Sentinel menggunakan objek koneksi:


```powershell
$SentinelConnection = @{
    ResourceGroupName = "myResourceGroupName"
    WorkspaceName = "myWorkspaceName"
}
Get-AzSentinelIncident @SentinelConnection
```

Contoh ini mendapatkan semua Insiden menggunakan objek koneksi

### Contoh 2
```powershell
PS C:\> $Incidents = Get-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"
```

Contoh ini mendapatkan semua Insiden dalam ruang kerja tertentu, lalu menyimpannya dalam variabel $Incidents.

### Contoh 3
```powershell
PS C:\> $Incident = Get-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" -IncidentId "myIncidentId"
```

Contoh ini mendapatkan Insiden tertentu dalam ruang kerja tertentu, lalu menyimpannya dalam variabel $Incident.<br/>
*Harap diperhatikan bahwa IncidentId dalam format ini: 168d330b-219b-4191-a5b1-742c211adb05*

### Contoh 4
```powershell
Get-AzSentinelIncident @SentinelConnection | Where-Object {$_.Title -eq "Failed AzureAD logons but success logon to host"}
```

Contoh ini menggunakan objek koneksi dan mengembalikan insiden dengan judul tertentu. <br/>
Menggunakan kondisi **Where-Object** , Anda dapat mengambil insiden dengan judul, status, tingkat keparahan, pemilik tertentu, dll.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Memfilter hasil, berdasarkan kondisi Boolean.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncidentId
Id Insiden.

```yaml
Type: System.String
Parameter Sets: IncidentId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Max
Jumlah maksimum rekaman untuk dikembalikan

```yaml
Type: System.Int32
Parameter Sets: WorkspaceScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrderBy
Mengurutkan hasil

```yaml
Type: System.String
Parameter Sets: WorkspaceScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, IncidentId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, IncidentId
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

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident
## CATATAN

## RELATED LINKS
