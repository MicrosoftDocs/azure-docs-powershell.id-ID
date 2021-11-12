---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 486748AC-3932-4E0C-BBCC-2BC194E69DCC
online version: https://docs.microsoft.com/en-us/powershell/module/az.batch/new-azbatchaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/New-AzBatchAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/New-AzBatchAccountKey.md
ms.openlocfilehash: 121e4b4b2ffe25d9e5ae53cb03e60cb7a1da91b2
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408212"
---
# New-AzBatchAccountKey

## SYNOPSIS
Meregenerasi kunci akun Kumpulan.

## SINTAKS

```
New-AzBatchAccountKey [-AccountName] <String> [-ResourceGroupName <String>] -KeyType <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzBatchAccountKey** meregenerasi kunci primer atau sekunder dari akun Azure Batch.
Cmdlet mengembalikan objek **BatchAccountContext yang** memiliki properti **PrimaryAccountKey dan** **SecondaryAccountKey saat** ini.

## CONTOH

### Contoh 1: Meregenerasi kunci akun utama pada akun Batch
```
PS C:\>New-AzBatchAccountKey -AccountName "pfuller" -KeyType "Primary"
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

Perintah ini meregenerasi kunci akun utama pada akun Kumpulan yang bernama pfuller.

## PARAMETERS

### -Nama Akun
Menentukan nama akun Kumpulan di mana cmdlet meregenerasi kunci.

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

### -KeyType
Menentukan tipe kunci yang meregenerasi cmdlet ini.
Nilai valid adalah:
- Utama
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
Menentukan grup sumber daya akun di mana cmdlet meregenerasi kunci.

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

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## CATATAN

## LINK TERKAIT

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
