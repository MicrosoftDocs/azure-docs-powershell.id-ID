---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 07c6e327-05f4-4279-a5fb-d4e860c897d4
online version: https://docs.microsoft.com/powershell/module/az.resources/update-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzTag.md
ms.openlocfilehash: 8179e0ecdd0a14a9d0de7e7b4916fb24e6e654cc
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145512430"
---
# Update-AzTag

## SYNOPSIS

Memperbarui kumpulan tag secara selektif pada sumber daya atau langganan.

## SYNTAX

```
Update-AzTag [-ResourceId] <String> [-Tag] <Hashtable> [-Operation] <TagPatchOperation>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Update-AzTag** dengan **ResourceId** secara selektif memperbarui kumpulan tag pada sumber daya atau langganan.
Operasi ini memungkinkan mengganti, menggabungkan, atau secara selektif menghapus tag pada sumber daya atau langganan yang ditentukan. Entitas yang ditentukan dapat memiliki maksimum 50 tag di akhir operasi. Opsi 'ganti' menggantikan seluruh set tag yang ada dengan set baru. Opsi 'gabungkan' memungkinkan penambahan tag dengan nama baru dan memperbarui nilai tag dengan nama yang ada. Opsi 'hapus' memungkinkan penghapusan tag secara selektif berdasarkan nama atau pasangan nama/nilai yang diberikan.

## EXAMPLES

### Contoh 1: Memperbarui kumpulan tag secara selektif pada langganan dengan Operasi "Gabungkan"

```powershell
$mergedTags = @{"key1"="value1"; "key3"="value3";}
Update-AzTag -ResourceId /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Tag $mergedTags -Operation Merge
```

```output
Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             key1     value1
             key2     value2
             key3     value3
```

Perintah ini Menggabungkan kumpulan tag pada langganan dengan "xxxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxx".

### Contoh 2: Secara selektif memperbarui kumpulan tag pada langganan dengan Operasi "Ganti"

```powershell
$replacedTags = @{"key1"="value1"; "key3"="value3";}
Update-AzTag -ResourceId /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Tag $replacedTags -Operation Replace
```

```output
Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             key1     value1
             key3     value3
```

Perintah ini Menggantikan kumpulan tag pada langganan dengan "xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxx".

### Contoh 3: Memperbarui kumpulan tag secara selektif pada langganan dengan Operasi "Hapus"

```powershell
$deletedTags = @{"key1"="value1"}
Update-AzTag -ResourceId /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Tag $deletedTags -Operation Delete
```

```output
Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             key3     value3
```

Perintah ini Menghapus kumpulan tag pada langganan dengan "xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxx".

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

### -Operasi
Operasi pembaruan. Opsinya adalah Gabungkan, Ganti, dan Hapus.

```yaml
Type: Microsoft.Azure.Commands.Tags.Model.TagPatchOperation
Parameter Sets: (All)
Aliases:
Accepted values: Merge, Replace, Delete

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya untuk entitas yang diberi tag. Sumber daya, grup sumber daya, atau langganan dapat ditandai.

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

### -Tag
Kumpulan tag yang akan digunakan untuk pembaruan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
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

### Microsoft.Azure.Commands.Tags.Model.TagPatchOperation

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTagResource

## NOTES

## RELATED LINKS

[Get-AzTag](./Get-AzTag.md)

[New-AzTag](./New-AzTag.md)

[Remove-AzTag](./Remove-AzTag.md)
