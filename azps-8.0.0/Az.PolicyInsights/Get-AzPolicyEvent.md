---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicyevent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyEvent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyEvent.md
ms.openlocfilehash: 4894a17c265d769969e7e8f33402d28c98d2eb92
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145519459"
---
# Get-AzPolicyEvent

## SYNOPSIS
Mendapatkan peristiwa evaluasi kebijakan yang dihasilkan saat sumber daya dibuat atau diperbarui.

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

### Cakupan Sumber Daya
```
Get-AzPolicyEvent -ResourceId <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>] [-From <DateTime>]
 [-To <DateTime>] [-Filter <String>] [-Apply <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan peristiwa evaluasi kebijakan yang dihasilkan saat sumber daya dibuat atau diperbarui. Rekaman peristiwa kebijakan dapat dikueri pada berbagai cakupan berdasarkan interval waktu yang ditentukan (default ke hari terakhir). Hasil dapat difilter, dikelompokkan, dan agregasi grup dapat dihitung.

## EXAMPLES

### Contoh 1: Mendapatkan peristiwa kebijakan dalam cakupan langganan saat ini
```powershell
Get-AzPolicyEvent
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Mendapatkan peristiwa kebijakan dalam cakupan langganan yang ditentukan
```powershell
Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk semua sumber daya dalam langganan yang ditentukan.

### Contoh 3: Mendapatkan peristiwa kebijakan dalam cakupan grup manajemen
```powershell
Get-AzPolicyEvent -ManagementGroupName "myManagementGroup"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup manajemen yang ditentukan.

### Contoh 4: Mendapatkan peristiwa kebijakan dalam cakupan grup sumber daya dalam langganan saat ini
```powershell
Get-AzPolicyEvent -ResourceGroupName "myResourceGroup"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup sumber daya yang ditentukan (dalam langganan dalam konteks sesi saat ini).

### Contoh 5: Mendapatkan peristiwa kebijakan dalam cakupan grup sumber daya dalam langganan yang ditentukan
```powershell
Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk semua sumber daya dalam grup sumber daya yang ditentukan (dalam langganan yang ditentukan).

