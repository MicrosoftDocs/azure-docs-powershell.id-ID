---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 0632DAD6-F331-454F-9E7E-2164AB413E77
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/new-Azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/New-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/New-AzResourceGroup.md
ms.openlocfilehash: b0d9d23b9563c38a985adfa3d12dfc2854319512
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142496537"
---
# New-AzResourceGroup

## SYNOPSIS
Membuat grup sumber daya Azure.

## SYNTAX

```
New-AzResourceGroup -Name <String> -Location <String> [-Tag <Hashtable>] [-Force] [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzResourceGroup** membuat grup sumber daya Azure.
Anda bisa membuat grup sumber daya hanya dengan menggunakan nama dan lokasi, lalu gunakan cmdlet New-AzResource untuk membuat sumber daya untuk ditambahkan ke grup sumber daya.
Untuk menambahkan penyebaran ke grup sumber daya yang sudah ada, gunakan cmdlet New-AzResourceGroupDeployment. Untuk menambahkan sumber daya ke grup sumber daya yang sudah ada, gunakan cmdlet **New-AzResource** . Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web. Grup sumber daya Azure adalah kumpulan sumber daya Azure yang disebarkan sebagai unit.

## EXAMPLES

### Contoh 1: Membuat grup sumber daya kosong
```
PS> New-AzResourceGroup -Name RG01 -Location "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya. Anda dapat menggunakan cmdlet **New-AzResource** atau **New-AzResourceGroupDeployment** untuk menambahkan sumber daya dan penyebaran ke grup sumber daya ini.

### Contoh 2: Membuat grup sumber daya kosong menggunakan parameter posisi
```
PS> New-AzResourceGroup RG01 "South Central US"
```

Perintah ini membuat grup sumber daya yang tidak memiliki sumber daya.

### Contoh 3: Membuat grup sumber daya dengan tag
```
PS> New-AzResourceGroup -Name RG01 -Location "South Central US" -Tag @{Empty=$null; Department="Marketing"}
```

Perintah ini membuat grup sumber daya kosong. Perintah ini sama dengan perintah dalam Contoh 1, kecuali bahwa perintah menetapkan tag ke grup sumber daya. Tag pertama, bernama Kosong, bisa digunakan untuk mengidentifikasi grup sumber daya yang tidak memiliki sumber daya. Tag kedua dinamai Departemen dan memiliki nilai Pemasaran. Anda bisa menggunakan tag seperti ini untuk mengkategorikan grup sumber daya untuk administrasi atau penganggaran.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
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
Menentukan lokasi grup sumber daya. Tentukan lokasi pusat data Azure, seperti AS Barat atau Asia Tenggara. Anda bisa menempatkan grup sumber daya di lokasi mana pun. Grup sumber daya tidak harus berada di lokasi yang sama dengan langganan Azure Anda atau di lokasi yang sama dengan sumber dayanya.
Untuk menentukan lokasi mana yang mendukung setiap tipe sumber daya, gunakan cmdlet Get-AzResourceProvider dengan parameter *ProviderNamespace* .

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
Menentukan nama untuk grup sumber daya. Nama sumber daya harus unik dalam langganan. Jika grup sumber daya yang memiliki nama tersebut sudah ada, perintah akan meminta konfirmasi sebelum mengganti grup sumber daya yang sudah ada.

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
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API prarilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Untuk menambahkan atau mengubah tag, Anda harus mengganti kumpulan tag untuk grup sumber daya.
Setelah menetapkan tag ke sumber daya dan grup, Anda bisa menggunakan parameter *Tag* Get-AzResource dan Get-AzResourceGroup untuk mencari sumber daya dan grup menurut nama tag atau menurut nama dan nilai. Anda bisa menggunakan tag untuk mengkategorikan sumber daya Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya.
Untuk mendapatkan tag yang sudah ditentukan sebelumnya, gunakan cmdlet Get-AzTag.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models.PSResourceGroup

## CATATAN

## RELATED LINKS

[Get-AzResourceProvider](./Get-AzResourceProvider.md)

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[New-AzResource](./New-AzResource.md)

[New-AzResourceGroupDeployment](./New-AzResourceGroupDeployment.md)

[Hapus-AzResourceGroup](./Remove-AzResourceGroup.md)

[Set-AzResourceGroup](./Set-AzResourceGroup.md)
