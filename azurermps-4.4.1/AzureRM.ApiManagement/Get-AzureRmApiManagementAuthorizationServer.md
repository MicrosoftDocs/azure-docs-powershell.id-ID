---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: AzureRM.ApiManagement
ms.assetid: 8B0116E5-0AED-4050-BF11-1BFE65DB9436
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Get-AzureRmApiManagementAuthorizationServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Get-AzureRmApiManagementAuthorizationServer.md
ms.openlocfilehash: 3c37376aa475e8b0797d4ff4433ab54a11d2b6bb
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428642"
---
# Get-AzureRmApiManagementAuthorizationServer

## SYNOPSIS
Mendapatkan server otorisasi Manajemen API.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Dapatkan semua server otorisasi (Default)
```
Get-AzureRmApiManagementAuthorizationServer -Context <PsApiManagementContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Dapatkan dengan Id
```
Get-AzureRmApiManagementAuthorizationServer -Context <PsApiManagementContext> [-ServerId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmApiManagementAuthorizationServer** mendapatkan semua server otorisasi Manajemen API Azure atau server otorisasi yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan semua server otorisasi
```
PS C:\>Get-AzureRmApiManagementAuthrizarionServer -Context $ApiMgmtContext
```

Perintah ini akan mendapatkan semua server otorisasi Manajemen API.

### Contoh 2: Dapatkan server otorisasi tertentu
```
PS C:\>Get-AzureRmApiManagementCertificate -Context $ApiMgmtContext -ServerId "0123456789"
```

Perintah ini akan mendapatkan server otorisasi yang ditentukan.

## PARAMETERS

### -Konteks
```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerId
```yaml
Type: System.String
Parameter Sets: Get by Id
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### IList<Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementOAuth2AuthrozationServer>

## CATATAN

## RELATED LINKS

[New-AzureRmApiManagementAuthorizationServer](./New-AzureRmApiManagementAuthorizationServer.md)

[Remove-AzureRmApiManagementAuthorizationServer](./Remove-AzureRmApiManagementAuthorizationServer.md)

[Set-AzureRmApiManagementAuthorizationServer](./Set-AzureRmApiManagementAuthorizationServer.md)


