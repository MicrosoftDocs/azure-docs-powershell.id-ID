---
external help file: Microsoft.Azure.Commands.Management.CognitiveServices.dll-Help.xml
Module Name: AzureRM.CognitiveServices
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.cognitiveservices/get-azurermcognitiveservicesaccounttype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/CognitiveServices/Commands.Management.CognitiveServices/help/Get-AzureRmCognitiveServicesAccountType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/CognitiveServices/Commands.Management.CognitiveServices/help/Get-AzureRmCognitiveServicesAccountType.md
ms.openlocfilehash: bfc0cac22a212b1482daa982e3f39a018c79e6a11f02a1fc835df595f3d666f2
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140854437"
---
# Get-AzureRmCognitiveServicesAccountType

## SYNOPSIS
Dapatkan Tipe Akun Layanan Kognitif yang tersedia.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetAccountTypeWithName
```
Get-AzureRmCognitiveServicesAccountType -TypeName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetAccountTypes
```
Get-AzureRmCognitiveServicesAccountType [-Location <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmCognitiveServicesAccountType** mendapatkan Tipe Akun Layanan Kognitif yang tersedia di bawah langganan ini.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzureRmCognitiveServicesAccountType
```

Mendapatkan daftar Tipe yang tersedia.

### Contoh 2
```powershell
PS C:\> Get-AzureRmCognitiveServicesAccountType -Location westus
```

Dapatkan daftar Tipe yang tersedia di westus.

### Contoh 3
```powershell
PS C:\> Get-AzureRmCognitiveServicesAccountType -TypeName Face

Face
```

Periksa apakah `Face` nama Tipe yang valid, nama tersebut akan dikembalikan jika merupakan nama yang valid.

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

### -Lokasi
Lokasi Akun Layanan Kognitif.

```yaml
Type: System.String
Parameter Sets: GetAccountTypes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeName
Nama Tipe Akun Layanan Kognitif.

```yaml
Type: System.String
Parameter Sets: GetAccountTypeWithName
Aliases: CognitiveServicesAccountTypeName, AccountTypeName, KindName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.String[]

### System.String

## CATATAN

## RELATED LINKS
