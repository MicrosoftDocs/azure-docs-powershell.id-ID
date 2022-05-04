---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 0632DAD6-F331-454F-9E7E-2164AB413E77
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceGroup.md
ms.openlocfilehash: b2549471f14096895fb4c42471936536e4436e0e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144725256"
---
# Baru-AzResourceGroup

## SYNOPSIS
Membuat grup sumber daya Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/new-azresourcegroup) untuk informasi terbaru.

## SYNTAX

```
New-AzResourceGroup [-Name] <String> [-Location] <String> [-Tag <Hashtable>] [-Force] [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzResourceGroup** membuat grup sumber daya Azure.
Anda dapat membuat grup sumber daya hanya dengan menggunakan nama dan lokasi, lalu menggunakan cmdlet New-AzResource untuk membuat sumber daya untuk ditambahkan ke grup sumber daya.
Untuk menambahkan penyebaran ke grup sumber daya yang ada, gunakan cmdlet New-AzResourceGroupDeployment. Untuk menambahkan sumber daya ke grup sumber daya yang ada, gunakan cmdlet **New-AzResource** . Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web. Grup sumber daya Azure adalah kumpulan sumber daya Azure yang disebarkan sebagai unit.

## EXAMPLES

### Contoh 1: Membuat grup sumber daya kosong
```powershell
New-AzResourceGroup -Name RG01 -Location "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya. Anda dapat menggunakan cmdlet **New-AzResource** atau **New-AzResourceGroupDeployment** untuk menambahkan sumber daya dan penyebaran ke grup sumber daya ini.

### Contoh 2: Membuat grup sumber daya kosong menggunakan parameter posisional
```powershell
New-AzResourceGroup RG01 "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya.

### Contoh 3: Membuat grup sumber daya dengan tag
```powershell
New-AzResourceGroup -Name RG01 -Location "South Central US" -Tag @{Empty=$null; Department="Marketing"}
```

Perintah ini membuat grup sumber daya kosong. Perintah ini sama dengan perintah di Contoh 1, kecuali bahwa perintah menetapkan tag ke grup sumber daya. Tag pertama, bernama Kosong, dapat digunakan untuk mengidentifikasi grup sumber daya yang tidak memiliki sumber daya. Tag kedua diberi nama Departemen dan memiliki nilai Pemasaran. Anda dapat menggunakan tag seperti ini untuk mengategorikan grup sumber daya untuk administrasi atau anggaran.

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda dapat menentukan versi yang berbeda dari versi default.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Menentukan lokasi grup sumber daya. Tentukan lokasi pusat data Azure, seperti US Barat atau Asia Tenggara. Anda dapat menempatkan grup sumber daya di lokasi mana pun. Grup sumber daya tidak harus berada di lokasi yang sama dengan langganan Azure Anda atau di lokasi yang sama dengan sumber dayanya.
Untuk menentukan lokasi mana yang mendukung setiap jenis sumber daya, gunakan cmdlet Get-AzResourceProvider dengan parameter *ProviderNamespace* .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama untuk grup sumber daya. Nama sumber daya harus unik dalam langganan. Jika grup sumber daya yang memiliki nama tersebut sudah ada, perintah akan meminta konfirmasi sebelum mengganti grup sumber daya yang ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroupName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Untuk menambahkan atau mengubah tag, Anda harus mengganti kumpulan tag untuk grup sumber daya.
Setelah menetapkan tag ke sumber daya dan grup, Anda dapat menggunakan parameter *Tag* Get-AzResource dan Get-AzResourceGroup untuk mencari sumber daya dan grup menurut nama tag atau berdasarkan nama dan nilai. Anda dapat menggunakan tag untuk mengategorikan sumber daya Anda, seperti berdasarkan departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya.
Untuk mendapatkan tag yang telah ditentukan sebelumnya, gunakan cmdlet Get-AzTag.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceGroup

## NOTES

## RELATED LINKS

[Get-AzResourceProvider](./Get-AzResourceProvider.md)

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[New-AzResource](./New-AzResource.md)

[New-AzResourceGroupDeployment](./New-AzResourceGroupDeployment.md)

[Remove-AzResourceGroup](./Remove-AzResourceGroup.md)

[Set-AzResourceGroup](./Set-AzResourceGroup.md)
