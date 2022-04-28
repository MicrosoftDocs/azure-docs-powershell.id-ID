---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeStore.dll-Help.xml
Module Name: Az.DataLakeStore
online version: https://docs.microsoft.com/powershell/module/az.datalakestore/export-azdatalakestorechilditemproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Export-AzDataLakeStoreChildItemProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Export-AzDataLakeStoreChildItemProperty.md
ms.openlocfilehash: 74c979efb7a1e46e795b08758c41ceebfb536e1b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144202823"
---
# Export-AzDataLakeStoreChildItemProperty

## SYNOPSIS
Mengekspor properti (Penggunaan disk dan Acl) untuk seluruh pohon dari jalur yang ditentukan ke jalur output

## SYNTAX

### GetDiskUsage
```
Export-AzDataLakeStoreChildItemProperty [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-OutputPath] <String> [-SaveToAdl] [-IncludeFile] [-MaximumDepth <Int32>] [-Concurrency <Int32>]
 [-GetDiskUsage] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### GetAllProperties
```
Export-AzDataLakeStoreChildItemProperty [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-OutputPath] <String> [-SaveToAdl] [-IncludeFile] [-MaximumDepth <Int32>] [-Concurrency <Int32>]
 [-GetDiskUsage] [-GetAcl] [-HideConsistentAcl] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetAclDump
```
Export-AzDataLakeStoreChildItemProperty [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-OutputPath] <String> [-SaveToAdl] [-IncludeFile] [-MaximumDepth <Int32>] [-Concurrency <Int32>] [-GetAcl]
 [-HideConsistentAcl] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Export-AzDataLakeStoreChildItemProperty** digunakan untuk melaporkan penggunaan ruang ADLS atau/dan penggunaan ACL untuk direktori tertentu dan sub direktori dan file.

## EXAMPLES

### Contoh 1: Dapatkan penggunaan disk dan penggunaan ACL untuk semua subdirektori dan file
```powershell
Export-AzDataLakeStoreChildItemProperty -Account ContosoADL -Path /a -OutputPath "C:\Users\contoso\Desktop\DumpFile.txt" -GetAcl -GetDiskUsage -IncludeFile
```

Dapatkan penggunaan disk dan penggunaan ACL untuk semua subdirektori dan file di bawah /a. IncludeFile memastikan penggunaan juga dilaporkan untuk file

### Contoh 2: Dapatkan penggunaan ACL untuk semua subdirektori dan file dengan ACL yang konsisten tersembunyi
```powershell
$fullAcl="user:contoso-userid:--x|user::rwx|other::---|group::rwx"
$newFullAcl = $fullAcl.Split("{|}");
Set-AzDataLakeStoreItemAcl -Account ContosoADL -Path /a -Acl $newFullAcl -Recurse -Debug

Export-AzDataLakeStoreChildItemProperty -Account ContosoADL -Path /a -OutputPath "C:\Users\contoso\Desktop\DumpFile.txt" -GetAcl -HideConsistentAcl -IncludeFile
```

Dapatkan penggunaan ACL untuk semua subdirektori dan file di bawah /a. IncludeFile memastikan penggunaan juga dilaporkan untuk file. HideconsistentAcl dalam hal ini akan menunjukkan Acl dari /a, bukan anak-anak karena semua anak memiliki acl yang sama dengan /a. Bendera ini melewati output acl subtree jika semua acl sama dengan root.

## PARAMETERS

### -Akun
Akun Data Lake Store untuk menjalankan operasi sistem file di

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konkurensi
Menunjukkan jumlah file/direktori yang diproses secara paralel.
Default akan dihitung sebagai upaya terbaik berdasarkan spesifikasi sistem.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -GetAcl
Mengambil acl yang dimulai dari jalur akar

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetAllProperties, GetAclDump
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GetDiskUsage
Mengambil penggunaan disk mulai dari jalur akar

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetDiskUsage, GetAllProperties
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HideConsistentAcl
Jangan tampilkan subtree direktori jika ACL sama di seluruh subtree. Ini membuatnya lebih mudah untuk hanya melihat jalur yang berbeda dengan ACL. Misalnya jika semua file dan folder di bawah /a/b sama, jangan tampilkan subtreeunder /a/b, dan hanya output /a/b dengan 'True' di kolom ACL KonsistenCannot diatur jika IncludeFiles tidak diatur, karena Acl yang konsisten tidak dapat ditentukan tanpa mengambil acl untuk file.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetAllProperties, GetAclDump
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFile
Tampilkan statistik pada tingkat file (defaultnya adalah menampilkan info tingkat direktori saja)

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

### -MaximumDepth
Kedalaman maksimum dari direktori akar sampai penggunaan disk atau acl ditampilkan

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputPath
Jalur ke file output. Dapat berupa Jalur lokal atau Jalur Adl. Secara default bersifat lokal. Jika SaveToAdl ditentukan, maka itu adalah jalur ADL di akun yang sama

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Menunjukkan respons boolean harus dikembalikan yang menunjukkan hasil operasi penghapusan.

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

### -Jalur
Jalur di akun Data Lake yang ditentukan yang harus diambil.
Dapat berupa file atau folder Dalam format '/folder/file.txt', di mana '/' pertama setelah DNS menunjukkan akar sistem file.

```yaml
Type: Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveToAdl
Jika diteruskan, maka simpan file cadangan ke ADL.
DumpFile wil menjadi jalur ADL dalam kasus itu

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance

### System.Management.Automation.SwitchParameter

### System.Int32

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
