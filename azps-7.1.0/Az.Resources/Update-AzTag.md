---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Tags.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 07c6e327-05f4-4279-a5fb-d4e860c897d4
online version: https://docs.microsoft.com/powershell/module/az.resources/update-aztag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzTag.md
ms.openlocfilehash: 0c1affa452a6e58312a90a8a1e92d7c9bc41f9ba
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136709076"
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

Cmdlet **Update-AzTag** dengan **ResourceId secara** selektif memperbarui kumpulan tag pada sumber daya atau langganan.
Operasi ini memungkinkan penggantian, penggabungan, atau penghapusan tag secara selektif pada sumber daya atau langganan yang ditentukan. Entitas yang ditentukan bisa memiliki maksimal 50 tag di akhir operasi. Opsi 'ganti' menggantikan seluruh rangkaian tag yang sudah ada dengan kumpulan baru. Opsi 'gabungkan' memungkinkan menambahkan tag dengan nama baru dan memperbarui nilai tag dengan nama yang sudah ada. Opsi 'hapus' memungkinkan penghapusan tag secara selektif berdasarkan nama atau pasangan nama/nilai tertentu.

## EXAMPLES

### Contoh 1: Secara selektif memperbarui kumpulan tag pada langganan dengan Operasi "Gabungkan"

```powershell
PS C:\>$mergedTags = @{"key1"="value1"; "key3"="value3";}
PS C:\>Update-AzTag -ResourceId /subscriptions/{subId} -Tag $mergedTags -Operation Merge

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

Perintah ini Menggabungkan serangkaian tag pada langganan dengan {subId}.

### Contoh 2: Memperbarui kumpulan tag secara selektif di langganan dengan Operasi "Ganti"

```powershell
PS C:\>$replacedTags = @{"key1"="value1"; "key3"="value3";}
PS C:\>Update-AzTag -ResourceId /subscriptions/{subId} -Tag $replacedTags -Operation Replace

Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             key1     value1
             key3     value3
```

Perintah ini Mengganti serangkaian tag pada langganan dengan {subId}.

### Contoh 3: Memperbarui kumpulan tag secara selektif di langganan dengan Operasi "Hapus"

```powershell
PS C:\>$deletedTags = @{"key1"="value1"}
PS C:\>Update-AzTag -ResourceId /subscriptions/{subId} -Tag $deletedTags -Operation Delete

Id         : {Id}
Name       : {Name}
Type       : {Type}
Properties :
             Name     Value
             =======  =========
             key3     value3
```

Perintah ini Menghapus serangkaian tag pada langganan dengan {subId}.

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
Pengidentifikasi sumber daya untuk entitas yang ditandai. Sumber daya, grup sumber daya atau langganan mungkin ditandai.

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

### Microsoft.Azure.Commands.Tags.Model.TagPatchOperation

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTagResource

## CATATAN

## RELATED LINKS

[Get-AzTag](./Get-AzTag.md)

[New-AzTag](./New-AzTag.md)

[Remove-AzTag](./Remove-AzTag.md)
