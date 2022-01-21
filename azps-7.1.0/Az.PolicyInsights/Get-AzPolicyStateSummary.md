---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicystatesummary
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyStateSummary.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyStateSummary.md
ms.openlocfilehash: 6368fd442b34b8167226a8b416c46e4e82c48421
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136582218"
---
# Get-AzPolicyStateSummary

## SYNOPSIS
Mendapatkan ringkasan kondisi kepatuhan kebijakan terbaru untuk sumber daya.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ManagementGroupScope
```
Get-AzPolicyStateSummary -ManagementGroupName <String> [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupScope
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] -ResourceGroupName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### PolicySetDefinitionScope
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] -PolicySetDefinitionName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### PolicyDefinitionScope
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] -PolicyDefinitionName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SubscriptionLevelPolicyAssignmentScope
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] -PolicyAssignmentName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupLevelPolicyAssignmentScope
```
Get-AzPolicyStateSummary [-SubscriptionId <String>] -ResourceGroupName <String> -PolicyAssignmentName <String>
 [-Top <Int32>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceScope
```
Get-AzPolicyStateSummary -ResourceId <String> [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan tampilan ringkasan nomor status kepatuhan kebijakan terbaru dalam berbagai lingkup, yang diputuskan ke dalam penetapan kebijakan dan definisi kebijakan. Ini hanya menyertakan negara-negara kebijakan yang tidak patuh.

## EXAMPLES

### Contoh 1: Mendapatkan ringkasan status kebijakan terbaru yang tidak patuh dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Mendapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh dalam lingkup langganan tertentu
```powershell
PS C:\> Get-AzPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan tampilan ringkasan laporan kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam langganan yang ditentukan.

### Contoh 3: Dapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh dalam lingkup grup manajemen
```powershell
PS C:\> Get-AzPolicyStateSummary -ManagementGroupName "myManagementGroup"
```

Mendapatkan tampilan ringkasan laporan kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup manajemen yang ditentukan.

### Contoh 4: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh dalam lingkup grup sumber daya dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary -ResourceGroupName "myResourceGroup"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan dalam konteks sesi saat ini).

### Contoh 5: Dapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh dalam lingkup grup sumber daya dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan tampilan ringkasan laporan kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya di dalam grup sumber daya yang ditentukan (dalam langganan yang ditentukan).

### Contoh 6: Dapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh untuk sumber daya
```powershell
PS C:\> Get-AzPolicyStateSummary -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan tampilan ringkasan laporan kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk sumber daya yang ditentukan.

### Contoh 7: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh untuk definisi kumpulan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 8: Dapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh untuk definisi kumpulan kebijakan di langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kumpulan kebijakan yang ditentukan (yang ada di dalam langganan tertentu).

### Contoh 9: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh untuk definisi kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 10: Dapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh untuk definisi kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 11: Mendapatkan ringkasan status kebijakan terbaru yang tidak patuh untuk penetapan kebijakan di langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 12: Mendapatkan ringkasan kondisi kebijakan terbaru yang tidak patuh untuk penetapan kebijakan di langganan yang ditentukan
```powershell
PS C:\> Get-AzPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan tertentu).

### Contoh 13: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh untuk penetapan kebijakan di grup sumber daya tertentu dalam langganan saat ini
```powershell
PS C:\> Get-AzPolicyStateSummary -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (dalam penyewa dalam konteks sesi saat ini) yang dihasilkan oleh penetapan kebijakan yang ditentukan (yang ada di grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 14: Mendapatkan ringkasan status kebijakan terbaru yang tidak patuh dalam lingkup langganan saat ini, dengan opsi Kueri teratas
```powershell
PS C:\> Get-AzPolicyStateSummary -Top 5
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. The command orders the policy assignment summaries in the results by non-compliant resource counts in descending order, and takes only top 5 of those policy assignment summaries.

### Contoh 15: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh dalam lingkup langganan saat ini, dengan opsi kueri Dari dan Kepada
```powershell
PS C:\> Get-AzPolicyStateSummary -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 16: Dapatkan ringkasan status kebijakan terbaru yang tidak patuh dalam lingkup langganan saat ini, dengan opsi Filter kueri
```powershell
PS C:\> Get-AzPolicyStateSummary -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ResourceLocation ne 'eastus'"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah tersebut membatasi hasil yang dikembalikan oleh pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan tolak atau audit), dan lokasi sumber daya (tidak termasuk lokasi eastus).

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

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyStateSummary

## CATATAN

## RELATED LINKS

[Get-AzPolicyState](./Get-AzPolicyState.md)
