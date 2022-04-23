---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 17D7EBD2-FE3F-4D24-A1AA-8C45B9B1FEF5
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/remove-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
ms.openlocfilehash: dbdca2c4db27cda8fce5c4da2458748926398237
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143097641"
---
# Remove-AzApiManagementRegion

## SYNOPSIS
Menghapus wilayah penyebaran yang sudah ada dari instans PsApiManagement.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/remove-azapimanagementregion) untuk informasi terbaru.

## SYNTAX

```
Remove-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApiManagementRegion** menghapus contoh tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** dari kumpulan **Region Tambahan** yang disediakan contoh tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak mengubah penyebaran dengan sendirinya tetapi memperbarui contoh **PsApiManagement** dalam memori.
Untuk memperbarui penyebaran API Management, **kirimkan PsApiManagementInstance** yang dimodifikasi ke **Set-AzApiManagement**.

## EXAMPLES

### Contoh 1: Menghapus kawasan dari instans PsApiManagement
```
PS C:\>Remove-AzApiManagementRegion -ApiManagement $ApiManagement -Location "East US"
```

Perintah ini menghapus kawasan bernama AS Timur dari **instans PsApiManagement** .

### Contoh 2: Menghapus kawasan dari instans PsApiManagement menggunakan serangkaian perintah
```
PS C:\>Get-AzApiManagement -ResourceGroupName "Contoso" -Name ContosoApi | Remove-AzApiManagementRegion -Location "East US" | Set-AzApiManagement
```

Perintah pertama ini mendapatkan contoh **PsApiManagement** dari grup sumber daya bernama Contoso Bernama ContosoApi.
Perintah terakhir kemudian menghapus kawasan bernama AS Timur dari instans tersebut lalu memperbarui penyebaran.

## PARAMETERS

### -ApiManagement
Menentukan **instans PsApiManagement** tempat cmdlet ini menghapus area penyebaran tambahan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile

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
Menentukan lokasi kawasan yang dihapus cmdlet ini.
Menentukan lokasi kawasan penyebaran baru di antara kawasan yang didukung untuk layanan Manajemen Api.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Lokasi Select-Object

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

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Add-AzApiManagementRegion](./Add-AzApiManagementRegion.md)

[Update-AzApiManagementRegion](./Update-AzApiManagementRegion.md)


