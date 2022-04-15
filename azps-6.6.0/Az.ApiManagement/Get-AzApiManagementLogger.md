---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: A935ABAC-6C60-4AE3-9434-B9BCC1182A34
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/get-azapimanagementlogger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementLogger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementLogger.md
ms.openlocfilehash: 1463d84a00f382daa042d0f938acee56ef003cda
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142307959"
---
# Get-AzApiManagementLogger

## SYNOPSIS
Mendapatkan objek API Management Logger.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/get-azapimanagementlogger) untuk informasi terbaru.

## SYNTAX

### GetAllLoggers (Default)
```
Get-AzApiManagementLogger -Context <PsApiManagementContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByLoggerId
```
Get-AzApiManagementLogger -Context <PsApiManagementContext> -LoggerId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApiManagementLogger** mendapatkan Azure API Management **Logger** atau semua logger.

## EXAMPLES

### Contoh 1: Dapatkan semua logger
```
PS C:\>$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
PS C:\>Get-AzApiManagementLogger -Context $apimContext
```

Perintah ini mendapatkan semua logger untuk konteks yang ditentukan.

### Contoh 2: Dapatkan logger tertentu
```
PS C:\>$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
PS C:\>Get-AzApiManagementLogger -Context $apimContext -LoggerId "Logger123"
```

Perintah ini menghapus logger yang memiliki ID Logger123.

## PARAMETERS

### -Konteks
Menentukan objek **PsApiManagementContext** .

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

### -LoggerId
Menentukan ID dari logger tertentu untuk didapatkan.

```yaml
Type: System.String
Parameter Sets: GetByLoggerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementLogger

## CATATAN

## RELATED LINKS

[New-AzApiManagementLogger](./New-AzApiManagementLogger.md)

[Remove-AzApiManagementLogger](./Remove-AzApiManagementLogger.md)

[Set-AzApiManagementLogger](./Set-AzApiManagementLogger.md)


