---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 17D7EBD2-FE3F-4D24-A1AA-8C45B9B1FEF5
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/remove-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
ms.openlocfilehash: f84727b91c8eaab0aeb0490ee328b82f29ff17b8
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136707536"
---
# Remove-AzApiManagementRegion

## SYNOPSIS
Menghapus kawasan penyebaran yang ada dari contoh PsApiManagement.

## SYNTAX

```
Remove-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApiManagementRegion** menghapus instans tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** dari kumpulan **AdditionalRegions** yang disediakan contoh tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak memodifikasi penyebaran dengan sendirinya, namun memperbarui contoh **in-memory PsApiManagement.**
Untuk memperbarui penyebaran Manajemen API, ubah **PsApiManagementInstance menjadi** **Set-AzApiManagement.**

## EXAMPLES

### Contoh 1: Menghapus kawasan dari contoh PsApiManagement
```
PS C:\>Remove-AzApiManagementRegion -ApiManagement $ApiManagement -Location "East US"
```

Perintah ini menghapus kawasan AS Timur dari contoh **PsApiManagement.**

### Contoh 2: Menghapus kawasan dari contoh PsApiManagement menggunakan serangkaian perintah
```
PS C:\>Get-AzApiManagement -ResourceGroupName "Contoso" -Name ContosoApi | Remove-AzApiManagementRegion -Location "East US" | Set-AzApiManagement
```

Perintah pertama ini mendapatkan contoh **PsApiManagement dari** grup sumber daya bernama Contoso bernama ContosoApi.
Perintah terakhir lalu menghapus kawasan YANG bernama AS Timur dari contoh tersebut, lalu memperbarui penyebarannya.

## PARAMETERS

### -ApiManagement
Menentukan instans **PsApiManagement** yang dihapus cmdlet ini dari wilayah penyebaran tambahan.

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
Menentukan lokasi wilayah yang dihapus cmdlet ini.
Menentukan lokasi wilayah penyebaran baru di antara kawasan yang didukung untuk layanan Manajemen Api.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Select-Object Lokasi

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## CATATAN

## RELATED LINKS

[Add-AzApiManagementRegion](./Add-AzApiManagementRegion.md)

[Update-AzApiManagementRegion](./Update-AzApiManagementRegion.md)


