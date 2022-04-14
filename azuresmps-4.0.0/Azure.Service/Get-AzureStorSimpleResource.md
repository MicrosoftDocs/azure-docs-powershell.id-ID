---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 482E8CD6-C38F-4BD5-8214-016D0D8C7FD0
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7d28b0bb94372128fd47bd2e2645cb8c2f66cb49
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141966147"
---
# Get-AzureStorSimpleResource

## SYNOPSIS
Mendapatkan semua sumber daya yang Anda buat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleResource [-ResourceName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleResource** mendapatkan semua sumber daya yang Anda buat dengan menggunakan Portal Azure.
Cmdlet mendapatkan detail yang dapat Anda gunakan untuk menyambungkan ke sumber daya.

## EXAMPLES

### Contoh 1: Dapatkan semua sumber daya
```
PS C:\>Get-AzureStorSimpleResource
VERBOSE: ClientRequestId: 5cd61b91-ef40-43b4-986d-156e06d2ed65_PS

ResourceName                                      ResourceId           ResourceState
------------                                      ----------           -------------
Contoso63-Tsqa                                    8838459798595306468  Started
Contoso68-Tsqa                                    2859070203638134681  Started
Contoso73-Tsqa                                    7871392677286863733  Started
Contoso87-Tsqa                                    1909806764156522689  Started
VERBOSE: Found 4 StorSimple resources.
```

Perintah ini mendapatkan semua sumber daya yang Anda buat.
Dalam contoh ini, ada tiga sumber daya.

### Contoh 2: Dapatkan sumber daya menggunakan namanya
```
PS C:\>Get-AzureStorSimpleResource -ResourceName "Contoso63-Tsqa"
VERBOSE: ClientRequestId: efc3c85c-12aa-4345-b6eb-ccc532de4825_PS

ResourceName                                      ResourceId           ResourceState
------------                                      ----------           -------------
Contoso63-Tsqa                                    1909806764156522689  Started
VERBOSE: Found 1 StorSimple resource.
```

Perintah ini mendapatkan sumber daya bernama Contoso63-Tsqa.

### Contoh 3: Mencoba mendapatkan sumber daya yang tidak ada
```
PS C:\>Get-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa"
VERBOSE: ClientRequestId: 5d08d40b-f9d7-4d43-956f-13f01e89625b_PS
VERBOSE: Invalid input : Could not find a resource named Contoso64-Tsqa in your subscription.
```

Perintah ini berusaha mendapatkan sumber daya bernama Contoso64-Tsqa.
Tidak ada sumber daya yang memiliki nama ini.
Contoh ini tidak mengembalikan sumber daya apa pun.

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

### -ResourceName
Menentukan nama sumber daya yang didapat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

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

### IEnumerable\<ResourceCredentials\>, ResourceCredentials
Cmdlet ini mengembalikan objek **ResourceCredentials** yang berisi properti berikut: 

- **NamaPengguna Sumber Daya**
- **ResouceId**
- **ResourceState**

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleResourceContext](./Get-AzureStorSimpleResourceContext.md)

[Select-AzureStorSimpleResource](./Select-AzureStorSimpleResource.md)


