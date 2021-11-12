---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM
ms.assetid: 23DB0AD2-7EB7-4373-BB8D-BB6CB651DD54
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.tags/new-azurermtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/New-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/New-AzureRmTag.md
ms.openlocfilehash: 77bf93905b0cba4e8f8a23cb9f3cb8945fff74f1
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422974"
---
# New-AzureRmTag

## SYNOPSIS
Membuat tag Azure yang sudah ditentukan sebelumnya atau menambahkan nilai ke tag yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmTag [-Name] <String> [[-Value] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmTag** membuat tag Azure yang sudah ditentukan sebelumnya dengan nilai opsional yang telah ditentukan sebelumnya.
Anda juga bisa menggunakannya untuk menambahkan nilai tambahan ke tag yang sudah ditentukan sebelumnya yang sudah ada.
Untuk membuat tag yang sudah ditentukan sebelumnya, masukkan nama tag unik.
Untuk menambahkan nilai ke tag yang sudah ditentukan sebelumnya yang sudah ada, tentukan nama tag yang sudah ada dan nilai baru.

Cmdlet ini mengembalikan objek yang mewakili tag baru atau yang dimodifikasi dengan nilainya dan jumlah sumber daya yang diterapkan.

Modul Tag Azure yang **menjadi bagian dari AzureRmTag** Baru dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat digunakan untuk mengategorikan sumber daya dan grup sumber daya Azure, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.

Anda bisa menetapkan dan menerapkan tag dalam satu langkah, tapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan yang bisa diprediksi untuk tag di langganan Anda.
Jika langganan menyertakan tag yang sudah ditentukan sebelumnya, Anda tidak dapat menerapkan tag atau nilai yang tidak didefinisikan ke sumber daya atau grup sumber daya apa pun dalam langganan.

Untuk menerapkan tag yang sudah ditentukan sebelumnya ke grup sumber daya atau sumber *daya,* gunakan parameter Tag New-AzureRmTag cmdlet.
Untuk mencari grup sumber daya dengan nama atau nama atau nilai tag yang *ditentukan,* gunakan parameter Tag Get-AzureRMResourceGroup cmdlet.

Setiap tag memiliki nama.
Nilainya bersifat opsional.
Tag Azure yang sudah ditentukan sebelumnya bisa memiliki beberapa nilai, tapi saat Anda menerapkan tag ke sumber daya atau grup sumber daya, Anda menerapkan nama tag dan hanya salah satu nilainya.
Misalnya, Anda dapat membuat tag Departemen yang sudah ditentukan sebelumnya dengan nilai untuk setiap departemen, seperti Keuangan, Sumber Daya Manusia, dan IT.
Saat Anda menerapkan tag Departemen ke sumber daya, Anda hanya menerapkan satu nilai yang sudah ditentukan sebelumnya, seperti Keuangan.

## EXAMPLES

### Contoh 1: Membuat tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "FY2015"
Name:   Department
Count:  0
Values: 

        Name        Count
        =========   =====

        Finance     0
```

Perintah ini akan membuat tag yang sudah ditentukan sebelumnya bernama FY2015.
Tag ini tidak memiliki nilai.
Anda dapat menerapkan tag tanpa nilai ke grup sumber daya atau sumber daya, atau menggunakan **AzureRmTag** Baru untuk menambahkan nilai ke tag.
Anda juga bisa menentukan nilai saat Anda menerapkan tag ke grup sumber daya atau sumber daya.

### Contoh 2: Membuat tag yang sudah ditentukan sebelumnya dengan nilai
```
PS C:\>New-AzureRmTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values: 

        Name        Count
        =========   =====
        Finance     0
```

Perintah ini akan membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan nilai Keuangan.

### Contoh 3: Menambahkan nilai ke tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0 PS C:\>New-AzureRmTag -Name "Department" -Value "IT"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0
        IT          0
```

Perintah ini membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan dua nilai.
Jika nama tag ada, **New-AzureRmTag** menambahkan nilai ke tag yang sudah ada, bukan membuat yang baru.

### Contoh 4: Menggunakan tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "CostCenter" -Value "0001"
Name:   CostCenter
Count:  0
Values: 
        Name        Count
        =========   =====
        0001        0 PS C:\>Set-AzureRmResourceGroup -Name "EngineerBlog" -Tag @{Name="CostCenter";Value="0001"}
Name:      EngineerBlog
Location:  East US
Resources: 
            
  Name             Type                     Location
    ===============  =======================  ========
    EngineerBlog     Microsoft.Web/sites      West US
    EngSvr01         Microsoft.Sql/servers    West US
    EngDB02          Microsoft.Sql/databases  West US
Tags: 
    Name         Value
    ==========   =====
    CostCenter   0001 PS C:\>Get-AzureRmTag -Name "CostCenter"
Name:   CostCenter
Count:  1
Values: 
        Name        Count
        =========   =====
        0001        1 PS C:\>Get-AzureRmResourceGroup -Tag @{Name="CostCenter"}
Name:      EngineerBlog
Location:  East US
Resources: 
     Name             Type                     Location
    ===============  =======================  ========
    EngineerBlog     Microsoft.Web/sites      West US

    EngSvr01         Microsoft.Sql/servers    West US
    EngDB02          Microsoft.Sql/databases  West US
Tags: 
    Name         Value
    ==========   =====
    CostCenter   0001
```

Perintah dalam contoh ini membuat dan menggunakan tag yang sudah ditentukan sebelumnya.

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

### -Nama
Menentukan nama tag.
Untuk membuat tag baru yang sudah ditentukan sebelumnya, masukkan nama yang unik.

Untuk menambahkan nilai ke tag yang sudah ada, masukkan nama tag yang sudah ada.
Jika tag yang sudah ditentukan sebelumnya memiliki nama yang ditentukan, **New-AzureRmTag** menambahkan nilai yang ditentukan, jika ada, ke tag dengan nama itu dan bukan membuat tag baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Menentukan nilai tag.
Tag yang sudah ditentukan sebelumnya bisa memiliki beberapa nilai, tapi Anda hanya bisa memasukkan satu nilai dalam setiap perintah.
Parameter ini opsional, karena tag bisa memiliki nama tanpa nilai.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTag

## CATATAN

## RELATED LINKS

[Get-AzureRmTag](./Get-AzureRmTag.md)

[Remove-AzureRmTag](./Remove-AzureRmTag.md)


