---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/get-aznetappfilesaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesAccount.md
ms.openlocfilehash: 49e778d2bd3c21ed79cd67c87610eae9e23d8e1a
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145803822"
---
# Get-AzNetAppFilesAccount

## SYNOPSIS
Mendapatkan detail akun Azure NetApp Files (ANF).

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.netappfiles/get-aznetappfilesaccount) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzNetAppFilesAccount -ResourceGroupName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzNetAppFilesAccount -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetAppFilesAccount** mendapatkan detail akun ANF.

## EXAMPLES

### Contoh 1: Mendapatkan akun ANF
```powershell
Get-AzNetAppFilesAccount -ResourceGroupName "MyRG" -Name "MyAnfAccount"
```

```output
Location          : westus2
Id                : /subscriptions/mySubs/resourceGroups/MyRG/providers/Microsoft.NetApp/netAppAccounts/MyAnfAccount
Name              : MyAnfAccount
Type              : Microsoft.NetApp/netAppAccounts
Tags              :
ProvisioningState : Succeeded
```

Perintah ini mendapatkan akun bernama MyAnfAccount.

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

### -Name
Nama akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases: AccountName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya akun ANF

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount

## NOTES

## RELATED LINKS
