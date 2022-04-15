---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 726E01DD-D73C-4D4B-8FC0-52767927367C
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzTag.md
ms.openlocfilehash: 1f2289351da276a0422828c082bb51d8dc267a20
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142056287"
---
# Get-AzTag

## SYNOPSIS
Mendapatkan tag Azure yang sudah ditentukan sebelumnya.

## SYNTAX

```
Get-AzTag [[-Name] <String>] [-Detailed] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzTag** akan mendapatkan tag Azure yang sudah ditentukan sebelumnya dalam langganan Anda.
Cmdlet ini mengembalikan informasi dasar tentang tag atau informasi mendetail tentang tag dan nilainya.
Semua objek output menyertakan properti Count yang mewakili jumlah sumber daya dan grup sumber daya tempat tag dan nilai telah diterapkan.
Modul Tag Azure yang **menjadi bagian dari Get-AzTag** dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang bisa Anda gunakan untuk mengategorikan sumber daya dan grup sumber daya Azure Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.
Untuk membuat tag yang sudah ditentukan sebelumnya, gunakan cmdlet New-AzTag.
Untuk menerapkan tag yang sudah ditentukan sebelumnya ke grup sumber daya, gunakan parameter *Tag* cmdlet New-AzTag.
Untuk mencari grup sumber daya untuk nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* cmdlet Get-AzResourceGroup.

## EXAMPLES

### Contoh 1: Dapatkan semua tag yang sudah ditentukan sebelumnya
```
PS C:\>Get-AzTag

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
PS C:\>Get-AzTag -Name "Department"

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
PS C:\>Get-AzTag -Detailed

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

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
Secara default, **Get-AzTag** mendapatkan informasi dasar tentang semua tag yang sudah ditentukan sebelumnya dalam langganan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag

## CATATAN

## RELATED LINKS

[New-AzTag](./New-AzTag.md)

[Hapus-AzTag](./Remove-AzTag.md)

