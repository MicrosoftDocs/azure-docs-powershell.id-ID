---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelincident
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelIncident.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelIncident.md
ms.openlocfilehash: 2c23f2eeae0135dc9964a1d20880c42896e2fac2
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145634426"
---
# Get-AzSentinelIncident

## SYNOPSIS
Mendapatkan satu atau beberapa Insiden Azure Sentinel.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/get-azsentinelincident) untuk informasi terbaru.

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
Cmdlet **Get-AzSentinelIncident** mendapatkan Insiden tertentu atau beberapa dari ruang kerja yang ditentukan.
Jika Anda menentukan parameter *IncidentId* , satu objek **Insiden** akan dikembalikan.
Jika Anda tidak menentukan parameter *IncidentId* , array yang berisi Insiden di ruang kerja yang ditentukan akan dikembalikan.
Default, modul mengembalikan 1000 insiden. Untuk mengambil lebih dari 1000, gunakan parameter -Max.
Anda dapat menggunakan objek **Insiden** untuk memperbarui Insiden. Misalnya Anda dapat menambahkan komentar, mengubah tingkat keparahan, menetapkan pemilik, dll. ke **Insiden**.

*Catatan: IncidentId dalam format berikut: c464bcd7-daee-47ff-ac58-1fbb73cf1d6b dan tidak sama dengan ID Insiden (angka) seperti dalam tampilan Insiden Azure Sentinel. IncidentId dapat ditemukan dalam tampilan detail insiden, di bidang "Tautan insiden", yang diwakili di bagian terakhir tautan https.*

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
$Incidents = Get-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"
```

Contoh ini mendapatkan semua Insiden di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $Incidents.

### Contoh: 3
```powershell
$Incident = Get-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" -IncidentId "myIncidentId"
```

Contoh ini mendapatkan Insiden tertentu di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $Incident.<br/>
*Harap dicatat bahwa IncidentId dalam format ini: 168d330b-219b-4191-a5b1-742c211adb05*

### Contoh 4
```powershell
Get-AzSentinelIncident @SentinelConnection | Where-Object {$_.Title -eq "Failed AzureAD logons but success logon to host"}
```

Contoh ini menggunakan objek koneksi dan mengembalikan insiden dengan judul tertentu. <br/>
Dengan menggunakan kondisi **Where-Object** , Anda dapat mengambil insiden dengan judul, status, tingkat keparahan, pemilik, dll tertentu.

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
Memfilter hasilnya, berdasarkan kondisi Boolean.

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

### -Maks
Jumlah maksimum rekaman yang akan dikembalikan

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

### -WorkspaceName
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident
## NOTES

## RELATED LINKS
