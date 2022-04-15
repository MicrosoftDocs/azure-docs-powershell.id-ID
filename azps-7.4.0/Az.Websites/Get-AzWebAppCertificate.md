---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 2D83D38F-3A5C-40DB-BE8B-D52E5CAFCF6E
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppCertificate.md
ms.openlocfilehash: 7308b9da699b397f17126b5edc1a47b44d0f0e8f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142419226"
---
# Get-AzWebAppCertificate

## SYNOPSIS
Mendapatkan sertifikat Azure Web App.

## SYNTAX

```
Get-AzWebAppCertificate [[-ResourceGroupName] <String>] [[-Thumbprint] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzWebAppCertificate** mendapatkan informasi tentang sertifikat Azure Web App yang terkait dengan grup sumber daya tertentu.
Jika Anda mengetahui sidik jari sertifikat, Anda juga bisa menggunakan cmdlet ini untuk mendapatkan informasi tentang sertifikat yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan sertifikat Web App dalam grup sumber daya
```powershell
Get-AzWebAppCertificate -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mengembalikan informasi tentang sertifikat Web App yang diunggah yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Mendapatkan sertifikat aplikasi web tertentu
```powershell
Get-AzWebAppCertificate -ResourceGroupName "ContosoResourceGroup" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini mendapatkan sertifikat ContosoResourceGroup Web App dengan sidik jari E3A38EBA60CAA1C162785A2E1C44A15AD450199C3.

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

### -Sidik jari
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.WebApps.Models.WebApp.PSCertificate

## CATATAN

## RELATED LINKS

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)


