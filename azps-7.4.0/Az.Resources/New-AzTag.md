---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 23DB0AD2-7EB7-4373-BB8D-BB6CB651DD54
online version: https://docs.microsoft.com/powershell/module/az.resources/new-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzTag.md
ms.openlocfilehash: 4f856aa8de004429376e8ab2113ef64ad2c231fc
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144727198"
---
# New-AzTag

## SYNOPSIS
Membuat tag Azure yang telah ditentukan sebelumnya atau menambahkan nilai ke tag yang sudah ada | Membuat atau memperbarui seluruh kumpulan tag pada sumber daya atau langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/new-aztag) untuk informasi terbaru.

## SYNTAX

### CreatePredefinedTagParameterSet
```
New-AzTag [-Name] <String> [[-Value] <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CreateByResourceIdParameterSet
```
New-AzTag [-ResourceId] <String> [-Tag] <Hashtable> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

**CreatePredefinedTagSet**: Cmdlet **New-AzTag** membuat tag Azure yang telah ditentukan sebelumnya dengan nilai opsional yang telah ditentukan sebelumnya.
Anda juga dapat menggunakannya untuk menambahkan nilai tambahan ke tag yang sudah ditentukan sebelumnya.
Untuk membuat tag yang telah ditentukan sebelumnya, masukkan nama tag unik.
Untuk menambahkan nilai ke tag yang sudah ditentukan sebelumnya, tentukan nama tag yang ada dan nilai baru.
Cmdlet ini mengembalikan objek yang mewakili tag baru atau yang dimodifikasi dengan nilainya dan jumlah sumber daya yang telah diterapkannya.
Modul Azure Tags yang merupakan bagian dari **New-AzTag** dapat membantu Anda mengelola tag Azure yang telah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat Anda gunakan untuk mengategorikan sumber daya Azure dan grup sumber daya Anda, seperti berdasarkan departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda dapat menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang telah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.
Untuk menerapkan tag yang telah ditentukan sebelumnya ke sumber daya atau grup sumber daya, gunakan parameter *Tag* cmdlet New-AzTag.
Untuk mencari grup sumber daya dengan nama atau nama dan nilai tag tertentu, gunakan parameter *Tag* cmdlet Get-AzResourceGroup.
Setiap tag memiliki nama.
Nilai bersifat opsional.
Tag Azure yang telah ditentukan sebelumnya dapat memiliki beberapa nilai, tetapi saat Anda menerapkan tag ke sumber daya atau grup sumber daya, Anda menerapkan nama tag dan hanya salah satu nilainya.
Misalnya, Anda dapat membuat tag Departemen yang telah ditentukan sebelumnya dengan nilai untuk setiap departemen, seperti Keuangan, Sumber Daya Manusia, dan IT.
Saat Anda menerapkan tag Departemen ke sumber daya, Anda hanya menerapkan satu nilai yang telah ditentukan sebelumnya, seperti Keuangan.

**CreateByResourceIdParameterSet**: Cmdlet **New-AzTag** dengan **ResourceId** membuat atau memperbarui seluruh kumpulan tag pada sumber daya atau langganan.
Operasi ini memungkinkan penambahan atau mengganti seluruh set tag pada sumber daya atau langganan yang ditentukan. Entitas yang ditentukan dapat memiliki maksimal 50 tag.

## EXAMPLES

### Contoh 1: Membuat tag yang telah ditentukan sebelumnya
```powershell
New-AzTag -Name "FY2015"
```

```output
Name   ValuesTable Count Values 
----   ----------- ----- ------
FY2015             0     {}
```

Perintah ini membuat tag yang telah ditentukan sebelumnya bernama FY2015.
Tag ini tidak memiliki nilai.
Anda dapat menerapkan tag tanpa nilai ke sumber daya atau grup sumber daya, atau menggunakan **New-AzTag** untuk menambahkan nilai ke tag.
Anda juga dapat menentukan nilai saat menerapkan tag ke sumber daya atau grup sumber daya.

