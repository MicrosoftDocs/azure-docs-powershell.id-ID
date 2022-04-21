---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
Module Name: AzureRM.Storage
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.storage/get-azurermstorageaccountnetworkruleset
schema: 2.0.0
ms.openlocfilehash: 8e3aa3bd313947712ef3831b83c75bb1349adb4f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142797093"
---
# Get-AzureRmStorageAccountNetworkRuleSet

## SYNOPSIS
Dapatkan properti NetWorkRule dari akun Storage

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmStorageAccountNetworkRuleSet [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmStorageAccountNetworkRuleSet** mendapatkan properti NetworkRule dari akun Storage

## EXAMPLES

### Contoh 1: Dapatkan properti NetworkRule dari akun Storage tertentu
```
PS C:\> Get-AzureRmStorageAccountNetworkRuleSet  -ResourceGroupName "rg1" -AccountName "mystorageaccount"
```

Perintah ini mendapatkan properti NetworkRule dari akun Storage yang ditentukan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun Storage.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya berisi akun Storage.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSNetworkRuleSet

## NOTES

## RELATED LINKS
