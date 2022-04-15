---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 7311F66C-3370-4436-8030-6D98D42C3112
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmimagepublisher
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMImagePublisher.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMImagePublisher.md
ms.openlocfilehash: bf3f22af472fef094d5be91b0e7aabcf1c2a56a0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434288"
---
# Get-AzVMImagePublisher

## SYNOPSIS
Mendapatkan penerbit VMImage.

## SYNTAX

```
Get-AzVMImagePublisher -Location <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMImagePublisher** mendapatkan penerbit VMImage.

## EXAMPLES

### Contoh 1: Dapatkan penerbit VMImage untuk kawasan
```powershell
Get-AzVMImagePublisher -Location "Central US"
```

Perintah ini mendapatkan penerbit instans VMImage untuk kawasan AS Tengah dalam profil Azure Anda.

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

### -Lokasi
Menentukan lokasi VMImage.

```yaml
Type: System.String
Parameter Sets: (All)
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineImagePublisher

## CATATAN

## RELATED LINKS

[Get-AzVMImage](./Get-AzVMImage.md)

[Get-AzVMImageOffer](./Get-AzVMImageOffer.md)

[Get-AzVMImageSku](./Get-AzVMImageSku.md)

[Simpan-AzVMImage](./Save-AzVMImage.md)