### Contoh 2: Membuat tag yang telah ditentukan sebelumnya dengan nilai
```powershell
New-AzTag -Name "Department" -Value "Finance"
```

```output
Name:   Department
Count:  0
Values: 

        Name        Count
        =========   =====
        Finance     0
```

Perintah ini membuat tag yang telah ditentukan sebelumnya bernama Departemen dengan nilai Keuangan.

### Contoh 3: Menambahkan nilai ke tag yang telah ditentukan sebelumnya
```powershell
New-AzTag -Name "Department" -Value "Finance"

Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0 
New-AzTag -Name "Department" -Value "IT"
Name:   Department
Count:  0
Values: 
        Name        Count
        =========   =====
        Finance     0
        IT          0
```

Perintah ini membuat tag yang telah ditentukan sebelumnya bernama Departemen dengan dua nilai.
Jika nama tag ada, **New-AzTag** menambahkan nilai ke tag yang ada alih-alih membuat yang baru.

### Contoh 4: Menggunakan tag yang telah ditentukan sebelumnya
```powershell
New-AzTag -Name "CostCenter" -Value "0001"
Name:   CostCenter
Count:  0
Values: 
        Name        Count
        =========   =====
        0001        0 
Set-AzResourceGroup -Name "EngineerBlog" -Tag @{Name="CostCenter";Value="0001"}
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
Get-AzTag -Name "CostCenter"
Name:   CostCenter
Count:  1
Values: 
        Name        Count
        =========   =====
        0001        1 
Get-AzResourceGroup -Tag @{Name="CostCenter"}
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

Perintah dalam contoh ini membuat dan menggunakan tag yang telah ditentukan sebelumnya.

### Contoh 5: Membuat atau memperbarui seluruh kumpulan tag pada langganan

```powershell
$Tags = @{"tagKey1"="tagValue1"; "tagKey2"="tagValue2"}
New-AzTag -ResourceId /subscriptions/{subId} -Tag $Tags
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

Perintah ini membuat atau memperbarui seluruh kumpulan tag pada langganan dengan {subId}.

### Contoh 6: Membuat atau memperbarui seluruh kumpulan tag pada sumber daya

```powershell
$Tags = @{"Dept"="Finance"; "Status"="Normal"}
New-AzTag -ResourceId /subscriptions/{subId}/resourcegroups/{rg}/providers/Microsoft.Sql/servers/Server1 -Tag $Tags
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

Perintah ini membuat atau memperbarui seluruh kumpulan tag pada sumber daya dengan {resourceId}.

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

### -Name
Menentukan nama tag yang telah ditentukan sebelumnya.
Untuk membuat tag baru yang telah ditentukan sebelumnya, masukkan nama unik.
Untuk menambahkan nilai ke tag yang sudah ada, masukkan nama tag yang ada.
Jika tag yang sudah ditentukan sebelumnya memiliki nama yang ditentukan, **New-AzTag** menambahkan nilai yang ditentukan, jika ada, ke tag dengan nama tersebut alih-alih membuat tag baru.

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

### -ResourceId
Pengidentifikasi sumber daya untuk entitas yang ditandai. Sumber daya, grup sumber daya, atau langganan dapat ditandai.

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

### -Nilai
Menentukan nilai tag yang telah ditentukan sebelumnya.
Tag yang telah ditentukan sebelumnya dapat memiliki beberapa nilai, tetapi Anda hanya dapat memasukkan satu nilai di setiap perintah.
Parameter ini bersifat opsional, karena tag dapat memiliki nama tanpa nilai.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag | Microsoft.Azure.Commands.Tags.Model.PSTagResource

## NOTES

## RELATED LINKS

[Get-AzTag](./Get-AzTag.md)

[Remove-AzTag](./Remove-AzTag.md)

[Update-AzTag](./Update-AzTag.md)
