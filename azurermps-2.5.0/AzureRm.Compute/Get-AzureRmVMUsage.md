---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 3702701E-428D-47E2-A227-0F38B055F881
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/get-azurermvmusage
schema: 2.0.0
ms.openlocfilehash: 7038f86b2a1a0123ea567b7823506d0171a0178d041f416dfa53057956eb6eef
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419357"
---
# Get-AzureRmVMUsage

## SYNOPSIS
Dapatkan penggunaan jumlah inti mesin virtual untuk suatu lokasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVMUsage [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVMUsage** mendapatkan penggunaan jumlah inti mesin virtual untuk suatu lokasi.

## EXAMPLES

### Contoh 1: Mendapatkan penggunaan jumlah inti untuk suatu lokasi
```
PS C:\> Get-AzureRmVMUsage -Location "Central US"
```

Perintah ini akan menggunakan jumlah inti mesin virtual untuk lokasi AS Pusat.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi di mana cmdlet ini mendapatkan penggunaan jumlah inti mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSUsage

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)


