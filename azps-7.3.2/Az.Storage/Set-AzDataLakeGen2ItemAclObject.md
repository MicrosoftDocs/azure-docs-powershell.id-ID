---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azdatalakegen2itemaclobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzDataLakeGen2ItemAclObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzDataLakeGen2ItemAclObject.md
ms.openlocfilehash: 9e0bd10918adfe46871bec4d9f59815cce136aa9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140570357"
---
# Set-AzDataLakeGen2ItemAclObject

## SYNOPSIS
Membuat/Memperbarui objek ACL item DataLake gen2, yang dapat digunakan Update-AzDataLakeGen2Item cmdlet.

## SYNTAX

```
Set-AzDataLakeGen2ItemAclObject [-EntityId <String>] [-DefaultScope] -Permission <String>
 [-InputObject <PSPathAccessControlEntry[]>] -AccessControlType <AccessControlType> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDataLakeGen2ItemAclObject** membuat/memperbarui objek ACL item DataLake gen2, yang dapat digunakan Update-AzDataLakeGen2Item cmdlet.
Jika entri ACL baru dengan AccessControlType/EntityId/DefaultScope yang sama tidak ada di ACL input, akan membuat entri ACL baru, izin pembaruan lain dari entri ACL yang sudah ada.

## EXAMPLES

### Contoh 1: Buat objek ACL dengan entri 3 ACL, dan perbarui ACL di direktori
```
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType user -Permission rwx -DefaultScope
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType group -Permission rw- -InputObject $acl 
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType other -Permission "rw-" -InputObject $acl
PS C:\>Update-AzDataLakeGen2Item -FileSystem "filesystem1" -Path "dir1/dir3" -ACL $acl

   FileSystem Name: filesystem1

Path                 IsDirectory  Length          LastModified         Permissions  Owner                Group               
----                 -----------  ------          ------------         -----------  -----                -----               
dir1/dir3            True                         2020-03-23 09:34:31Z rwxrw-rw-+   $superuser           $superuser
```

Perintah ini membuat objek ACL dengan entri 3 ACL (gunakan parameter -InputObject untuk menambahkan entri acl ke objek acl yang sudah ada), dan memperbarui ACL di direktori.

### Contoh 2: Membuat objek ACL dengan 4 entri ACL, dan memperbarui izin untuk entri ACL yang sudah ada
```
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType user -Permission rwx -DefaultScope
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType group -Permission rw- -InputObject $acl 
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType other -Permission "rw-" -InputObject $acl
PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType user -EntityId $id -Permission rwx -InputObject $acl 
PS C:\>$acl

DefaultScope AccessControlType EntityId                             Permissions
------------ ----------------- --------                             -----------
True         User                                                   rwx        
False        Group                                                  rw-        
False        Other                                                  rw-        
False        User              ********-****-****-****-************ rwx        

PS C:\>$acl = Set-AzDataLakeGen2ItemAclObject -AccessControlType user -EntityId $id -Permission r-x -InputObject $acl 
PS C:\>$acl  

DefaultScope AccessControlType EntityId                             Permissions
------------ ----------------- --------                             -----------
True         User                                                   rwx        
False        Group                                                  rw-        
False        Other                                                  rw-        
False        User              ********-****-****-****-************ r-x
```

Perintah ini pertama-pertama membuat objek ACL dengan 4 entri ACL, lalu menjalankan cmdlet lagi dengan izin berbeda tetapi AccessControlType/EntityId/DefaultScope yang ada dari entri ACL yang sudah ada.
Lalu izin entri ACL diperbarui, tetapi tidak ada entri ACL baru yang ditambahkan.

## PARAMETERS

### -AccessControlType
Ada empat tipe: "pengguna" memberikan hak kepada pemilik atau pengguna bernama, "grup" memberikan hak kepada grup pemilik atau grup bernama, "masker" membatasi hak yang diberikan kepada pengguna bernama dan anggota grup, dan "lainnya" memberikan hak kepada semua pengguna yang tidak ditemukan dalam entri lain.

```yaml
Type: Azure.Storage.Files.DataLake.Models.AccessControlType
Parameter Sets: (All)
Aliases:
Accepted values: User, Group, Mask, Other

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultScope
Atur parameter ini untuk menunjukkan ACE milik ACL default untuk direktori; jika tidak, lingkupnya implisit dan ACE berada di access ACL.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntityId
Pengidentifikasi pengguna atau grup.
Itu dihilangkan untuk entri "mask" dan "other" AccessControlType.
Pengidentifikasi pengguna atau grup juga dihilangkan untuk pemilik dan grup pemilik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Jika memasukkan objek PSPathAccessControlEntry\[\] , akan menambahkan ACL baru sebagai elemen baru dari objek input PSPathAccessControlEntry\[\] .

```yaml
Type: Microsoft.WindowsAzure.Commands.Storage.Model.ResourceModel.PSPathAccessControlEntry[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Permission
Bidang izin adalah urutan 3 karakter di mana karakter pertama adalah 'r' untuk memberikan akses baca, karakter kedua adalah 'w' untuk memberikan akses tertulis, dan karakter ketiga adalah 'x' untuk memberikan izin jalankan.
Jika akses tidak diberikan, karakter '-' digunakan untuk menunjukkan bahwa izin ditolak.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.WindowsAzure.Commands. Storage. Model.ResourceModel.PSPathAccessControlEntry

## CATATAN

## RELATED LINKS
