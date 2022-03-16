---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/start-azpolicyremediation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyRemediation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyRemediation.md
ms.openlocfilehash: 089091589dd18e9587d4cf7793fe90c7fa898b48
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140190366"
---
# Start-AzPolicyRemediation

## SYNOPSIS
Membuat dan memulai perbaikan kebijakan untuk penetapan kebijakan.

## SYNTAX

### ByName (Default)
```
Start-AzPolicyRemediation -Name <String> [-Scope <String>] [-ManagementGroupName <String>]
 [-ResourceGroupName <String>] -PolicyAssignmentId <String> [-PolicyDefinitionReferenceId <String>]
 [-LocationFilter <String[]>] [-ResourceDiscoveryMode <String>] [-ResourceCount <Int32>]
 [-ParallelDeploymentCount <Int32>] [-FailureThreshold <Double>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Start-AzPolicyRemediation -ResourceId <String> -PolicyAssignmentId <String>
 [-PolicyDefinitionReferenceId <String>] [-LocationFilter <String[]>] [-ResourceDiscoveryMode <String>]
 [-ResourceCount <Int32>] [-ParallelDeploymentCount <Int32>] [-FailureThreshold <Double>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzPolicyRemediation** membuat perbaikan kebijakan untuk penetapan kebijakan tertentu. Semua sumber daya yang tidak memenuhi syarat di atau di bawah lingkup perbaikan akan diperbaiki. Perbaikan hanya didukung untuk kebijakan dengan efek 'deployIfNotExists'.

## EXAMPLES

### Contoh 1: Mulai perbaikan di lingkup langganan
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription "My Subscription"
PS C:\> Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1"
```

Perintah ini membuat perbaikan kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan.

### Contoh 2: Mulai perbaikan pada lingkup grup manajemen dengan filter opsional
```
PS C:\> $policyAssignmentId = "/providers/Microsoft.Management/managementGroups/mg1/providers/Microsoft.Authorization/policyAssignments/pa1"
PS C:\> Start-AzPolicyRemediation -ManagementGroupName "mg1" -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -LocationFilter "westus","eastus"
```

Perintah ini membuat perbaikan kebijakan baru dalam grup manajemen 'mg1' untuk penetapan kebijakan yang diberikan. Hanya sumber daya di lokasi 'westus' atau 'eastus' yang akan diperbaiki.

### Contoh 3: Mulai perbaikan pada lingkup grup sumber daya untuk penetapan definisi kumpulan kebijakan
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/resourceGroups/myRG/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Start-AzPolicyRemediation -ResourceGroupName "myRG" -PolicyAssignmentId $policyAssignmentId -PolicyDefinitionReferenceId "0349234412441" -Name "remediation1"
```

Perintah ini membuat perbaikan kebijakan baru dalam grup sumber daya 'myRG' untuk penetapan kebijakan yang diberikan. Penetapan kebijakan menetapkan definisi kumpulan kebijakan (juga dikenal sebagai inisiatif). ID referensi definisi kebijakan menunjukkan kebijakan mana yang di dalam inisiatif tersebut harus diperbaiki.

### Contoh 4: Mulai perbaikan dan tunggu hingga selesai di latar belakang
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription f0710c27-9663-4c05-19f8-1b4be01e86a5
PS C:\> $job = Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -AsJob
PS C:\> $job | Wait-Job
PS C:\> $remediation = $job | Receive-Job
```

Perintah ini memulai perbaikan kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan. Langkah tersebut akan menunggu hingga perbaikan selesai sebelum mengembalikan status perbaikan akhir.

### Contoh 5: Mulai perbaikan yang akan menemukan sumber daya yang tidak sesuai sebelum memulihkan
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription "My Subscription"
PS C:\> Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ResourceDiscoveryMode ReEvaluateCompliance
```

Perintah ini membuat perbaikan kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan. Status kepatuhan sumber daya dalam langganan akan dievaluasi ulang terhadap penetapan kebijakan dan sumber daya yang tidak patuh akan diperbaiki.

### Contoh 6: Mulai perbaikan yang akan memulihkan hingga 10.000 sumber daya yang tidak memenuhi syarat
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription "My Subscription"
PS C:\> Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ResourceCount 10000
```

### Contoh 7: Mulai perbaikan yang akan memulihkan 30 sumber daya secara paralel
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription "My Subscription"
PS C:\> Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ParallelDeployments 30
```

### Contoh 8: Mulai perbaikan yang akan berakhir jika lebih dari setengah dari penyebaran perbaikan gagal
```
PS C:\> $policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
PS C:\> Select-AzSubscription -Subscription "My Subscription"
PS C:\> Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -FailureThreshold 0.5
```

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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

### -FailureThreshold
Angka antara 0,0 hingga 1,0 yang menyatakan ambang kegagalan persentase. Pemulihan akan gagal jika persentase operasi pemulihan yang gagal (misalnya, gagal dalam penyebaran) melebihi ambang batas ini.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocationFilter
Lokasi sumber daya yang harus disertakan dalam perbaikan.
Sumber daya yang tidak berada di lokasi tersebut tidak akan diperbaiki.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagementGroupName
ID grup manajemen.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParallelDeploymentCount
Berapa banyak sumber daya yang dapat diperbaiki kapan saja. Dapat digunakan untuk mengontrol kecepatan perbaikan. Jika tidak tersedia, nilai penyebaran paralel default digunakan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyAssignmentId
ID penetapan kebijakan.
Misalnya
'/subscriptions/{subscriptionId}/providers/Microsoft.Authorization/policyAssignments/{assignmentName}'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyDefinitionReferenceId
Mendapatkan ID referensi definisi kebijakan dari definisi individu yang sedang diperbaiki.
Diperlukan saat penetapan kebijakan menetapkan definisi kumpulan kebijakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceCount
Jumlah maksimum sumber daya yang tidak memenuhi syarat yang akan diperbaiki. Jika tidak disediakan, jumlah sumber daya default digunakan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceDiscoveryMode
Menjelaskan bagaimana tugas perbaikan akan menemukan sumber daya yang perlu diperbaiki.
ReEvaluateCompliance tidak didukung ketika memulihkan lingkup grup manajemen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ExistingNonCompliant, ReEvaluateCompliance

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lingkup
Lingkup sumber daya.
Misalnya
'/subscriptions/{subscriptionId}/resourceGroups/{rgName}'.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.Remediation.PSRemediation

## CATATAN

## RELATED LINKS
