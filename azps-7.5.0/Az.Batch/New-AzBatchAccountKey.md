---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 486748AC-3932-4E0C-BBCC-2BC194E69DCC
online version: https://docs.microsoft.com/powershell/module/az.batch/new-azbatchaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchAccountKey.md
ms.openlocfilehash: 4ef0bc6c008dfa9d57910fdddad8fb1608c5d2ec
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244996"
---
# New-AzBatchAccountKey

## SYNOPSIS
Meregenerasi kunci akun Batch.

## SYNTAX

```
New-AzBatchAccountKey [-AccountName] <String> [-ResourceGroupName <String>] -KeyType <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzBatchAccountKey** meregenerasi kunci primer atau sekunder dari akun Azure Batch.
Cmdlet mengembalikan objek **BatchAccountContext** yang memiliki properti **PrimaryAccountKey** dan **SecondaryAccountKey** saat ini.

## EXAMPLES

### Contoh 1: Meregenerasi kunci akun utama pada akun Batch
```powershell
New-AzBatchAccountKey -AccountName "pfuller" -KeyType "Primary"
```

```output
AccountName                  : pfuller
Location                     : westus
ResourceGroupName            : CmdletExampleRG
DedicatedCoreQuota           : 20
LowPriorityCoreQuota         : 20
PoolQuota                    : 20
ActiveJobAndJobScheduleQuota : 20
Tags                         :
TaskTenantUrl                : https://cmdletexample.westus.batch.azure.com
```

Perintah ini meregenerasi kunci akun utama pada akun Batch bernama pfuller.

## PARAMETERS

### -AccountName
Menentukan nama akun Batch yang cmdlet ini meregenerasi kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -KeyType
Menentukan jenis kunci yang diregenerasi cmdlet ini.
Nilai yang valid adalah:
- Primer
- Sekunder

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya akun yang cmdlet ini meregenerasi kunci.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
