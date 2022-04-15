---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 7CB42968-8F6F-4D84-9AE2-1000F280BF3C
online version: ''
schema: 2.0.0
ms.openlocfilehash: aca7a14e42ae79a6f536f38761e4740a8921ceab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245562"
---
# Get-AzureStorSimpleResourceContext

## SYNOPSIS
Mendapatkan konteks sumber daya saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleResourceContext [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleResourceContext** mendapatkan konteks sumber daya saat ini.

## EXAMPLES

### Contoh 1: Dapatkan konteks saat ini
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso63-Tsqa" 
PS C:\> Get-AzureStorSimpleResourceContext
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso63-Tsqa
```

Perintah pertama mengatur konteks saat ini menjadi sumber daya yang bernama Contoso63-Tsqa menggunakan cmdlet **Select-AzureStorSimpleResource** .

Perintah kedua mendapatkan konteks sumber daya saat ini.

### Contoh 2: Mencoba untuk mendapatkan konteks saat ini
```
PS C:\>Get-AzureStorSimpleResourceContext
Get-AzureStorSimpleResourceContext : Resource Context is not set for your subscription. Please use
Select-AzureStorSimpleResource -ResourceName <<name>> to set
```

Perintah ini mendapatkan konteks saat ini.
Dalam contoh ini, tidak ada konteks yang telah ditetapkan.
Perintah mengembalikan pesan yang menjelaskan masalah.

## PARAMETERS

### -Profil
Menentukan profil Azure.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### StorSimpleResourceContext
Cmdlet ini mengembalikan objek **ResourceContext** .

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleResource](./Get-AzureStorSimpleResource.md)

[Select-AzureStorSimpleResource](./Select-AzureStorSimpleResource.md)


