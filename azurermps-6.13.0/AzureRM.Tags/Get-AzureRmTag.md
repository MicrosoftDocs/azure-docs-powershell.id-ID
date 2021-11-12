---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM.Tags
ms.assetid: 726E01DD-D73C-4D4B-8FC0-52767927367C
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.tags/get-azurermtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Get-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Get-AzureRmTag.md
ms.openlocfilehash: 945af88df11e210c3af3a11bd69123dd32befe4a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421182"
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
Cmdlet **Get-AzureRmTag** mendapatkan tag Azure yang sudah ditentukan sebelumnya di langganan Anda.
Cmdlet ini mengembalikan informasi dasar tentang tag atau informasi mendetail tentang tag dan nilainya.
Semua objek output menyertakan properti Hitung yang mewakili jumlah sumber daya dan grup sumber daya di mana tag dan nilai telah diterapkan.
Modul Tag Azure yang menjadi **bagian dari Get-AzureRMTag** dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat digunakan untuk mengategorikan sumber daya dan grup sumber daya Azure, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menetapkan dan menerapkan tag dalam satu langkah, tapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan yang bisa diprediksi untuk tag di langganan Anda.
Untuk membuat tag yang sudah ditentukan sebelumnya, gunakan cmdlet New-AzureRmTag.
Untuk menerapkan tag yang sudah ditentukan sebelumnya ke grup sumber daya, gunakan parameter *Tag* cmdlet New-AzureRmTag cmdlet.
Untuk mencari grup sumber daya bagi nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* Get-AzureRMResourceGroup cmdlet.

## EXAMPLES

### Contoh 1: Mendapatkan semua tag yang sudah ditentukan sebelumnya
```
PS C:\>Get-AzureRmTag

Name      Count
========  =====

Department    5
FY2015        2
CostCenter   20
```

Perintah ini akan mendapatkan semua tag yang sudah ditentukan sebelumnya dalam langganan.
Properti Count memperlihatkan berapa kali tag diterapkan ke sumber daya dan grup sumber daya dalam langganan.

### Contoh 2: Dapatkan tag dengan nama
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

### Contoh 3: Dapatkan nilai semua tag
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

Perintah ini menggunakan *parameter Mendetail* untuk mendapatkan informasi detail tentang semua tag yang sudah ditentukan sebelumnya dalam langganan.
Penggunaan *parameter Detail* setara dengan penggunaan parameter *Name* untuk setiap tag.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan nama tag untuk mendapatkan.
Secara default, **Get-AzureRmTag** mendapatkan informasi dasar tentang semua tag yang ditentukan sebelumnya dalam langganan.
Ketika Anda menentukan parameter *Name,* *parameter Detail* tidak memiliki efek.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag

## CATATAN

## RELATED LINKS

[New-AzureRmTag](./New-AzureRmTag.md)

[Remove-AzureRmTag](./Remove-AzureRmTag.md)


