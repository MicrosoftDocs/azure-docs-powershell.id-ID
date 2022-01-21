---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azstaticwebappfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebAppFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebAppFunction.md
ms.openlocfilehash: 2b342dc1d79ad313423842eacffdf00143158414
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136572390"
---
# Get-AzStaticWebAppFunction

## SYNOPSIS
Deskripsi untuk Mendapatkan fungsi situs statis.

## SYNTAX

```
Get-AzStaticWebAppFunction -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Mendapatkan fungsi situs statis.

## EXAMPLES

### Contoh 1: Mendapatkan fungsi situs statis
```powershell
PS C:\>  Get-AzStaticWebAppFunction -ResourceGroupName azure-rg-test -Name staticweb-portal04

```

Perintah ini mendapatkan fungsi dari situs statis.

## PARAMETERS

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

### -Nama
Nama situs statis.

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

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya tersebut berada.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteFunctionOverviewArmResource

## CATATAN

ALIAS

## RELATED LINKS

