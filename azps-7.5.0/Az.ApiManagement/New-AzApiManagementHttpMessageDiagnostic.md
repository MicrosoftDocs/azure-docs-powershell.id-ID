---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementhttpmessagediagnostic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementHttpMessageDiagnostic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementHttpMessageDiagnostic.md
ms.openlocfilehash: 2b499de6d6c88a62df20cb4d881538253a8cadbe
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145817352"
---
# New-AzApiManagementHttpMessageDiagnostic

## SYNOPSIS
Membuat **instans PsApiManagementHttpMessageDiagnostic** yang merupakan pengaturan diagnostik Pesan Http dari Diagnostik

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementhttpmessagediagnostic) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementHttpMessageDiagnostic [-HeadersToLog <String[]>] [-BodyBytesToLog <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementHttpMessageDiagnostic membuat pengaturan diagnostik** Pesan Http.

## EXAMPLES

### Contoh 1: Membuat Pengaturan diagnostik Pesan Http Dasar
```powershell
New-AzApiManagementHttpMessageDiagnostic -HeadersToLog 'Content-Type', 'UserAgent' -BodyBytesToLog 100
```

```output
Headers                   Body
-------                   ----
{Content-Type, UserAgent} Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementBodyDiagnosticSetting
```

Membuat pengaturan diagnostik pesan http untuk mencatat `Content-Type` dan `User-Agent` header bersama dengan 100 byte `body`

## PARAMETERS

### -BodyBytesToLog
Jumlah byte isi permintaan untuk dicatat. Parameter ini bersifat opsional.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -HeadersToLog
Array header yang akan dicatat. Parameter ini bersifat opsional.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementHttpMessageDiagnostic

## NOTES

## RELATED LINKS

[New-AzApiManagementDiagnostic](./New-AzApiManagementDiagnostic.md)

[New-AzApiManagementSamplingSetting](./New-AzApiManagementHttpMessageDiagnostic.md)
