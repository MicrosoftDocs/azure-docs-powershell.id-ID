---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicystate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyState.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyState.md
ms.openlocfilehash: e95744756f9f7721b25f1d35d76307b2d102096c
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136527548"
---
# Get-AzPolicyState

## SYNOPSIS
Mendapatkan kebijakan tingkat kepatuhan untuk sumber daya.

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

### ResourceScope
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
Mendapatkan kebijakan tingkat kepatuhan untuk sumber daya. Catatan status kebijakan bisa dikutafkan di berbagai lingkup. Berdasarkan interval waktu yang ditentukan (default ke hari terakhir), baik status kebijakan terbaru maupun semua transisi status kebijakan dapat dikuerifikasi. Hasil bisa difilter, dikelompokkan, dan agregasi grup bisa dihitung.

## EXAMPLES

### Contoh 1: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyState
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Dapatkan kondisi kebijakan terbaru dalam lingkup langganan tertentu
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam langganan yang ditentukan.

### Contoh 3: Dapatkan semua status kebijakan dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -All
```

Mendapatkan semua catatan status kebijakan historis (termasuk yang terbaru) yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 4: Dapatkan kondisi kebijakan terbaru dalam lingkup grup manajemen
```powershell
PS C:\> Get-AzPolicyState -ManagementGroupName "myManagementGroup"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup manajemen yang ditentukan.

### Contoh 5: Dapatkan status kebijakan terbaru dalam lingkup grup sumber daya dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -ResourceGroupName "myResourceGroup"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan dalam konteks sesi saat ini).

### Contoh 6: Dapatkan kondisi kebijakan terbaru dalam lingkup grup sumber daya dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan yang ditentukan).

### Contoh 7: Dapatkan kondisi kebijakan terbaru untuk sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan.

### Contoh 8: Dapatkan status kebijakan terbaru untuk definisi kumpulan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 9: Dapatkan kondisi kebijakan terbaru untuk definisi kumpulan kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada di dalam langganan yang ditentukan).

### Contoh 10: Dapatkan status kebijakan terbaru untuk definisi kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 11: Dapatkan kondisi kebijakan terbaru untuk definisi kebijakan dalam langganan tertentu
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada di langganan yang ditentukan).

### Contoh 12: Dapatkan status kebijakan terbaru untuk penetapan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 13: Dapatkan kondisi kebijakan terbaru untuk penetapan kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 14: Dapatkan status kebijakan terbaru untuk penetapan kebijakan dalam grup sumber daya tertentu dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyState -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada di grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 15: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan OrderBy, Top, dan Pilih opsi kueri
```powershell
PS C:\> Get-AzPolicyState -OrderBy "Timestamp desc, PolicyAssignmentName asc" -Top 5 -Select "Timestamp, ResourceId, PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionId, IsCompliant"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah memesan hasil menurut timestamp dan properti nama penetapan kebijakan, dan hanya akan mengambil 5 teratas dari properti yang tercantum dalam urutan tersebut.
Opsi ini juga memilih untuk mencantumkan hanya subset kolom untuk setiap rekaman.

### Contoh 16: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan opsi kueri Dari dan Ke
```powershell
PS C:\> Get-AzPolicyState -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya di dalam langganan dalam konteks sesi saat ini.

