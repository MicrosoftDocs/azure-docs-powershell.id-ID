---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Relay.dll-Help.xml
Module Name: Az.Relay
online version: https://docs.microsoft.com/powershell/module/az.relay/test-azrelayname
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Relay/Relay/help/Test-AzRelayName.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Relay/Relay/help/Test-AzRelayName.md
ms.openlocfilehash: b3e1dc61e683310bed57a890bcd49947c2e6730b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990642"
---
# Test-AzRelayName

## SYNOPSIS
Memeriksa Ketersediaan Nama NameSpace yang diberikan

## SYNTAX

```
Test-AzRelayName [-Namespace] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzRelayName** Memeriksa Ketersediaan Nama NameSpace

## EXAMPLES

### Contoh 1
```powershell
Test-AzRelayName -Namespace TestingtheAvailability
```

```output
NameAvailable Reason Message
------------- ------ -------
         True   None
```

### Contoh 2
```powershell
Test-AzRelayName -Namespace Testi
```

```output
NameAvailable      Reason Message
-------------      ------ -------
        False InvalidName The specified service namespace is invalid.
```

### Contoh 3
```powershell
Test-AzRelayName -Namespace Test123
```

```output
NameAvailable    Reason Message
-------------    ------ -------
        False NameInUse The specified service namespace is not available.
```

Mengembalikan status ketersediaan nama ruang nama

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

### -Namespace
Relai Nama Ruang Nama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Relay.Models.PSCheckNameAvailabilityResultAttributes

## CATATAN

## RELATED LINKS
