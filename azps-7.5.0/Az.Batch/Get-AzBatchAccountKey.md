---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: AFDE5ECD-29AB-4C91-98BF-1B8C9C3BB079
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchAccountKey.md
ms.openlocfilehash: e2536a8fecdd4cf161bac7d0ffa169e765a79955
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144214307"
---
# Get-AzBatchAccountKey

## SYNOPSIS
Mendapatkan kunci akun Batch.

## SYNTAX

```
Get-AzBatchAccountKey [-AccountName] <String> [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchAccountKey** mendapatkan kunci akun Azure Batch dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan kunci akun batch dan simpan dalam variabel $Context untuk digunakan nanti
```powershell
$Context = Get-AzBatchAccountKey -AccountName myaccount
```

Perintah ini mendapatkan detail akun dan menyimpannya dalam `$Context` objek untuk digunakan nanti.

### Contoh 2: Mendapatkan kunci akun batch dan menampilkannya
```powershell
$Context = Get-AzBatchAccountKey -AccountName myaccount
$Context.PrimaryAccountKey
ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789ABCDEFGHIJKLMN==
$Context.SecondaryAccountKey
ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789ABCDEFGHIJKLMN==
```

Perintah ini mendapatkan kunci akun dan mencetaknya ke konsol.

## PARAMETERS

### -AccountName
Menentukan nama akun yang cmdlet ini mendapatkan kunci.

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi akun tempat cmdlet ini mendapatkan kunci.

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

[New-AzBatchAccountKey](./New-AzBatchAccountKey.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
