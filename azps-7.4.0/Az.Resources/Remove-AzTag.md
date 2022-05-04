---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 66B25541-0FA5-46CF-90D8-FE9527BE11C6
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzTag.md
ms.openlocfilehash: b5f241658164ff2c89f2b270fe388ecfc3a1af09
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144618566"
---
# Remove-AzTag

## SYNOPSIS
Menghapus tag atau nilai Azure yang telah ditentukan sebelumnya | Menghapus seluruh kumpulan tag pada sumber daya atau langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-aztag) untuk informasi terbaru.

## SYNTAX

### RemovePredefinedTagParameterSet
```
Remove-AzTag [-Name] <String> [[-Value] <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByResourceIdParameterSet
```
Remove-AzTag [-PassThru] -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

**RemovePredefinedTagSet**: Cmdlet **Remove-AzTag** menghapus tag dan nilai Azure yang telah ditentukan sebelumnya dari langganan Anda.
Untuk menghapus nilai tertentu dari tag yang telah ditentukan sebelumnya, gunakan parameter *Nilai* .
Secara default, **Remove-AzTag** menghapus tag yang ditentukan dan semua nilainya. Anda tidak dapat menghapus tag atau nilai yang saat ini diterapkan ke grup sumber daya atau sumber daya.
Sebelum menggunakan **Remove-AzTag**, gunakan parameter *Tag* cmdlet Set-AzResourceGroup untuk menghapus tag atau nilai dari sumber daya atau grup sumber daya.
Modul Tag Azure yang merupakan bagian dari **Remove-AzTag** dapat membantu Anda mengelola tag Azure yang telah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat Anda gunakan untuk mengategorikan sumber daya Azure dan grup sumber daya Anda, seperti berdasarkan departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda dapat menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang telah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.

**RemoveByResourceIdParameterSet**: Cmdlet **Remove-AzTag** dengan **ResourceId** menghapus seluruh set tag pada sumber daya atau langganan.

## EXAMPLES

### Contoh 1: Menghapus tag yang telah ditentukan sebelumnya
```powershell
Remove-AzTag -Name "Department"
```

Perintah ini menghapus tag yang telah ditentukan sebelumnya bernama Departemen dan semua nilainya.
Jika tag telah diterapkan ke sumber daya atau grup sumber daya apa pun, perintah gagal.

### Contoh 2: Menghapus nilai dari tag yang telah ditentukan sebelumnya
```powershell
Remove-AzTag -Name "Department" -Value "HumanResources" -PassThru
```

```output
Name:   Department
Count:  14
Values: 

        Name        Count
        =========   =====

        Finance        2
        IT            12
```

Perintah ini menghapus nilai HumanResources dari tag Departemen yang telah ditentukan sebelumnya.
Ini tidak menghapus tag.
Jika nilai telah diterapkan ke sumber daya atau grup sumber daya apa pun, perintah gagal.

### Contoh 3: Menghapus seluruh kumpulan tag pada langganan

```powershell
Remove-AzTag -ResourceId /subscriptions/{subId}
```

Perintah ini menghapus seluruh kumpulan tag pada langganan dengan {subId}. Ini tidak akan mengembalikan objek yang dihapus jika tidak melewati "-PassThru".

### Contoh 4: Menghapus seluruh kumpulan tag pada sumber daya

```powershell
Remove-AzTag -ResourceId /subscriptions/{subId}/resourcegroups/{rg}/providers/Microsoft.Sql/servers/Server1 -PassThru
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

Perintah ini menghapus seluruh kumpulan tag pada sumber daya dengan {resourceId}. Ini mengembalikan oktet yang dihapus saat meneruskan "-PassThru".

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
Menentukan Nama tag yang telah ditentukan sebelumnya untuk dihapus.
Secara default, **Remove-AzTag** menghapus tag yang ditentukan dan semua nilainya.
Untuk menghapus nilai yang dipilih, tetapi tidak menghapus tag, gunakan parameter *Nilai* .

```yaml
Type: System.String
Parameter Sets: RemovePredefinedTagParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili tag yang dihapus atau tag yang dihasilkan dengan nilai yang dihapus.

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

### -ResourceId
Pengidentifikasi sumber daya untuk entitas yang diberi tag. Sumber daya, grup sumber daya, atau langganan dapat ditandai.

```yaml
Type: System.String
Parameter Sets: RemoveByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nilai
Menghapus nilai yang ditentukan dari tag yang telah ditentukan sebelumnya, tetapi tidak menghapus tag.

```yaml
Type: System.String[]
Parameter Sets: RemovePredefinedTagParameterSet
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

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag | Microsoft.Azure.Commands.Tags.Model.PSTagResource

## NOTES

## RELATED LINKS

[Get-AzTag](./Get-AzTag.md)

[New-AzTag](./New-AzTag.md)

[Update-AzTag](./Update-AzTag.md)
