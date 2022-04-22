---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicystate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyState.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyState.md
ms.openlocfilehash: 5f0fc612b5309ab68b27157d2d1bb13c9855fdd2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142898831"
---
# Get-AzPolicyState

## SYNOPSIS
Mendapatkan status kepatuhan kebijakan untuk sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.policyinsights/get-azpolicystate) untuk informasi terbaru.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ManagementGroupScope
```
Get-AzPolicyState [-All] -ManagementGroupName <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupScope
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] -ResourceGroupName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Cakupan Sumber Daya
```
Get-AzPolicyState [-All] -ResourceId <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>] [-Expand <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicySetDefinitionScope
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] -PolicySetDefinitionName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyDefinitionScope
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] -PolicyDefinitionName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelPolicyAssignmentScope
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] -PolicyAssignmentName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupLevelPolicyAssignmentScope
```
Get-AzPolicyState [-All] [-SubscriptionId <String>] -ResourceGroupName <String> -PolicyAssignmentName <String>
 [-Top <Int32>] [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan status kepatuhan kebijakan untuk sumber daya. Catatan status kebijakan dapat dikueri di berbagai lingkup. Berdasarkan interval waktu yang ditentukan (default ke hari terakhir), baik status kebijakan terbaru atau semua transisi status kebijakan dapat dikueri. Hasil dapat difilter, dikelompokkan, dan agregasi grup dapat dihitung.

## EXAMPLES

### Contoh 1: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyState
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Dapatkan status kebijakan terbaru dalam lingkup langganan tertentu
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan tertentu.

### Contoh 3: Dapatkan semua status kebijakan dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -All
```

Mendapatkan semua rekaman status kebijakan historis (termasuk terbaru) yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 4: Dapatkan status kebijakan terbaru dalam lingkup grup manajemen
```powershell
PS C:\> Get-AzPolicyState -ManagementGroupName "myManagementGroup"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup manajemen yang ditentukan.

### Contoh 5: Dapatkan status kebijakan terbaru dalam lingkup grup sumber daya dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -ResourceGroupName "myResourceGroup"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup sumber daya tertentu (dalam langganan dalam konteks sesi saat ini).

### Contoh 6: Dapatkan status kebijakan terbaru dalam lingkup grup sumber daya dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup sumber daya tertentu (dalam langganan yang ditentukan).

### Contoh 7: Dapatkan status kebijakan terbaru untuk sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan.

### Contoh 8: Dapatkan status kebijakan terbaru untuk definisi kumpulan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 9: Dapatkan status kebijakan terbaru untuk definisi kumpulan kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kumpulan kebijakan tertentu (yang ada dalam langganan yang ditentukan).

### Contoh 10: Dapatkan status kebijakan terbaru untuk definisi kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 11: Dapatkan status kebijakan terbaru untuk definisi kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 12: Mendapatkan status kebijakan terbaru untuk penetapan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipenrpengaruh oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 13: Mendapatkan status kebijakan terbaru untuk penetapan kebijakan dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dipenrpengaruh oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 14: Dapatkan status kebijakan terbaru untuk penetapan kebijakan dalam grup sumber daya tertentu dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh penetapan kebijakan yang ditentukan (yang ada dalam grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 15: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan opsi OrderBy, Atas, dan Pilih kueri
```powershell
PS C:\> Get-AzPolicyState -OrderBy "Timestamp desc, PolicyAssignmentName asc" -Top 5 -Select "Timestamp, ResourceId, PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionId, IsCompliant"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah mengurutkan hasil menurut stempel waktu dan properti nama penetapan kebijakan, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.
Ini juga memilih untuk mencantumkan hanya subset kolom untuk setiap catatan.

### Contoh 16: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan opsi kueri Dari dan Ke
```powershell
PS C:\> Get-AzPolicyState -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 17: Mendapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan opsi Filter kueri
```powershell
PS C:\> Get-AzPolicyState -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ComplianceState eq 'NonCompliant' and ResourceLocation ne 'eastus'"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan penolakan atau audit), status kepatuhan (hanya menyertakan status yang tidak sesuai) dan lokasi sumber daya (tidak termasuk lokasi eastus).

### Contoh 18: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Terapkan yang menentukan agregasi hitungan baris
```powershell
PS C:\> Get-AzPolicyState -Apply "aggregate(`$count as NumberOfRecords)"
```

Mendapatkan jumlah rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah mengembalikan hitungan rekaman status kebijakan saja, yang dikembalikan di dalam properti AdditionalProperties.

### Contoh 19: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Terapkan menentukan pengelompokan dengan agregasi
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumStates))" -OrderBy "NumStates desc" -Top 5
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan status kepatuhan (hanya menyertakan status yang tidak sesuai).
Ini mengelompokkan hasil berdasarkan penetapan kebijakan, definisi kumpulan kebijakan, dan definisi kebijakan, dan menghitung jumlah rekaman di setiap grup, yang dikembalikan di dalam properti AdditionalProperties.
Ini mengurutkan hasil menurut agregasi hitungan dalam urutan menurun, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.

### Contoh 20: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Terapkan menentukan pengelompokan tanpa agregasi
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((ResourceId))"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan status kepatuhan (hanya menyertakan status yang tidak sesuai).
Ini mengelompokkan hasil berdasarkan id sumber daya. Ini menghasilkan daftar semua sumber daya dalam langganan yang tidak memenuhi syarat untuk setidaknya satu kebijakan.

### Contoh 21: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Terapkan yang menentukan beberapa pengelompokan
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId, ResourceId))/groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumNonCompliantResources))" -OrderBy "NumNonCompliantResources desc" -Top 5
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan status kepatuhan (hanya menyertakan status yang tidak sesuai).
Ini mengelompokkan hasil terlebih dahulu berdasarkan penetapan kebijakan, definisi kumpulan kebijakan, definisi kebijakan, dan id sumber daya. Kemudian, grup selanjutnya mengelompokkan hasil pengelompokan ini dengan properti yang sama kecuali untuk id sumber daya, dan menghitung jumlah rekaman di setiap grup ini, yang dikembalikan di dalam properti AdditionalProperties.
Ini mengurutkan hasil menurut agregasi hitungan dalam urutan menurun, dan hanya mengambil 5 teratas dari yang tercantum dalam urutan tersebut.
Ini menghasilkan 5 kebijakan teratas dengan jumlah sumber daya yang tidak sesuai.

### Contoh 22: Dapatkan status kebijakan terbaru termasuk detail evaluasi kebijakan untuk sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1" -Expand "PolicyEvaluationDetails"
```

Mendapatkan rekaman status kebijakan terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan dan memperluas kebijakanEvaluationDetails.


## PARAMETERS

### -Semua
Dalam interval waktu yang ditentukan, dapatkan semua status kebijakan, bukan yang terbaru saja.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Perluas
Memperluas ekspresi menggunakan notasi OData.

```yaml
Type: System.String
Parameter Sets: ResourceScope
Aliases:

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
Stempel waktu yang diformat ISO 8601 menentukan waktu mulai interval ke kueri.
Ketika tidak ditentukan, default ke nilai parameter 'Kepada' dikurangi 1 hari.

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
Pengurutan ekspresi menggunakan notasi OData.
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
Membatasi kolom pada setiap catatan hanya pada yang diminta.

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

### -Kepada
Stempel waktu yang diformat ISO 8601 menentukan waktu akhir interval ke kueri.
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

### -Top
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyState

## NOTES

## RELATED LINKS

[Get-AzPolicyStateSummary](./Get-AzPolicyStateSummary.md)
