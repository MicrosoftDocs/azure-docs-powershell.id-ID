---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappwebjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppWebJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppWebJob.md
ms.openlocfilehash: 7b9555eda1a1317ea53986b889dce7ba43e79b02
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144620994"
---
# Get-AzWebAppWebJob

## SYNOPSIS
Mencantumkan webjobs untuk aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.websites/get-azwebappwebjob) untuk informasi terbaru.

## SYNTAX

```
Get-AzWebAppWebJob -AppName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan webjobs untuk aplikasi.

## EXAMPLES

### Contoh 1: Mencantumkan webjobs untuk aplikasi
```powershell
PS C:\> Get-AzWebAppWebJob -ResourceGroupName webjob-rg-test -AppName appService-test01 

Name                               Kind WebJobType
----                               ---- ----------
appService-test01/triggeredjob-01
appService-test01/triggeredjob-02
appService-test01/continuousjob-01
appService-test01/continuousjob-02
```

Perintah ini mencantumkan webjobs untuk aplikasi.

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

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000).

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20210201.IWebJob

## NOTES

ALIAS

## RELATED LINKS
