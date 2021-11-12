---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 0632DAD6-F331-454F-9E7E-2164AB413E77
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/new-azurermresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmResourceGroup.md
ms.openlocfilehash: 7264733055322c3d5886ff57f50d22e23f932a7c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422509"
---
# New-AzureRmResourceGroup

## SYNOPSIS
Membuat grup sumber daya Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmResourceGroup -Name <String> -Location <String> [-Tag <Hashtable>] [-Force] [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmResourceGroup** membuat grup sumber daya Azure.
Anda bisa membuat grup sumber daya hanya dengan menggunakan nama dan lokasi, lalu menggunakan cmdlet New-AzureRmResource untuk membuat sumber daya untuk ditambahkan ke grup sumber daya.
Untuk menambahkan penyebaran ke grup sumber daya yang sudah ada, gunakan cmdlet New-AzureRmResourceGroupDeployment cmdlet. Untuk menambahkan sumber daya ke grup sumber daya yang sudah ada, gunakan cmdlet **New-AzureRmResource.** Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web. Grup sumber daya Azure adalah kumpulan sumber daya Azure yang digunakan sebagai unit.

## EXAMPLES

### Contoh 1: Membuat grup sumber daya kosong
```
PS> New-AzureRmResourceGroup -Name RG01 -Location "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya. Anda dapat menggunakan cmdlet **New-AzureRmResource** atau **New-AzureRmResourceGroupDeployment** untuk menambahkan sumber daya dan penyebaran ke grup sumber daya ini.

### Contoh 2: Membuat grup sumber daya kosong menggunakan parameter posisi
```
PS> New-AzureRmResourceGroup RG01 "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya.

### Contoh 3: Buat grup sumber daya dengan tag
```
PS> New-AzureRmResourceGroup -Name RG01 -Location "South Central US" -Tag @{Empty=$null; Department="Marketing"}
```

Perintah ini akan membuat grup sumber daya kosong. Perintah ini sama dengan perintah dalam Contoh 1, kecuali menetapkan tag ke grup sumber daya. Tag pertama, bernama Kosong, bisa digunakan untuk mengidentifikasi grup sumber daya yang tidak memiliki sumber daya. Tag kedua dinamai Departemen dan memiliki nilai Pemasaran. Anda bisa menggunakan tag seperti ini untuk mengkategorikan grup sumber daya untuk administrasi atau anggaran.

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda bisa menentukan versi yang berbeda dari versi default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi grup sumber daya. Tentukan lokasi pusat data Azure, seperti AS Barat atau Asia Tenggara. Anda bisa menempatkan grup sumber daya di lokasi mana pun. Grup sumber daya tidak harus berada di lokasi yang sama dengan langganan Azure Anda atau di lokasi yang sama dengan sumber dayanya.
Untuk menentukan lokasi yang mendukung setiap tipe sumber daya, Get-AzureRmResourceProvider cmdlet dengan parameter *ProviderNamespace.*

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

### -Nama
Menentukan nama untuk grup sumber daya. Nama sumber daya harus unik dalam langganan. Jika grup sumber daya yang memiliki nama tersebut sudah ada, perintah akan meminta konfirmasi Anda sebelum mengganti grup sumber daya yang ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Mengindikasikan bahwa cmdlet ini mempertimbangkan versi API prari perilisan bila secara otomatis menentukan versi mana yang akan digunakan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Untuk menambahkan atau mengubah tag, Anda harus mengganti kumpulan tag untuk grup sumber daya tersebut.
Setelah menetapkan tag untuk sumber daya dan grup, Anda bisa menggunakan parameter *Tag* dari Get-AzureRmResource dan Get-AzureRmResourceGroup untuk mencari sumber daya dan grup dengan nama tag atau menurut nama dan nilai. Anda bisa menggunakan tag untuk mengkategorikan sumber daya Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya tersebut.
Untuk mendapatkan tag yang sudah ditentukan sebelumnya, gunakan cmdlet Get-AzureRMTag.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models.PSResourceGroup

## CATATAN

## RELATED LINKS

[Get-AzureRmResourceProvider](./Get-AzureRmResourceProvider.md)

[Get-AzureRmResourceGroup](./Get-AzureRmResourceGroup.md)

[New-AzureRmResource](./New-AzureRmResource.md)

[New-AzureRmResourceGroupDeployment](./New-AzureRmResourceGroupDeployment.md)

[Remove-AzureRmResourceGroup](./Remove-AzureRmResourceGroup.md)

[Set-AzureRmResourceGroup](./Set-AzureRmResourceGroup.md)
