---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM.Tags
ms.assetid: 23DB0AD2-7EB7-4373-BB8D-BB6CB651DD54
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.tags/new-azurermtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/New-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/New-AzureRmTag.md
ms.openlocfilehash: cd9700a633f1a9c09c5fafd060d318b35eaeaabb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141773627"
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
Cmdlet **AzureRmTag Baru** membuat tag Azure yang sudah ditentukan sebelumnya dengan nilai opsional yang sudah ditentukan sebelumnya.
Anda juga bisa menggunakannya untuk menambahkan nilai tambahan ke tag yang sudah ditentukan sebelumnya.
Untuk membuat tag yang sudah ditentukan sebelumnya, masukkan nama tag unik.
Untuk menambahkan nilai ke tag yang sudah ditentukan sebelumnya, tentukan nama tag yang sudah ada dan nilai baru.
Cmdlet ini mengembalikan objek yang mewakili tag baru atau yang diubah dengan nilainya dan jumlah sumber daya yang telah diterapkan.
Modul Tag Azure yang merupakan bagian dari **AzureRmTag Baru** dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang bisa Anda gunakan untuk mengategorikan sumber daya dan grup sumber daya Azure Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.
Untuk menerapkan tag yang sudah ditentukan sebelumnya ke grup sumber daya atau sumber daya, gunakan parameter *Tag* cmdlet New-AzureRmTag.
Untuk mencari grup sumber daya dengan nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* cmdlet Get-AzureRMResourceGroup.
Setiap tag memiliki nama.
Nilai bersifat opsional.
Tag Azure yang sudah ditentukan sebelumnya dapat memiliki beberapa nilai, tetapi saat Anda menerapkan tag ke grup sumber daya atau sumber daya, Anda menerapkan nama tag dan hanya salah satu nilainya.
Misalnya, Anda bisa membuat tag Departemen yang sudah ditentukan sebelumnya dengan nilai untuk setiap departemen, seperti Keuangan, Sumber Daya Manusia, dan TI.
Saat Anda menerapkan tag Departemen ke sumber daya, Anda hanya menerapkan satu nilai yang sudah ditentukan sebelumnya, seperti Keuangan.

## EXAMPLES

### Contoh 1: Membuat tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "FY2015"
Name:   FY2015
Count:  0
Values: 

        Name        Count
        =========   =====

        Finance     0
```

Perintah ini membuat tag yang sudah ditentukan sebelumnya bernama FY2015.
Tag ini tidak memiliki nilai.
Anda dapat menerapkan tag tanpa nilai ke grup sumber daya atau sumber daya, atau menggunakan **New-AzureRmTag** untuk menambahkan nilai ke tag.
Anda juga dapat menentukan nilai saat menerapkan tag ke grup sumber daya atau sumber daya.

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

Perintah ini membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan nilai Keuangan.

### Contoh 3: Menambahkan nilai ke tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0 
PS C:\>New-AzureRmTag -Name "Department" -Value "IT"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0
        IT          0
```

Perintah ini membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan dua nilai.
Jika nama tag sudah ada, **New-AzureRmTag** menambahkan nilai ke tag yang sudah ada, bukan membuat yang baru.

### Contoh 4: Menggunakan tag yang sudah ditentukan sebelumnya
```
PS C:\>New-AzureRmTag -Name "CostCenter" -Value "0001"
Name:   CostCenter
Count:  0
Values: 
        Name        Count
        =========   =====
        0001        0 
PS C:\>Set-AzureRmResourceGroup -Name "EngineerBlog" -Tag @{Name="CostCenter";Value="0001"}
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
PS C:\>Get-AzureRmTag -Name "CostCenter"
Name:   CostCenter
Count:  1
Values: 
        Name        Count
        =========   =====
        0001        1 
PS C:\>Get-AzureRmResourceGroup -Tag @{Name="CostCenter"}
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Menentukan nama tag.
Untuk membuat tag baru yang sudah ditentukan sebelumnya, masukkan nama yang unik.
Untuk menambahkan nilai ke tag yang sudah ada, masukkan nama tag yang sudah ada.
Jika tag yang sudah ditentukan sebelumnya memiliki nama yang ditentukan, **AzureRmTag Baru** menambahkan nilai yang ditentukan, jika ada, ke tag dengan nama tersebut, bukan membuat tag baru.

```yaml
Type: System.String
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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag

## CATATAN

## RELATED LINKS

[Get-AzureRmTag](./Get-AzureRmTag.md)

[Hapus-AzureRmTag](./Remove-AzureRmTag.md)


