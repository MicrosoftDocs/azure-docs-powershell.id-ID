---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/start-azpolicycompliancescan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyComplianceScan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyComplianceScan.md
ms.openlocfilehash: fbf8e002ee69ffdfe7133b7e323ca32a402e5fe1
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136389533"
---
# Start-AzPolicyComplianceScan

## SYNOPSIS
Memicu evaluasi kepatuhan kebijakan untuk semua sumber daya dalam langganan atau grup sumber daya.

## SYNTAX

```
Start-AzPolicyComplianceScan [-ResourceGroupName <String>] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzPolicyComplianceScan** memulai evaluasi kepatuhan kebijakan untuk langganan atau grup sumber daya. Semua sumber daya dalam lingkup tersebut akan memiliki status kepatuhan mereka yang dievaluasi terhadap semua kebijakan yang ditetapkan.

## EXAMPLES

### Contoh 1: Mulai pemindaian kepatuhan di lingkup langganan
```
PS C:\> Start-AzPolicyComplianceScan
```

Perintah ini memulai evaluasi kepatuhan kebijakan untuk langganan aktif.

### Contoh 2: Mulai pemindaian kepatuhan pada lingkup grup sumber daya
```
PS C:\> Start-AzPolicyComplianceScan -ResourceGroupName "myRG"
```

Perintah ini memulai evaluasi kepatuhan kebijakan untuk grup sumber daya "myRG" dalam langganan aktif.

### Contoh 3: Mulai pemindaian kepatuhan dan tunggu hingga selesai di latar belakang
```
PS C:\> $job = Start-AzPolicyComplianceScan -AsJob
PS C:\> $job | Wait-Job
```

Perintah ini memulai evaluasi kepatuhan kebijakan untuk langganan aktif. Proses ini akan menunggu hingga pindaian selesai.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

```yaml
Type: SwitchParameter
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan True jika perintah berhasil diselesaikan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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
Type: String
Parameter Sets: (All)
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### System.Boolean

## CATATAN

## RELATED LINKS