### Contoh 17: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan opsi Filter kueri
```powershell
PS C:\> Get-AzPolicyState -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ComplianceState eq 'NonCompliant' and ResourceLocation ne 'eastus'"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah tersebut membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan tolak atau audit), status kepatuhan (hanya menyertakan status tidak memenuhi syarat) dan lokasi sumber daya (tidak termasuk lokasi eastus).

### Contoh 18: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Terapkan agregasi menentukan jumlah baris
```powershell
PS C:\> Get-AzPolicyState -Apply "aggregate(`$count as NumberOfRecords)"
```

Dapatkan jumlah catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah mengembalikan hitungan data status kebijakan saja, yang dikembalikan di dalam properti AdditionalProperties.

### Contoh 19: Get latest policy states in current subscription scope, with Apply specifying grouping with aggregation
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumStates))" -OrderBy "NumStates desc" -Top 5
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan dengan memfilter berdasarkan status kepatuhan (hanya menyertakan status tidak memenuhi persyaratan).
Properti ini mengelompokkan hasil berdasarkan penetapan kebijakan, definisi kumpulan kebijakan, dan definisi kebijakan, serta menghitung jumlah data di setiap grup, yang dikembalikan di dalam properti AdditionalProperties.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.

### Contoh 20: Get latest policy states in current subscription scope, with Apply specifying grouping without aggregation
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((ResourceId))"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan dengan memfilter berdasarkan status kepatuhan (hanya menyertakan status tidak memenuhi persyaratan).
It groups the results based on resource id. Ini menghasilkan daftar semua sumber daya di dalam langganan yang tidak memenuhi syarat untuk setidaknya satu kebijakan.

### Contoh 21: Dapatkan status kebijakan terbaru dalam lingkup langganan saat ini, dengan Menerapkan menentukan beberapa grup
```powershell
PS C:\> Get-AzPolicyState -Filter "ComplianceState eq 'NonCompliant'" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId, ResourceId))/groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumNonCompliantResources))" -OrderBy "NumNonCompliantResources desc" -Top 5
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah tersebut membatasi hasil yang dikembalikan dengan memfilter berdasarkan status kepatuhan (hanya menyertakan status tidak memenuhi persyaratan).
It groups the results first based on policy assignment, policy set definition, policy definition, and resource id. Lalu, selanjutnya mengelompokkan hasil dari grup ini dengan properti yang sama kecuali untuk id sumber daya, dan menghitung jumlah data di setiap grup ini, yang dikembalikan di dalam properti AdditionalProperties.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.
Ini menghasilkan 5 kebijakan teratas dengan sebagian besar sumber daya yang tidak patuh.

### Contoh 22: Dapatkan kondisi kebijakan terbaru termasuk detail evaluasi kebijakan untuk sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1" -Expand "PolicyEvaluationDetails"
```

Mendapatkan catatan status kebijakan terbaru yang dihasilkan di hari terakhir untuk sumber daya tertentu dan memperluas kebijakanEvaluationDetails.

### Contoh 23: Dapatkan kondisi kebijakan komponen terbaru untuk sumber daya (misalnya. vault) diberi penetapan kebijakan mode penyedia sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.KeyVault/vaults/myvault" - Filter "policyAssignmentId eq '/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/providers/Microsoft.Authorization/policyAssignments/ddd8ef92e3714a5ea3d208c1'" -Expand "Components(`$filter=ComplianceState eq 'NonCompliant' or ComplianceState eq 'Compliant')"
```

Mendapatkan catatan status kebijakan komponen terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan, diberikan penetapan kebijakan mode penyedia sumber daya yang mereferesi definisi kebijakan mode penyedia sumber daya.


### Contoh 24: Dapatkan kondisi kebijakan komponen terbaru untuk sumber daya (misalnya. vault) diberi penetapan inisiatif kebijakan yang berisi definisi kebijakan mode penyedia sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.KeyVault/vaults/myvault" - Filter "policyAssignmentId eq '/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/providers/Microsoft.Authorization/policyAssignments/ddd8ef92e3714a5ea3d208c1' and policyDefinitionReferenceId eq 'myResourceProviderModeDefinitionReferenceId'" -Expand "Components(`$filter=ComplianceState eq 'NonCompliant' or ComplianceState eq 'Compliant')"
```

Mendapatkan catatan status kebijakan komponen terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan, diberikan penetapan kebijakan mode penyedia sumber daya yang mereferisi inisiatif yang berisi definisi kebijakan mode penyedia sumber daya.


### Contoh 25: Dapatkan hitungan komponen terbaru menurut status kepatuhan untuk sumber daya (misalnya. vault) diberi penetapan kebijakan mode penyedia sumber daya
```powershell
PS C:\> Get-AzPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.KeyVault/vaults/myvault" - Filter "policyAssignmentId eq '/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/providers/Microsoft.Authorization/policyAssignments/ddd8ef92e3714a5ea3d208c1'" -Expand "Components(`$filter=ComplianceState eq 'NonCompliant' or ComplianceState eq 'Compliant' or ComplianceState eq 'Conflict';`$apply=groupby((complianceState),aggregate(`$count as count)))"
```

Mendapatkan hitungan komponen terbaru yang dihasilkan dalam hari terakhir yang dikelompokkan menurut status kepatuhan untuk sumber daya yang ditentukan, diberikan penetapan kebijakan mode penyedia sumber daya.


## PARAMETERS

### -Semua
Dalam interval waktu yang ditentukan, dapatkan semua kondisi kebijakan, bukan yang terbaru saja.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyState

## CATATAN

## RELATED LINKS

[Get-AzPolicyStateSummary](./Get-AzPolicyStateSummary.md)
