---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappslotwebjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSlotWebJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSlotWebJob.md
ms.openlocfilehash: afa3d3a58cf7c35a6de07272301192caa94839bf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143169929"
---
# Get-AzWebAppSlotWebJob

## SYNOPSIS
Daftar webjobs untuk slot penyebaran.

## SYNTAX

```
Get-AzWebAppSlotWebJob -AppName <String> -ResourceGroupName <String> -SlotName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Daftar webjobs untuk slot penyebaran.

## EXAMPLES

### Contoh 1: Daftar webjobs untuk slot penyebaran
```powershell
PS C:\> Get-AzWebAppSlotWebJob -ResourceGroupName webjob-rg-test -AppName appService-test01 -SlotName slot01

Name                                          Kind WebJobType ResourceGroupName
----                                          ---- ---------- -----------------
appService-test01/slot01/slottriggeredjob-03                  webjob-rg-test
appService-test01/slot01/slottriggeredjob-04                  webjob-rg-test
appService-test01/slot01/slotcontinuousjob-03                 webjob-rg-test
appService-test01/slot01/slotcontinuousjob-04                 webjob-rg-test
```

Perintah ini mencantumkan webjob untuk slot penyebaran.

## PARAMETERS

### -AppName
Nama situs.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya berada.

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

### -SlotName
Nama slot penyebaran.
Jika slot tidak ditentukan, API mengembalikan penyebaran untuk slot produksi.

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

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20210201.IWebJob

## NOTES

ALIAS

## RELATED LINKS
