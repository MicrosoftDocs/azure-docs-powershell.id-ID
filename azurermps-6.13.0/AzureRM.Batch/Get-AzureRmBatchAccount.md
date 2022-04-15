---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 818D5D85-B6D5-458C-A26E-E4DE8E111A10
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/get-azurermbatchaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchAccount.md
ms.openlocfilehash: ddc3bab48e766f80375fdf98add15e16e0086fee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142143338"
---
# Get-AzureRmBatchAccount

## SYNOPSIS
Mendapatkan akun Batch dalam langganan saat ini.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBatchAccount [[-AccountName] <String>] [[-ResourceGroupName] <String>] [[-Tag] <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBatchAccount** mendapatkan akun Azure Batch dalam langganan saat ini. Anda dapat menggunakan parameter *AccountName* untuk mendapatkan satu akun, atau menggunakan parameter *ResourceGroupName* untuk mendapatkan akun di bawah grup sumber daya tersebut.

## EXAMPLES

### Contoh 1: Dapatkan akun batch berdasarkan nama
```
PS C:\>Get-AzureRmBatchAccount -AccountName "pfuller"
AccountName                  : pfuller
Location                     : westus
ResourceGroupName            : CmdletExampleRG
CoreQuota                    : 20
PoolQuota                    : 20
ActiveJobAndJobScheduleQuota : 20
Tags                         :
TaskTenantUrl                : https://pfuller.westus.batch.azure.com
```

Perintah ini mendapatkan akun batch bernama pfuller.

### Contoh 2: Dapatkan akun kumpulan yang terkait dengan grup sumber daya
```
PS C:\>Get-AzureRmBatchAccount -ResourceGroupName "CmdletExampleRG"
AccountName                  : cmdletexample
Location                     : westus
ResourceGroupName            : CmdletExampleRG
CoreQuota                    : 20
PoolQuota                    : 20
ActiveJobAndJobScheduleQuota : 20
Tags                         :
TaskTenantUrl                : https://cmdletexample.westus.batch.azure.com
AccountName                  : cmdletexample2
Location                     : westus
ResourceGroupName            : CmdletExampleRG
CoreQuota                    : 20
PoolQuota                    : 20
ActiveJobAndJobScheduleQuota : 20
Tags                         :
TaskTenantUrl                : https://cmdletexample.westus.batch.azure.com
```

Perintah ini mendapatkan akun kumpulan yang terkait dengan grup sumber daya CmdletExampleRG.

## PARAMETERS

### -AccountName
Menentukan nama akun.
Jika Anda menentukan nama akun, cmdlet ini hanya mengembalikan akun tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -ResourceGroupName
Menentukan nama grup sumber daya.
Jika Anda menentukan grup sumber daya, cmdlet ini akan mendapatkan akun di bawah grup sumber daya tertentu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Cmdlet ini mendapatkan akun yang berisi tag yang ditentukan parameter ini.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## CATATAN

## RELATED LINKS

[AzureRmBatchAccount baru](./New-AzureRmBatchAccount.md)

[Hapus-AzureRmBatchAccount](./Remove-AzureRmBatchAccount.md)

[Set-AzureRmBatchAccount](./Set-AzureRmBatchAccount.md)

[Cmdlet Azure Batch](./AzureRM.Batch.md)
