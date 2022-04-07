---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 4E5C059B-36F3-41C8-9FDB-69F5318CF39B
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzResourceGroup.md
ms.openlocfilehash: f33094398c1f5754eaad21dfa4028973c5358598
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140459752"
---
# Set-AzResourceGroup

## SYNOPSIS
Mengubah grup sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/set-azresourcegroup) untuk informasi terkini.

## SYNTAX

### SetByResourceGroupName (Default)
```
Set-AzResourceGroup -Name <String> [-Tag] <Hashtable> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceGroupId
```
Set-AzResourceGroup [-Tag] <Hashtable> -Id <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzResourceGroup** mengubah properti grup sumber daya.
Anda dapat menggunakan cmdlet ini untuk menambahkan, mengubah, atau menghapus tag Azure yang diterapkan ke grup sumber daya.
Tentukan parameter *Nama* untuk mengidentifikasi grup sumber daya *dan parameter* Tag untuk mengubah tag.
Anda tidak dapat menggunakan cmdlet ini untuk mengubah nama grup sumber daya.

## EXAMPLES

### Contoh 1: Menerapkan tag ke grup sumber daya
```
PS C:\>Set-AzResourceGroup -Name "ContosoRG" -Tag @{Department="IT"}
```

Perintah ini menerapkan tag Departemen dengan nilai IT ke grup sumber daya yang tidak memiliki tag yang sudah ada.

### Contoh 2: Menambahkan tag ke grup sumber daya
```
PS C:\>$Tags = (Get-AzResourceGroup -Name "ContosoRG").Tags
PS C:\> $Tags
PS C:\> $Tags += @{"Status"="Approved"; "FY2016"=$null}
PS C:\> Set-AzResourceGroup -Name "ContosoRG" -Tag $Tags
PS C:> (Get-AzResourceGroup -Name "ContosoRG").Tags
```

Contoh ini menambahkan tag Status dengan nilai Disetujui dan tag FY2016 ke grup sumber daya yang memiliki tag yang sudah ada. Karena tag yang ditentukan akan menggantikan tag yang sudah ada, Anda harus menyertakan tag yang sudah ada dalam kumpulan tag baru atau kehilangan tag tersebut.
Perintah pertama mendapatkan grup sumber daya ContosoRG dan menggunakan metode titik untuk mendapatkan nilai properti Tag. Perintah menyimpan tag dalam $Tags variabel.
Perintah kedua mendapatkan tag di $Tags variabel.
Perintah ketiga menggunakan operator penetapan += untuk menambahkan tag Status dan FY2016 ke larik tag di $Tags penerima.
Perintah keempat menggunakan parameter *Tag* **Set-AzResourceGroup** untuk menerapkan tag di variabel $Tags ke grup sumber daya ContosoRG.
Perintah kelima adalah semua tag yang diterapkan ke grup sumber daya ContosoRG. Output memperlihatkan bahwa grup sumber daya memiliki tag Departemen dan dua tag baru, Status dan FY2015.

### Contoh 3: Hapus semua tag untuk grup sumber daya
```
PS C:\>Set-AzResourceGroup -Name "ContosoRG" -Tag @{}
```

Perintah ini menentukan *parameter Tag* dengan nilai tabel hash kosong untuk menghapus semua tag dari grup sumber daya ContosoRG.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID grup sumber daya untuk diubah.

```yaml
Type: System.String
Parameter Sets: SetByResourceGroupId
Aliases: ResourceGroupId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama grup sumber daya untuk diubah.

```yaml
Type: System.String
Parameter Sets: SetByResourceGroupName
Aliases: ResourceGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Cmdlet ini mempertimbangkan versi API prari release ketika cmdlet menentukan versi mana yang akan digunakan secara otomatis.

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
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Tag adalah pasangan nilai nama yang dapat dibuat dan diterapkan ke sumber daya dan grup sumber daya. Setelah menetapkan tag untuk sumber daya dan grup, Anda bisa menggunakan parameter *Tag* dari Get-AzResource dan Get-AzResourceGroup untuk mencari sumber daya dan grup dengan nama atau nama tag dan nilai. Anda bisa menggunakan tag untuk mengkategorikan sumber daya Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya tersebut.
Untuk menambahkan atau mengubah tag, Anda harus mengganti kumpulan tag untuk grup sumber daya tersebut. Untuk menghapus tag, masukkan tabel hash dengan semua tag yang saat ini diterapkan ke grup sumber daya, dari **Get-AzResourceGroup**, kecuali untuk tag yang ingin Anda hapus. Untuk menghapus semua tag dari grup sumber daya, tentukan tabel hash kosong: `@{}`.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceGroup

## CATATAN

## RELATED LINKS

[Get-AzResource](./Get-AzResource.md)

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[New-AzResourceGroup](./New-AzResourceGroup.md)

[Remove-AzResourceGroup](./Remove-AzResourceGroup.md)
