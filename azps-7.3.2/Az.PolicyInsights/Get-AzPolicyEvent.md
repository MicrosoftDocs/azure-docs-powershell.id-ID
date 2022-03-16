---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicyevent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyEvent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyEvent.md
ms.openlocfilehash: 91d1a7a625869c3d68f0952e616bb52f64342b28
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140184837"
---
# Get-AzPolicyEvent

## SYNOPSIS
Gets policy evaluation events generated as resources are created or updated.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzPolicyEvent [-SubscriptionId <String>] [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ManagementGroupScope
```
Get-AzPolicyEvent -ManagementGroupName <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupScope
```
Get-AzPolicyEvent [-SubscriptionId <String>] -ResourceGroupName <String> [-Top <Int32>] [-OrderBy <String>]
 [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicySetDefinitionScope
```
Get-AzPolicyEvent [-SubscriptionId <String>] -PolicySetDefinitionName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyDefinitionScope
```
Get-AzPolicyEvent [-SubscriptionId <String>] -PolicyDefinitionName <String> [-Top <Int32>] [-OrderBy <String>]
 [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelPolicyAssignmentScope
```
Get-AzPolicyEvent [-SubscriptionId <String>] -PolicyAssignmentName <String> [-Top <Int32>] [-OrderBy <String>]
 [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupLevelPolicyAssignmentScope
```
Get-AzPolicyEvent [-SubscriptionId <String>] -ResourceGroupName <String> -PolicyAssignmentName <String>
 [-Top <Int32>] [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceScope
```
Get-AzPolicyEvent -ResourceId <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>] [-From <DateTime>]
 [-To <DateTime>] [-Filter <String>] [-Apply <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets policy evaluation events generated as resources are created or updated. Rekaman kejadian kebijakan dapat dikuerifikasi pada berbagai lingkup berdasarkan interval waktu yang ditentukan (default ke hari terakhir). Hasil bisa difilter, dikelompokkan, dan agregasi grup bisa dihitung.

## EXAMPLES

### Contoh 1: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Dapatkan kejadian kebijakan dalam lingkup langganan tertentu
```powershell
PS C:\> Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya di dalam langganan yang ditentukan.

### Contoh 3: Dapatkan kejadian kebijakan dalam lingkup grup manajemen
```powershell
PS C:\> Get-AzPolicyEvent -ManagementGroupName "myManagementGroup"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup manajemen yang ditentukan.

### Contoh 4: Dapatkan kejadian kebijakan dalam lingkup grup sumber daya dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent -ResourceGroupName "myResourceGroup"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan dalam konteks sesi saat ini).

### Contoh 5: Dapatkan kejadian kebijakan dalam lingkup grup sumber daya dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan yang ditentukan).

### Contoh 6: Dapatkan kejadian kebijakan untuk sumber daya
```powershell
PS C:\> Get-AzPolicyEvent -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan.

### Contoh 7: Dapatkan kejadian kebijakan untuk definisi kumpulan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 8: Dapatkan kejadian kebijakan untuk definisi kumpulan kebijakan dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada di dalam langganan yang ditentukan).

### Contoh 9: Dapatkan kejadian kebijakan untuk definisi kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 10: Dapatkan kejadian kebijakan untuk definisi kebijakan dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 11: Mendapatkan kejadian kebijakan untuk penetapan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 12: Dapatkan kejadian kebijakan untuk penetapan kebijakan dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang disebabkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 13: Dapatkan kejadian kebijakan untuk penetapan kebijakan di grup sumber daya tertentu dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyEvent -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada di grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 14: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan OrderBy, Top, dan Pilih opsi kueri
```powershell
PS C:\> Get-AzPolicyEvent -OrderBy "Timestamp desc, PolicyAssignmentName asc" -Top 5 -Select "Timestamp, ResourceId, PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionId"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah memesan hasil menurut timestamp dan properti nama penetapan kebijakan, dan hanya akan mengambil 5 teratas dari properti yang tercantum dalam urutan tersebut.
Opsi ini juga memilih untuk mencantumkan hanya subset kolom untuk setiap rekaman.

### Contoh 15: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan opsi kueri Dari dan Ke
```powershell
PS C:\> Get-AzPolicyEvent -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya di dalam langganan dalam konteks sesi saat ini.

### Contoh 16: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan opsi Filter kueri
```powershell
PS C:\> Get-AzPolicyEvent -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ResourceLocation ne 'eastus'"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah tersebut membatasi hasil yang dikembalikan oleh pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan tolak atau audit) dan lokasi sumber daya (tidak termasuk lokasi eastus).

### Contoh 17: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan Menerapkan agregasi menentukan agregasi jumlah baris
```powershell
PS C:\> Get-AzPolicyEvent -Apply "aggregate(`$count as NumberOfRecords)"
```

Dapatkan jumlah catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah mengembalikan hitungan data kejadian kebijakan saja, yang dikembalikan di dalam properti AdditionalProperties.

### Contoh 18: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan Terapkan tentukan grup dengan agregasi
```powershell
PS C:\> Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'audit' or PolicyDefinitionAction eq 'deny'" -Apply "groupby((PolicyAssignmentId, PolicyDefinitionId, PolicyDefinitionAction, ResourceId), aggregate(`$count as NumEvents))" -OrderBy "NumEvents desc" -Top 5
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan oleh pemfilteran berdasarkan tindakan definisi kebijakan (hanya menyertakan audit dan tolak kejadian).
Fungsi ini mengelompokkan hasil berdasarkan penetapan kebijakan, definisi kebijakan, tindakan definisi kebijakan, dan id sumber daya, serta menghitung jumlah data di setiap grup, yang dikembalikan di dalam properti AdditionalProperties.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.

### Contoh 19: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan Terapkan tentukan grup tanpa agregasi
```powershell
PS C:\> Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'audit' or PolicyDefinitionAction eq 'deny'" -Apply "groupby((ResourceId))"
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan oleh pemfilteran berdasarkan tindakan definisi kebijakan (hanya menyertakan audit dan tolak kejadian).
It groups the results based on resource id. Ini menghasilkan daftar semua sumber daya di dalam langganan yang menghasilkan kejadian kebijakan untuk setidaknya satu audit atau tolak kebijakan.

### Contoh 20: Dapatkan kejadian kebijakan dalam lingkup langganan saat ini, dengan Menerapkan menentukan beberapa grup
```powershell
PS C:\> Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'deny'" -Apply "groupby((PolicyAssignmentId, PolicyDefinitionId, ResourceId))/groupby((PolicyAssignmentId, PolicyDefinitionId), aggregate(`$count as NumDeniedResources))" -OrderBy "NumDeniedResources desc" -Top 5
```

Mendapatkan catatan kejadian kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (termasuk hanya tolak kejadian).
It groups the results first based on policy assignment, policy definition, and resource id. Lalu, selanjutnya mengelompokkan hasil dari grup ini dengan properti yang sama kecuali untuk id sumber daya, dan menghitung jumlah data di setiap grup ini, yang dikembalikan di dalam properti AdditionalProperties.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.
Ini menghasilkan 5 kebijakan penolakan teratas dengan sebagian besar sumber daya yang ditolak.

## PARAMETERS

### -Apply
Menerapkan ekspresi untuk agregasi menggunakan notasi OData.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Memfilter ekspresi menggunakan notasi OData.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dari
Timestamp yang diformat ISO 8601 yang menentukan waktu mulai interval ke kueri.
Ketika tidak ditentukan, default nilai parameter 'To' dikurangi 1 hari.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementGroupName
Nama grup manajemen.

```yaml
Type: System.String
Parameter Sets: ManagementGroupScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrderBy
Memesan ekspresi menggunakan notasi OData.
Satu atau beberapa nama kolom yang dipisahkan koma dengan 'desc' opsional (default) atau 'asc'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyAssignmentName
Nama penetapan kebijakan.

```yaml
Type: System.String
Parameter Sets: SubscriptionLevelPolicyAssignmentScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyDefinitionName
Nama definisi kebijakan.

```yaml
Type: System.String
Parameter Sets: PolicyDefinitionScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicySetDefinitionName
Nama definisi kumpulan kebijakan.

```yaml
Type: System.String
Parameter Sets: PolicySetDefinitionScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceGroupScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pilih
Pilih ekspresi menggunakan notasi OData.
Satu atau beberapa nama kolom yang dipisahkan koma.
Membatasi kolom di setiap rekaman hanya untuk yang diminta.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan.

```yaml
Type: System.String
Parameter Sets: SubscriptionScope, ResourceGroupScope, PolicySetDefinitionScope, PolicyDefinitionScope, SubscriptionLevelPolicyAssignmentScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ke
Timestamp yang diformat ISO 8601 yang menentukan waktu akhir interval ke kueri.
Bila tidak ditentukan, defaultnya adalah waktu permintaan.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Jumlah rekaman maksimum yang dikembalikan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyEvent

## CATATAN

## RELATED LINKS
