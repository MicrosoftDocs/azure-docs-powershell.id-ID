---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/en-us/powershell/module/az.policyinsights/start-azpolicycompliancescan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyComplianceScan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PolicyInsights/PolicyInsights/help/Start-AzPolicyComplianceScan.md
ms.openlocfilehash: 61022603ad34c345274328d47767e90580e54d6b
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136012570"
---
# Start-AzPolicyComplianceScan

## SYNOPSIS
Memicu evaluasi kepatuhan kebijakan untuk semua sumber daya dalam langganan atau grup sumber daya.

## SINTAKS

```
Start-AzPolicyComplianceScan [-ResourceGroupName <String>] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Start-AzPolicyComplianceScan** memulai evaluasi kepatuhan kebijakan untuk langganan atau grup sumber daya. Semua sumber daya dalam lingkup tersebut akan memiliki status kepatuhan mereka yang dievaluasi terhadap semua kebijakan yang ditetapkan.

## CONTOH

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

## INPUT

### System.String

## OUTPUT

### System.Boolean

## CATATAN

## LINK TERKAIT
