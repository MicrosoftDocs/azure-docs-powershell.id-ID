---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 726E01DD-D73C-4D4B-8FC0-52767927367C
online version: https://docs.microsoft.com/powershell/module/az.resources/get-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTag.md
ms.openlocfilehash: 599d8cf47af90479c8c26693c2a340a8d4ab85d5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144569036"
---
# Get-AzTag

## SYNOPSIS
Mendapatkan tag Azure yang telah ditentukan sebelumnya | Mendapatkan seluruh kumpulan tag pada sumber daya atau langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-aztag) untuk informasi terbaru.

## SYNTAX

### GetPredefinedTagParameterSet
```
Get-AzTag [[-Name] <String>] [-Detailed] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzTag -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

**GetPredefinedTagSet**: Cmdlet **Get-AzTag** mendapatkan tag Azure yang telah ditentukan sebelumnya di langganan Anda.
Cmdlet ini mengembalikan informasi dasar tentang tag atau informasi terperinci tentang tag dan nilainya.
Semua objek output menyertakan properti Hitungan yang mewakili jumlah sumber daya dan grup sumber daya tempat tag dan nilai telah diterapkan.
Modul Tag Azure yang merupakan bagian dari **Get-AzTag** dapat membantu Anda mengelola tag Azure yang telah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat Anda gunakan untuk mengategorikan sumber daya dan grup sumber daya Azure Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda dapat menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang telah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag di langganan Anda.
Untuk membuat tag yang telah ditentukan sebelumnya, gunakan cmdlet New-AzTag.
Untuk menerapkan tag yang telah ditentukan sebelumnya ke grup sumber daya, gunakan parameter *Tag* cmdlet New-AzTag.
Untuk mencari grup sumber daya untuk nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* cmdlet Get-AzResourceGroup.

**GetByResourceIdParameterSet**: Cmdlet **Get-AzTag** dengan **ResourceId** mendapatkan seluruh set tag pada sumber daya atau langganan.

## EXAMPLES

### Contoh 1: Dapatkan semua tag yang telah ditentukan sebelumnya
```powershell
Get-AzTag
```

```output
Name      Count
========  =====

Department    5
FY2015        2
CostCenter   20
```

Perintah ini mendapatkan semua tag yang telah ditentukan sebelumnya dalam langganan.
Properti Hitung memperlihatkan berapa kali tag telah diterapkan ke sumber daya dan grup sumber daya dalam langganan.

### Contoh 2: Mendapatkan tag menurut nama
```powershell
Get-AzTag -Name "Department"
```

```output
Name:   Department
Count:  5
Values: 

        Name        Count
        ==========  =====

        Finance       2
        IT            3
```

Perintah ini mendapatkan informasi terperinci tentang tag Departemen dan nilainya.
Properti Hitung memperlihatkan berapa kali tag dan setiap nilainya telah diterapkan ke sumber daya dan grup sumber daya dalam langganan.

### Contoh 3: Mendapatkan nilai semua tag
```powershell
Get-AzTag -Detailed
```

```output
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

Perintah ini menggunakan parameter *Terperinci* untuk mendapatkan informasi terperinci tentang semua tag yang telah ditentukan sebelumnya dalam langganan.
Menggunakan parameter *Terperinci* setara dengan menggunakan parameter *Nama* untuk setiap tag.

### Contoh 4: Mendapatkan seluruh set tag pada langganan

```powershell
Get-AzTag -ResourceId /subscriptions/{subId}
```

```output
Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             tagKey1  tagValue1
             tagKey2  tagValue2
```

Perintah ini mendapatkan seluruh set tag pada langganan dengan {subId}.

### Contoh 5: Mendapatkan seluruh set tag pada sumber daya

```powershell
Get-AzTag -ResourceId /subscriptions/{subId}/resourcegroups/{rg}/providers/Microsoft.Sql/servers/Server1
```

```output
Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             Dept     Finance
             Status   Normal
```

Perintah ini mendapatkan seluruh set tag pada sumber daya dengan {resourceId}.

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

### -Terperinci
Menunjukkan bahwa operasi ini menambahkan informasi tentang nilai tag ke output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetPredefinedTagParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama tag yang telah ditentukan sebelumnya.
Secara default, **Get-AzTag** mendapatkan informasi dasar tentang semua tag yang telah ditentukan sebelumnya dalam langganan.
Saat Anda menentukan parameter *Nama* , parameter *Terperinci* tidak berpengaruh.

```yaml
Type: System.String
Parameter Sets: GetPredefinedTagParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya untuk entitas yang diberi tag. Sumber daya, grup sumber daya, atau langganan dapat ditandai.

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag | Microsoft.Azure.Commands.Tags.Model.PSTagResource

## NOTES

## RELATED LINKS

[New-AzTag](./New-AzTag.md)

[Remove-AzTag](./Remove-AzTag.md)

[Update-AzTag](./Update-AzTag.md)
