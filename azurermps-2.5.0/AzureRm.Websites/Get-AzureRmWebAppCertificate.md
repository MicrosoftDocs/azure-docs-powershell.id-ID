---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM.WebSites
ms.assetid: 2D83D38F-3A5C-40DB-BE8B-D52E5CAFCF6E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/get-azurermwebappcertificate
schema: 2.0.0
ms.openlocfilehash: dcdba23de872ed0f1518188387c6f7e2d357c909
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142797012"
---
# Get-AzureRmWebAppCertificate

## SYNOPSIS
Mendapatkan sertifikat Azure Web App.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmWebAppCertificate [[-ResourceGroupName] <String>] [[-Thumbprint] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmWebAppCertificate** mendapatkan informasi tentang sertifikat Azure Web App yang terkait dengan grup sumber daya tertentu.
Jika Anda mengetahui sidik jari sertifikat, Anda juga bisa menggunakan cmdlet ini untuk mendapatkan informasi tentang sertifikat yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan sertifikat Web App dalam grup sumber daya
```
PS C:\>Get-AzureRmWebAppCertificate -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mengembalikan informasi tentang sertifikat Web App yang diunggah yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Mendapatkan sertifikat aplikasi web tertentu
```
PS C:\>Get-AzureRmWebAppCertificate -ResourceGroupName "ContosoResourceGroup" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini mendapatkan sertifikat ContosoResourceGroup Web App dengan sidik jari E3A38EBA60CAA1C162785A2E1C44A15AD450199C3.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat sertifikat ditetapkan.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmWebAppSSLBinding](./Get-AzureRmWebAppSSLBinding.md)