### Contoh 6: Mendapatkan peristiwa kebijakan untuk sumber daya
```powershell
Get-AzPolicyEvent -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk sumber daya yang ditentukan.

### Contoh 7: Mendapatkan peristiwa kebijakan untuk definisi yang ditetapkan kebijakan dalam langganan saat ini
```powershell
Get-AzPolicyEvent -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 8: Mendapatkan peristiwa kebijakan untuk definisi kumpulan kebijakan dalam langganan yang ditentukan
```powershell
Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 9: Mendapatkan peristiwa kebijakan untuk definisi kebijakan dalam langganan saat ini
```powershell
Get-AzPolicyEvent -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 10: Mendapatkan peristiwa kebijakan untuk definisi kebijakan dalam langganan yang ditentukan
```powershell
Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh definisi kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 11: Mendapatkan peristiwa kebijakan untuk penetapan kebijakan dalam langganan saat ini
```powershell
Get-AzPolicyEvent -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 12: Mendapatkan peristiwa kebijakan untuk penetapan kebijakan dalam langganan yang ditentukan
```powershell
Get-AzPolicyEvent -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan pada hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 13: Mendapatkan peristiwa kebijakan untuk penetapan kebijakan di grup sumber daya yang ditentukan dalam langganan saat ini
```powershell
Get-AzPolicyEvent -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipengaruhi oleh penetapan kebijakan yang ditentukan (yang ada di grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 14: Mendapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan opsi OrderBy, Top, dan Select query
```powershell
Get-AzPolicyEvent -OrderBy "Timestamp desc, PolicyAssignmentName asc" -Top 5 -Select "Timestamp, ResourceId, PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionId"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah mengurutkan hasil berdasarkan tanda waktu dan properti nama penetapan kebijakan, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.
Ini juga memilih untuk mencantumkan hanya subset kolom untuk setiap rekaman.

### Contoh 15: Mendapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan opsi kueri Dari dan Ke
```powershell
Get-AzPolicyEvent -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 16: Dapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan opsi Filter kueri
```powershell
Get-AzPolicyEvent -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ResourceLocation ne 'eastus'"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan tolak atau audit) dan lokasi sumber daya (tidak termasuk lokasi eastus).

### Contoh 17: Dapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan Terapkan yang menentukan agregasi jumlah baris
```powershell
Get-AzPolicyEvent -Apply "aggregate(`$count as NumberOfRecords)"
```

Mendapatkan jumlah rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah mengembalikan jumlah rekaman peristiwa kebijakan saja, yang dikembalikan di dalam properti AdditionalProperties.

### Contoh 18: Dapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan Terapkan menentukan pengelompokan dengan agregasi
```powershell
Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'audit' or PolicyDefinitionAction eq 'deny'" -Apply "groupby((PolicyAssignmentId, PolicyDefinitionId, PolicyDefinitionAction, ResourceId), aggregate(`$count as NumEvents))" -OrderBy "NumEvents desc" -Top 5
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan memfilter berdasarkan tindakan definisi kebijakan (hanya mencakup peristiwa audit dan tolak).
Ini mengelompokkan hasil berdasarkan penetapan kebijakan, definisi kebijakan, tindakan definisi kebijakan, dan id sumber daya, dan menghitung jumlah rekaman di setiap grup, yang dikembalikan di dalam properti AdditionalProperties.
Ini mengurutkan hasil berdasarkan agregasi hitungan dalam urutan turun, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.

### Contoh 19: Dapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan Terapkan menentukan pengelompokan tanpa agregasi
```powershell
Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'audit' or PolicyDefinitionAction eq 'deny'" -Apply "groupby((ResourceId))"
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan memfilter berdasarkan tindakan definisi kebijakan (hanya mencakup peristiwa audit dan tolak).
Ini mengelompokkan hasil berdasarkan id sumber daya. Ini menghasilkan daftar semua sumber daya dalam langganan yang menghasilkan peristiwa kebijakan untuk setidaknya satu kebijakan audit atau penolakan.

### Contoh 20: Dapatkan peristiwa kebijakan dalam cakupan langganan saat ini, dengan Terapkan yang menentukan beberapa pengelompokan
```powershell
Get-AzPolicyEvent -Filter "PolicyDefinitionAction eq 'deny'" -Apply "groupby((PolicyAssignmentId, PolicyDefinitionId, ResourceId))/groupby((PolicyAssignmentId, PolicyDefinitionId), aggregate(`$count as NumDeniedResources))" -OrderBy "NumDeniedResources desc" -Top 5
```

Mendapatkan rekaman peristiwa kebijakan yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (hanya menyertakan peristiwa tolak).
Ini mengelompokkan hasil terlebih dahulu berdasarkan penetapan kebijakan, definisi kebijakan, dan id sumber daya. Kemudian, ini selanjutnya mengelompokkan hasil pengelompokan ini dengan properti yang sama kecuali untuk id sumber daya, dan menghitung jumlah rekaman di masing-masing grup ini, yang dikembalikan di dalam properti AdditionalProperties.
Ini mengurutkan hasil berdasarkan agregasi hitungan dalam urutan turun, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.
Ini menghasilkan 5 kebijakan tolak teratas dengan jumlah sumber daya yang ditolak paling banyak.

## PARAMETERS

### -Terapkan
Terapkan ekspresi untuk agregasi menggunakan notasi OData.

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
Filter ekspresi menggunakan notasi OData.

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
Tanda waktu berformat ISO 8601 yang menentukan waktu mulai interval untuk kueri.
Ketika tidak ditentukan, default ke nilai parameter 'Ke' dikurangi 1 hari.

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
Mengurutkan ekspresi menggunakan notasi OData.
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
Membatasi kolom pada setiap rekaman hanya untuk yang diminta.

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
Tanda waktu berformat ISO 8601 yang menentukan waktu akhir interval untuk kueri.
Ketika tidak ditentukan, default ke waktu permintaan.

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

### -Atas
Jumlah maksimum rekaman yang akan dikembalikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyEvent

## NOTES

## RELATED LINKS
