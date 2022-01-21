---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 23DB0AD2-7EB7-4373-BB8D-BB6CB651DD54
online version: https://docs.microsoft.com/powershell/module/az.resources/new-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzTag.md
ms.openlocfilehash: 2e28f5107984a6522ff24109872ad9203848976c
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136558726"
---
# New-AzTag

## SYNOPSIS
Membuat tag Azure yang sudah ditentukan sebelumnya atau menambahkan nilai ke tag yang sudah | Membuat atau memperbarui seluruh kumpulan tag pada sumber daya atau langganan.

## SYNTAX

### CreatePredefinedTagParameterSet

```powershell
New-AzTag [-Name] <String> [[-Value] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### CreateByResourceIdParameterSet

```powershell
New-AzTag
   -ResourceId <String>
   -Tag <Hashtable>
   [-DefaultProfile <IAzureContextContainer>]
   [-WhatIf]
   [-Confirm]
   [<CommonParameters>]
```

## DESCRIPTION

**CreatePredefinedTagSet**: Cmdlet **New-AzTag** membuat tag Azure yang sudah ditentukan sebelumnya dengan nilai opsional yang sudah ditentukan sebelumnya.
Anda juga bisa menggunakannya untuk menambahkan nilai tambahan ke tag yang sudah ditentukan sebelumnya yang sudah ada.
Untuk membuat tag yang sudah ditentukan sebelumnya, masukkan nama tag unik.
Untuk menambahkan nilai ke tag yang sudah ditentukan sebelumnya yang sudah ada, tentukan nama tag yang sudah ada dan nilai baru.
Cmdlet ini mengembalikan objek yang mewakili tag baru atau yang dimodifikasi dengan nilainya dan jumlah sumber daya yang diterapkan.
Modul Tag Azure yang **merupakan bagian dari Modul Azure** merupakan bagian darinya yang bisa membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat digunakan untuk mengategorikan sumber daya dan grup sumber daya Azure, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menetapkan dan menerapkan tag dalam satu langkah, tapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan yang bisa diprediksi untuk tag di langganan Anda.
Untuk menerapkan tag yang sudah ditentukan sebelumnya ke sumber daya atau grup sumber daya, gunakan parameter *Tag* New-AzTag cmdlet.
Untuk mencari grup sumber daya dengan nama atau nama dan nilai tag yang *ditentukan,* gunakan parameter Tag Get-AzResourceGroup cmdlet.
Setiap tag memiliki nama.
Nilainya bersifat opsional.
Tag Azure yang sudah ditentukan sebelumnya bisa memiliki beberapa nilai, tapi saat Anda menerapkan tag ke sumber daya atau grup sumber daya, Anda menerapkan nama tag dan hanya salah satu nilainya.
Misalnya, Anda dapat membuat tag Departemen yang sudah ditentukan sebelumnya dengan nilai untuk setiap departemen, seperti Keuangan, Sumber Daya Manusia, dan IT.
Saat Anda menerapkan tag Departemen ke sumber daya, Anda hanya menerapkan satu nilai yang sudah ditentukan sebelumnya, seperti Keuangan.

**CreateByResourceIdParameterSet**: Cmdlet **New-AzTag** dengan **ResourceId** membuat atau memperbarui seluruh kumpulan tag pada sumber daya atau langganan.
Operasi ini memungkinkan penambahan atau penggantian seluruh rangkaian tag pada sumber daya atau langganan yang ditentukan. Entitas yang ditentukan bisa memiliki maksimal 50 tag.

## EXAMPLES

### Contoh 1: Membuat tag yang sudah ditentukan sebelumnya
```powershell
PS C:\>New-AzTag -Name "FY2015"
                                
Name   ValuesTable Count Values 
----   ----------- ----- ------
FY2015             0     {}
```

Perintah ini akan membuat tag yang sudah ditentukan sebelumnya bernama FY2015.
Tag ini tidak memiliki nilai.
Anda bisa menerapkan tag tanpa nilai ke sumber daya atau grup sumber daya, atau gunakan **AzTag Baru** untuk menambahkan nilai ke tag.
Anda juga bisa menentukan nilai saat Anda menerapkan tag ke grup sumber daya atau sumber daya.

### Contoh 2: Membuat tag yang sudah ditentukan sebelumnya dengan nilai
```powershell
PS C:\>New-AzTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values: 

        Name        Count
        =========   =====
        Finance     0
