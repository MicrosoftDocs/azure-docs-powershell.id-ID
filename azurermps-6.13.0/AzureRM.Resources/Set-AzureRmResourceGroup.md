---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 4E5C059B-36F3-41C8-9FDB-69F5318CF39B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/set-azurermresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmResourceGroup.md
ms.openlocfilehash: 4ba57d1f8e1abe8c506f1bcd6625a7a90551f164
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141775170"
---
# Set-AzureRmResourceGroup

## SYNOPSIS
Mengubah grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResourceGroupName (Default)
```
Set-AzureRmResourceGroup [-Name] <String> [-Tag] <Hashtable> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceGroupId
```
Set-AzureRmResourceGroup [-Tag] <Hashtable> [-Id] <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmResourceGroup** mengubah properti grup sumber daya.
Anda dapat menggunakan cmdlet ini untuk menambahkan, mengubah, atau menghapus tag Azure yang diterapkan ke grup sumber daya.
Tentukan parameter *Nama* untuk mengidentifikasi grup sumber daya dan parameter *Tag* untuk mengubah tag.
Anda tidak dapat menggunakan cmdlet ini untuk mengubah nama grup sumber daya.

## EXAMPLES

### Contoh 1: Menerapkan tag ke grup sumber daya
```
PS C:\>Set-AzureRmResourceGroup -Name "ContosoRG" -Tag @{Department="IT"}
```

Perintah ini menerapkan tag Departemen dengan nilai TI ke grup sumber daya yang tidak memiliki tag yang sudah ada.

### Contoh 2: Menambahkan tag ke grup sumber daya
```
PS C:\>$Tags = (Get-AzureRmResourceGroup -Name "ContosoRG").Tags
PS C:\> $Tags
PS C:\> $Tags += @{"Status"="Approved"; "FY2016"=$null}
PS C:\> Set-AzureRmResourceGroup -Name "ContosoRG" -Tag $Tags
PS C:> (Get-AzureRmResourceGroup -Name "ContosoRG").Tags
```

Contoh ini menambahkan tag Status dengan nilai Disetujui dan tag FY2016 ke grup sumber daya yang memiliki tag yang sudah ada. Karena tag yang Anda tentukan mengganti tag yang sudah ada, Anda harus menyertakan tag yang sudah ada dalam kumpulan tag baru atau Anda akan kehilangan tag tersebut.
Perintah pertama mendapatkan grup sumber daya ContosoRG dan menggunakan metode titik untuk mendapatkan nilai properti Tag-nya. Perintah menyimpan tag dalam variabel $Tags.
Perintah kedua akan mendapatkan tag dalam variabel $Tags.
Perintah ketiga menggunakan operator penugasan += untuk menambahkan tag Status dan FY2016 ke array tag dalam variabel $Tags.
Perintah keempat menggunakan parameter *Tag* **Set-AzureRmResourceGroup** untuk menerapkan tag dalam variabel $Tags ke grup sumber daya ContosoRG.
Perintah kelima mendapatkan semua tag yang diterapkan ke grup sumber daya ContosoRG. Output menunjukkan bahwa grup sumber daya memiliki tag Departemen dan dua tag baru, Status dan FY2015.

### Contoh 3: Menghapus semua tag untuk grup sumber daya
```
PS C:\>Set-AzureRmResourceGroup -Name "ContosoRG" -Tag @{}
```

Perintah ini menentukan parameter *Tag* dengan nilai tabel hash kosong untuk menghapus semua tag dari grup sumber daya ContosoRG.

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
Aliases: AzureRmContext, AzureCredential

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
Position: 0
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
Position: 0
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
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"} Tag adalah pasangan nilai nama yang dapat Anda buat dan terapkan ke sumber daya dan grup sumber daya. Setelah menetapkan tag ke sumber daya dan grup, Anda bisa menggunakan parameter *Tag* Get-AzureRmResource dan Get-AzureRmResourceGroup untuk mencari sumber daya dan grup menurut nama tag atau nama dan nilai. Anda bisa menggunakan tag untuk mengkategorikan sumber daya Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya.
Untuk menambahkan atau mengubah tag, Anda harus mengganti kumpulan tag untuk grup sumber daya. Untuk menghapus tag, masukkan tabel hash dengan semua tag yang saat ini diterapkan ke grup sumber daya, dari **Get-AzureRmResourceGroup**, kecuali tag yang ingin Anda hapus. Untuk menghapus semua tag dari grup sumber daya, tentukan tabel hash kosong: `@{}`.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceGroup

## CATATAN

## RELATED LINKS

[Get-AzureRmResource](./Get-AzureRmResource.md)

[Get-AzureRmResourceGroup](./Get-AzureRmResourceGroup.md)

[AzureRmResourceGroup baru](./New-AzureRmResourceGroup.md)

[Hapus-AzureRmResourceGroup](./Remove-AzureRmResourceGroup.md)
