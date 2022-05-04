---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/send-feedback
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Send-Feedback.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Send-Feedback.md
ms.openlocfilehash: ad910a1ad58722fd15e53e8c7a9193017628faed
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144634958"
---
# Kirim-Tanggapan

## SYNOPSIS
Mengirim umpan balik ke tim Azure PowerShell melalui serangkaian perintah terpandu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/send-feedback) untuk informasi terbaru.

## SYNTAX

```
Send-Feedback [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Send-Feedback mengirimkan umpan balik ke tim Azure PowerShell.

## EXAMPLES

### Contoh 1:
```powershell
Send-Feedback
```

```Output
With zero (0) being the least and ten (10) being the most, how likely are you to recommend Azure PowerShell to a friend or colleague?

10

What does Azure PowerShell do well?

Response.

Upon what could Azure PowerShell improve?

Response.

Please enter your email if you are interested in providing follow up information:

your@email.com
```

## PARAMETERS

### -DefaultProfile
Kredensial, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS
