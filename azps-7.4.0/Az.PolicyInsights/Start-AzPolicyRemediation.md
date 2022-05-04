---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/start-azpolicyremediation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyRemediation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyRemediation.md
ms.openlocfilehash: 900b7d3f9ea62058e5b542d80393b149a87c0ace
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144701384"
---
# Start-AzPolicyRemediation

## SYNOPSIS
Membuat dan memulai remediasi kebijakan untuk penetapan kebijakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.policyinsights/start-azpolicyremediation) untuk informasi terbaru.

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
Cmdlet **Start-AzPolicyRemediation** membuat remediasi kebijakan untuk penetapan kebijakan tertentu. Semua sumber daya yang tidak sesuai pada atau di bawah cakupan remediasi akan diperbaiki. Remediasi hanya didukung untuk kebijakan dengan efek 'deployIfNotExists'.

## EXAMPLES

### Contoh 1: Memulai remediasi pada cakupan langganan
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription "My Subscription"
Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1"
```

Perintah ini membuat remediasi kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan.

### Contoh 2: Memulai remediasi di cakupan grup manajemen dengan filter opsional
```powershell
$policyAssignmentId = "/providers/Microsoft.Management/managementGroups/mg1/providers/Microsoft.Authorization/policyAssignments/pa1"
Start-AzPolicyRemediation -ManagementGroupName "mg1" -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -LocationFilter "westus","eastus"
```

Perintah ini membuat remediasi kebijakan baru di grup manajemen 'mg1' untuk penetapan kebijakan yang diberikan. Hanya sumber daya di lokasi 'westus' atau 'eastus' yang akan diperbaiki.

### Contoh 3: Memulai remediasi di cakupan grup sumber daya untuk penetapan definisi kumpulan kebijakan
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/resourceGroups/myRG/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Start-AzPolicyRemediation -ResourceGroupName "myRG" -PolicyAssignmentId $policyAssignmentId -PolicyDefinitionReferenceId "0349234412441" -Name "remediation1"
```

Perintah ini membuat remediasi kebijakan baru di grup sumber daya 'myRG' untuk penetapan kebijakan yang diberikan. Penetapan kebijakan menetapkan definisi yang ditetapkan kebijakan (juga dikenal sebagai inisiatif). ID referensi definisi kebijakan menunjukkan kebijakan mana dalam inisiatif yang harus diperbaiki.

### Contoh 4: Mulai remediasi dan tunggu hingga selesai di latar belakang
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription f0710c27-9663-4c05-19f8-1b4be01e86a5
$job = Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -AsJob
$job | Wait-Job
$remediation = $job | Receive-Job
```

Perintah ini memulai remediasi kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan. Ini akan menunggu remediasi selesai sebelum mengembalikan status remediasi akhir.

### Contoh 5: Memulai remediasi yang akan menemukan sumber daya yang tidak sesuai sebelum memulihkan
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription "My Subscription"
Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ResourceDiscoveryMode ReEvaluateCompliance
```

Perintah ini membuat remediasi kebijakan baru dalam langganan 'Langganan Saya' untuk penetapan kebijakan yang diberikan. Status kepatuhan sumber daya dalam langganan akan dievaluasi kembali terhadap penetapan kebijakan dan sumber daya yang tidak patuh akan diperbaiki.

### Contoh 6: Memulai remediasi yang akan memulihkan hingga 10.000 sumber daya yang tidak patuh
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription "My Subscription"
Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ResourceCount 10000
```

### Contoh 7: Memulai remediasi yang akan memulihkan 30 sumber daya secara paralel
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription "My Subscription"
Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -ParallelDeployments 30
```

### Contoh 8: Mulai remediasi yang akan berakhir jika lebih dari setengah penyebaran remediasi gagal
```powershell
$policyAssignmentId = "/subscriptions/f0710c27-9663-4c05-19f8-1b4be01e86a5/providers/Microsoft.Authorization/policyAssignments/2deae24764b447c29af7c309"
Select-AzSubscription -Subscription "My Subscription"
Start-AzPolicyRemediation -PolicyAssignmentId $policyAssignmentId -Name "remediation1" -FailureThreshold 0.5
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
Angka antara 0,0 hingga 1,0 yang menunjukkan ambang kegagalan persentase. Remediasi akan gagal jika persentase operasi remediasi yang gagal (yaitu penyebaran yang gagal) melebihi ambang batas ini.

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
Lokasi sumber daya yang harus disertakan dalam remediasi.
Sumber daya yang tidak berada di lokasi ini tidak akan diperbaiki.

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

### -Name
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
Berapa banyak sumber daya yang akan diperbaiki pada waktu tertentu. Dapat digunakan untuk mengontrol laju remediasi. Jika tidak disediakan, nilai penyebaran paralel default digunakan.

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
Mis.
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
Diperlukan saat penetapan kebijakan menetapkan definisi yang ditetapkan kebijakan.

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
Jumlah maksimum sumber daya yang tidak sesuai yang akan diperbaiki. Jika tidak disediakan, jumlah sumber daya default digunakan.

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
Menjelaskan bagaimana tugas remediasi akan menemukan sumber daya yang perlu diperbaiki.
ReEvaluateCompliance tidak didukung saat memulihkan cakupan grup manajemen.

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

### -Cakupan
Cakupan sumber daya.
Mis.
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.Remediation.PSRemediation

## NOTES

## RELATED LINKS
