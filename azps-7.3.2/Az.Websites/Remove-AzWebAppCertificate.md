---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/remove-AzWebAppCertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppCertificate.md
ms.openlocfilehash: 64241f9c4307bc5c663254cb2a320d66286da375
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142363697"
---
# Remove-AzWebAppCertificate

## SYNOPSIS
Menghapus sertifikat terkelola layanan Aplikasi untuk Azure Web App. 

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/remove-azwebappcertificate) untuk informasi terbaru.

## SYNTAX

```
Remove-AzWebAppCertificate [-ResourceGroupName] <String> [-ThumbPrint] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzWebAppCertificate** Menghapus Sertifikat yang Dikelola Azure App Service

## EXAMPLES

### Contoh 1
```powershell
PS C:\>Remove-AzWebAppCertificate -ResourceGroupName Default-Web-WestUS -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" 
```

Perintah ini menghapus sertifikat App Service Dikelola untuk aplikasi web tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThumbPrint
Sidik jari sertifikat yang sudah ada di ruang web.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS
[New-AzWebAppCertificate](./New-AzWebAppCertificate.md)
