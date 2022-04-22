---
external help file: Microsoft.Azure.Commands.PolicyInsights.dll-Help.xml
Module Name: AzureRM.PolicyInsights
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.policyinsights/get-azurermpolicystatesummary
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PolicyInsights/Commands.PolicyInsights/help/Get-AzureRmPolicyStateSummary.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PolicyInsights/Commands.PolicyInsights/help/Get-AzureRmPolicyStateSummary.md
ms.openlocfilehash: 4b4d45414a9a27561c3be4be195a1e5f77076e6b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142855721"
---
# Get-AzureRmPolicyStateSummary

## SYNOPSIS
Mendapatkan ringkasan status kepatuhan kebijakan terbaru untuk sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ManagementGroupScope
```
Get-AzureRmPolicyStateSummary -ManagementGroupName <String> [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupScope
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] -ResourceGroupName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### PolicySetDefinitionScope
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] -PolicySetDefinitionName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### PolicyDefinitionScope
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] -PolicyDefinitionName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SubscriptionLevelPolicyAssignmentScope
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] -PolicyAssignmentName <String> [-Top <Int32>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupLevelPolicyAssignmentScope
```
Get-AzureRmPolicyStateSummary [-SubscriptionId <String>] -ResourceGroupName <String>
 -PolicyAssignmentName <String> [-Top <Int32>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Cakupan Sumber Daya
```
Get-AzureRmPolicyStateSummary -ResourceId <String> [-Top <Int32>] [-From <DateTime>] [-To <DateTime>]
 [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan tampilan ringkasan tentang nomor status kepatuhan kebijakan terbaru pada berbagai lingkup, diuraikan ke dalam penetapan kebijakan dan definisi kebijakan. Ini hanya menyertakan status kebijakan yang tidak sesuai.

## EXAMPLES

### Contoh 1: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 2: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup langganan tertentu
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan pada hari terakhir untuk semua sumber daya dalam langganan yang ditentukan.

### Contoh 3: Dapatkan ringkasan status kebijakan yang tidak sesuai terbaru dalam lingkup grup manajemen
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -ManagementGroupName "myManagementGroup"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup manajemen yang ditentukan.

### Contoh 4: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup grup sumber daya dalam langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -ResourceGroupName "myResourceGroup"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup sumber daya tertentu (dalam langganan dalam konteks sesi saat ini).

### Contoh 5: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup grup sumber daya dalam langganan tertentu
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam grup sumber daya tertentu (dalam langganan yang ditentukan).

### Contoh 6: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk sumber daya
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan pada hari terakhir untuk sumber daya yang ditentukan.

### Contoh 7: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk definisi kumpulan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 8: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk definisi kumpulan kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kumpulan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 9: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk definisi kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 10: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk definisi kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh definisi kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 11: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk penetapan kebijakan dalam langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dipenrpengaruh oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan dalam konteks sesi saat ini).

### Contoh 12: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk penetapan kebijakan dalam langganan yang ditentukan
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang dipenrpengaruh oleh penetapan kebijakan yang ditentukan (yang ada dalam langganan yang ditentukan).

### Contoh 13: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai untuk penetapan kebijakan dalam grup sumber daya tertentu dalam langganan saat ini
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya (di dalam penyewa dalam konteks sesi saat ini) yang diberlakukan oleh penetapan kebijakan yang ditentukan (yang ada dalam grup sumber daya dalam langganan dalam konteks sesi saat ini).

### Contoh 14: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup langganan saat ini, dengan opsi Kueri teratas
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -Top 5
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini. Perintah mengurutkan ringkasan penetapan kebijakan dalam hasil menurut jumlah sumber daya yang tidak sesuai dalam urutan menurun, dan hanya mengambil 5 ringkasan penetapan kebijakan teratas.

### Contoh 15: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup langganan saat ini, dengan opsi kueri Dari dan Ke
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan dalam rentang tanggal yang ditentukan untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.

### Contoh 16: Dapatkan ringkasan status kebijakan terbaru yang tidak sesuai dalam lingkup langganan saat ini, dengan opsi Filter kueri
```powershell
PS C:\> Get-AzureRmPolicyStateSummary -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and ResourceLocation ne 'eastus'"
```

Mendapatkan tampilan ringkasan status kepatuhan kebijakan terbaru yang dihasilkan di hari terakhir untuk semua sumber daya dalam langganan dalam konteks sesi saat ini.
Perintah membatasi hasil yang dikembalikan dengan pemfilteran berdasarkan tindakan definisi kebijakan (termasuk tindakan penolakan atau audit), dan lokasi sumber daya (tidak termasuk lokasi eastus).

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PolicyStateSummary

## NOTES

## RELATED LINKS

[Get-AzureRmPolicyState](./Get-AzureRmPolicyState.md)
