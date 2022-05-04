---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 2D83D38F-3A5C-40DB-BE8B-D52E5CAFCF6E
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppCertificate.md
ms.openlocfilehash: 3c455a8e3c3127cfb0fcb7e816de43adcb253395
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144639348"
---
# Get-AzWebAppCertificate

## SYNOPSIS
Mendapatkan sertifikat Azure Web App.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.websites/get-azwebappcertificate) untuk informasi terbaru.

## SYNTAX

```
Get-AzWebAppCertificate [[-ResourceGroupName] <String>] [[-Thumbprint] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzWebAppCertificate** mendapatkan informasi tentang sertifikat Azure Web App yang terkait dengan grup sumber daya tertentu.
Jika Anda mengetahui thumbprint sertifikat, Anda juga dapat menggunakan cmdlet ini untuk mendapatkan informasi tentang sertifikat tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan sertifikat Aplikasi Web dalam grup sumber daya
```powershell
Get-AzWebAppCertificate -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mengembalikan informasi tentang sertifikat Aplikasi Web yang diunggah yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Mendapatkan sertifikat aplikasi web tertentu
```powershell
Get-AzWebAppCertificate -ResourceGroupName "ContosoResourceGroup" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini mendapatkan sertifikat Aplikasi Web ContosoResourceGroup dengan thumbprint E3A38EBA60CAA1C162785A2E1C44A15AD450199C3.

## PARAMETERS

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
Menentukan nama grup sumber daya tempat sertifikat ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Menentukan pengidentifikasi unik untuk sertifikat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.WebApps.Models.WebApp.PSCertificate

## NOTES

## RELATED LINKS

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)