```

Perintah ini akan membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan nilai Keuangan.

### Contoh 3: Menambahkan nilai ke tag yang sudah ditentukan sebelumnya
```powershell
PS C:\>New-AzTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0 
PS C:\>New-AzTag -Name "Department" -Value "IT"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0
        IT          0
```

Perintah ini membuat tag yang sudah ditentukan sebelumnya bernama Departemen dengan dua nilai.
Jika nama tag ada, **New-AzTag** menambahkan nilai ke tag yang sudah ada, bukan membuat yang baru.

### Contoh 4: Menggunakan tag yang sudah ditentukan sebelumnya
```powershell
PS C:\>New-AzTag -Name "CostCenter" -Value "0001"
Name:   CostCenter
Count:  0
Values: 
        Name        Count
        =========   =====
        0001        0 
PS C:\>Set-AzResourceGroup -Name "EngineerBlog" -Tag @{Name="CostCenter";Value="0001"}
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
PS C:\>Get-AzTag -Name "CostCenter"
Name:   CostCenter
Count:  1
Values: 
        Name        Count
        =========   =====
        0001        1 
PS C:\>Get-AzResourceGroup -Tag @{Name="CostCenter"}
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

### Contoh 5: Membuat atau memperbarui seluruh rangkaian tag pada langganan

```powershell
PS C:\>$Tags = @{"tagKey1"="tagValue1"; "tagKey2"="tagValue2"}
PS C:\>New-AzTag -ResourceId /subscriptions/{subId} -Tag $Tags

Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             tagKey1  tagValue1
             tagKey2  tagValue2
```

Perintah ini akan membuat atau memperbarui seluruh rangkaian tag pada langganan dengan {subId}.

### Contoh 6: Membuat atau memperbarui seluruh rangkaian tag pada sumber daya

```powershell
PS C:\>$Tags = @{"Dept"="Finance"; "Status"="Normal"}
PS C:\>New-AzTag -ResourceId /subscriptions/{subId}/resourcegroups/{rg}/providers/Microsoft.Sql/servers/Server1 -Tag $Tags

Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             Dept     Finance
             Status   Normal
```

Perintah ini membuat atau memperbarui seluruh kumpulan tag pada sumber daya dengan {resourceId}.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Nama
Menentukan nama tag yang sudah ditentukan sebelumnya.
Untuk membuat tag baru yang sudah ditentukan sebelumnya, masukkan nama yang unik.
Untuk menambahkan nilai ke tag yang sudah ada, masukkan nama tag yang sudah ada.
Jika tag yang sudah ditentukan sebelumnya memiliki nama yang ditentukan, **New-AzTag** menambahkan nilai tertentu, jika ada, ke tag dengan nama itu alih-alih membuat tag baru.

```yaml
Type: System.String
Parameter Sets: CreatePredefinedTagParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Menentukan nilai tag yang sudah ditentukan sebelumnya.
Tag yang sudah ditentukan sebelumnya bisa memiliki beberapa nilai, tapi Anda hanya bisa memasukkan satu nilai dalam setiap perintah.
Parameter ini opsional, karena tag bisa memiliki nama tanpa nilai.

```yaml
Type: System.String
Parameter Sets: CreatePredefinedTagParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya untuk entitas yang ditandai. Sumber daya, grup sumber daya atau langganan mungkin ditandai.

```yaml
Type: System.String
Parameter Sets: CreateByResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tag yang akan diletakkan pada sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: CreateByResourceIdParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag | Microsoft.Azure.Commands.Tags.Model.PSTagResource

## CATATAN

## RELATED LINKS

[Get-AzTag](./Get-AzTag.md)

[Remove-AzTag](./Remove-AzTag.md)

[Update-AzTag](./Update-AzTag.md)