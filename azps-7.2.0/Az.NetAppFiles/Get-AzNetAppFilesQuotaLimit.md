---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/get-aznetappfilesquotalimit
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesQuotaLimit.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesQuotaLimit.md
ms.openlocfilehash: 8fdd0b8885af9d422d114f7d45983b73fda36975
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138271339"
---
# Get-AzNetAppFilesQuotaLimit

## SYNOPSIS
Dapatkan batas kuota

## SYNTAX

```
Get-AzNetAppFilesQuotaLimit -Location <String> [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan batasan default dan saat ini untuk kuota Azure NetApp Files (ANF)

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzNetAppFilesQuotaLimit -Location "westus2"  -Name totalTiBsPerSubscription

Output

Name                             Current Default
----                             ------- -------
westus2/totalTiBsPerSubscription      25      25
```

Perintah ini mendapatkan Batas Kuota bernama totalTiBsPerSubscription

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

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Batas Kuota

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: QuotaLimitName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesSubscriptionQuotaLimit

## CATATAN

## RELATED LINKS
