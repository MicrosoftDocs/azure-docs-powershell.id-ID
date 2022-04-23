---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM.Tags
ms.assetid: 726E01DD-D73C-4D4B-8FC0-52767927367C
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.tags/get-azurermtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Get-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Get-AzureRmTag.md
ms.openlocfilehash: 945af88df11e210c3af3a11bd69123dd32befe4a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212735"
---
# Get-AzureRmTag

## SYNOPSIS
Mendapatkan tag Azure yang sudah ditentukan sebelumnya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmTag [[-Name] <String>] [-Detailed] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmTag** akan mendapatkan tag Azure yang sudah ditentukan sebelumnya dalam langganan Anda.
Cmdlet ini mengembalikan informasi dasar tentang tag atau informasi mendetail tentang tag dan nilainya.
Semua objek output menyertakan properti Count yang mewakili jumlah sumber daya dan grup sumber daya tempat tag dan nilai telah diterapkan.
Modul Tag Azure yang menjadi bagian dari **Get-AzureRMTag** dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang bisa Anda gunakan untuk mengategorikan sumber daya dan grup sumber daya Azure Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.
Untuk membuat tag yang sudah ditentukan sebelumnya, gunakan cmdlet New-AzureRmTag.
Untuk menerapkan tag yang sudah ditentukan sebelumnya ke grup sumber daya, gunakan parameter *Tag* cmdlet New-AzureRmTag.
Untuk mencari grup sumber daya untuk nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* cmdlet Get-AzureRMResourceGroup.

## EXAMPLES

### Contoh 1: Dapatkan semua tag yang sudah ditentukan sebelumnya
```
PS C:\>Get-AzureRmTag

Name      Count
========  =====

Department    5
FY2015        2
CostCenter   20
```

Perintah ini mendapatkan semua tag yang sudah ditentukan sebelumnya dalam langganan.
Properti Count memperlihatkan berapa kali tag telah diterapkan ke sumber daya dan grup sumber daya dalam langganan.

### Contoh 2: Mendapatkan tag menurut nama
```
PS C:\>Get-AzureRmTag -Name "Department"

Name:   Department
Count:  5
Values: 

        Name        Count
        ==========  =====

        Finance       2
        IT            3
```

Perintah ini mendapatkan informasi mendetail tentang tag Departemen dan nilainya.
Properti Count memperlihatkan berapa kali tag dan setiap nilainya telah diterapkan ke sumber daya dan grup sumber daya dalam langganan.

### Contoh 3: Mendapatkan nilai dari semua tag
```
PS C:\>Get-AzureRmTag -Detailed

Name:   Department
Count:  5
Values: 

        Name        Count
        ==========  =====

        Finance       2
        IT            3


Name:   FY2015
Count:  2


Name:   CostCenter
Count:  20
Values: 

        Name        Count
        ==========  =====

        0001          5
        0002         10
        0003          5
```

Perintah ini menggunakan parameter *Detail* untuk mendapatkan informasi mendetail tentang semua tag yang sudah ditentukan sebelumnya dalam langganan.
Menggunakan parameter *Detail* sama dengan menggunakan parameter *Nama* untuk setiap tag.

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

### -Detail
Menunjukkan bahwa operasi ini menambahkan informasi tentang nilai tag ke output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama tag yang akan didapatkan.
Secara default, **Get-AzureRmTag** mendapatkan informasi dasar tentang semua tag yang sudah ditentukan sebelumnya dalam langganan.
Saat Anda menentukan parameter *Nama* , parameter *Detail* tidak berpengaruh.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag

## NOTES

## RELATED LINKS

[AzureRmTag Baru](./New-AzureRmTag.md)

[Hapus-AzureRmTag](./Remove-AzureRmTag.md)


