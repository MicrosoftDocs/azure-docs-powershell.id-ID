---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM
ms.assetid: 89ED4231-7616-47D0-BDAA-D849C245DC79
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/get-azurermappserviceplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/Get-AzureRmAppServicePlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/Get-AzureRmAppServicePlan.md
ms.openlocfilehash: a46d104a6cd5917d6550d6b78d62a6d50581039e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428494"
---
# Get-AzureRmAppServicePlan

## SYNOPSIS
Mendapatkan paket Layanan Aplikasi Azure dalam grup sumber daya yang ditentukan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
Get-AzureRmAppServicePlan [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
Get-AzureRmAppServicePlan [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmAppServicePlan** mendapatkan paket Layanan Aplikasi Azure di grup sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan paket Layanan Aplikasi dari grup sumber daya
```
PS C:\>Get-AzureRmAppServicePlan -ResourceGroupName "Default-Web-WestUS" -Name "ContosoASP"
```

Perintah ini mendapatkan paket Layanan Aplikasi bernama ContosoASP yang dimiliki grup sumber daya bernama Default-Web-WestUS.

### Contoh 2: Dapatkan semua paket Layanan Aplikasi di suatu lokasi
```
PS C:\>Get-AzureRmAppServicePlan -Location "West US"
```

Perintah ini mendapatkan semua paket Layanan Aplikasi yang terletak di kawasan "Barat AS".

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Lokasi
Lokasi 

```yaml
Type: String
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Paket Layanan Aplikasi

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.ServerFarmWithRichSku

### Microsoft.Azure.Management.WebSites.Models.ServerFarmCollection

## CATATAN

## RELATED LINKS

[New-AzureRmAppServicePlan](./New-AzureRmAppServicePlan.md)

[Remove-AzureRmAppServicePlan](./Remove-AzureRmAppServicePlan.md)

[Set-AzureRmAppServicePlan](./Set-AzureRmAppServicePlan.md)


