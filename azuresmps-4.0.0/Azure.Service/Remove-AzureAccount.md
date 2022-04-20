---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 3CD1A989-902C-48B3-81E9-7B78EDA5F880
online version: ''
schema: 2.0.0
ms.openlocfilehash: f230139e201528eb1307ba852c2587a1d312ab67
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142655488"
---
# Remove-AzureAccount

## SYNOPSIS
Menghapus akun Azure dari Windows PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureAccount -Name <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Hapus-AzureAccount** menghapus akun Azure dan langganannya dari file data langganan di profil pengguna jelajah Anda.
Akun tersebut tidak menghapus akun dari Microsoft Azure, atau mengubah akun aktual dengan cara apa pun.

Menggunakan cmdlet ini sangat mirip dengan keluar dari akun Azure Anda.
Dan, jika Anda ingin masuk kembali ke akun tersebut, gunakan **Add-AzureAccount** atau **Impor-AzurePublishSettingsFile** untuk menambahkan akun ke Windows PowerShell lagi.

Anda juga bisa menggunakan cmdlet **Remove-AzureAccount** untuk mengubah cara cmdlet Azure PowerShell masuk ke akun Azure Anda.
Jika akun Anda memiliki sertifikat manajemen dari **Import-AzurePublishSettingsFile** dan token akses dari **Add-AzureAccount**, cmdlet Azure PowerShell hanya menggunakan token akses; mereka mengabaikan sertifikat manajemen.
Untuk menggunakan sertifikat manajemen, **jalankan Hapus-AzureAccount**.
Saat **Remove-AzureAccount** menemukan sertifikat manajemen dan token akses, token hanya akan menghapus token akses, bukan menghapus akun.
Sertifikat manajemen masih ada, sehingga akun masih tersedia untuk Windows PowerShell.

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Menghapus akun
```
PS C:\> Remove-AzureAccount -Name admin@contoso.com
```

Perintah ini menghapus admin@contoso.com file data langganan Anda.
Setelah perintah selesai, akun tidak lagi tersedia untuk Windows PowerShell.

## PARAMETERS

### -Paksa
Menyembunyikan perintah konfirmasi.
Secara default, **Remove-AzureAccount** meminta Anda sebelum menghapus akun dari Windows PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun yang akan dihapus.
Nilai parameter peka huruf besar kecil.
Karakter wildcard tidak didukung.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan $True jika perintah berhasil dan $False jika gagal.
Secara default, cmdlet ini tidak mengembalikan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak ada atau System.Boolean
Jika Anda menggunakan parameter *PassThru* , cmdlet ini mengembalikan nilai Boolean.
Jika tidak, tidak mengembalikan output apa pun.

## NOTES

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Dapatkan-AzureAccount](./Get-AzureAccount.md)


