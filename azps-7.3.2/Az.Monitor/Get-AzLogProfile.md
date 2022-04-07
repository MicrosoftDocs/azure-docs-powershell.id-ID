---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 019EFD94-4087-45F6-812D-FBDFE1B2E48A
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azlogprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzLogProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzLogProfile.md
ms.openlocfilehash: 81ecf35032e6e0eab1b222f52e0d8b17c1544357
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140401866"
---
# Get-AzLogProfile

## SYNOPSIS
Mendapatkan profil log.

## SYNTAX

```
Get-AzLogProfile [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzLogProfile** mendapatkan profil log.

## EXAMPLES
### Contoh 1: Mendapatkan profil log
```
PS C:\>Get-AzLogProfile
StorageAccountId : /subscriptions/xxxx-xxxx-xxxx-xxxx-xxxx/resourceGroups/testrg/providers/Microsoft.Stor
age/storageAccounts/storageaccount
ServiceBusRuleId :
Locations
     : eastus
Categories
     : Delete
     : Write
     : Action
RetentionPolicy
Enabled : False
Days    : 0

Id               :
/subscriptions/xxxx-xxxx-xxxx-xxxx-xxxx/providers/microsoft.insights/logprofiles/exportlogprofile
Name             : exportlogprofile
Type             :
Location         :
Tags             :
Kind             :
Etag             :
```

Perintah ini akan mendapatkan profil log.
## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama profil log untuk mendapatkannya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfileCollection

## CATATAN

## RELATED LINKS

[Add-AzLogProfile](./Add-AzLogProfile.md)

[Remove-AzLogProfile](./Remove-AzLogProfile.md)


