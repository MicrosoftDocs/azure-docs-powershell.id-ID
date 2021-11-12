---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 3CD1A989-902C-48B3-81E9-7B78EDA5F880
online version: ''
schema: 2.0.0
ms.openlocfilehash: f230139e201528eb1307ba852c2587a1d312ab67
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424109"
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
Cmdlet **Remove-AzureAccount** menghapus akun Azure dan langganannya dari file data langganan di profil pengguna roaming.
Tindakan ini tidak menghapus akun dari Microsoft Azure, atau mengubah akun sebenarnya dengan cara apa pun.

Menggunakan cmdlet ini sangat mirip dengan keluar dari akun Azure Anda.
Dan, jika Anda ingin masuk lagi ke akun tersebut, gunakan **Add-AzureAccount** atau **Import-AzurePublishSettingsFile** untuk menambahkan akun Windows PowerShell lagi.

Anda juga dapat **menggunakan cmdlet Remove-AzureAccount** untuk mengubah cara cmdlet Azure PowerShell masuk ke akun Azure.
Jika akun Anda memiliki sertifikat manajemen dari **Import-AzurePublishSettingsFile** dan token akses dari **Add-AzureAccount,** cmdlet Azure PowerShell hanya menggunakan token akses; mereka mengabaikan sertifikat manajemen.
Untuk menggunakan sertifikat manajemen, jalankan **Remove-AzureAccount**.
Ketika **Remove-AzureAccount** menemukan sertifikat manajemen dan token akses, ia hanya akan menghapus token akses, bukan menghapus akun.
Sertifikat manajemen masih ada, sehingga akun masih tersedia untuk Windows PowerShell.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Hapus akun
```
PS C:\> Remove-AzureAccount -Name admin@contoso.com
```

Perintah ini akan menghapus admin@contoso.com file data langganan Anda.
Ketika perintah selesai, akun tidak lagi tersedia untuk Windows PowerShell.

## PARAMETERS

### -Force
Menyembunyikan perintah konfirmasi.
Secara default, **Hapus-AzureAccount** akan meminta Anda sebelum menghapus akun dari Windows PowerShell.

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
Nilai parameter peka huruf besar/kecil.
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
Mengembalikan $True jika perintah berhasil $False jika gagal.
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
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak Ada atau System.Boolean
Jika Anda menggunakan parameter *PassThru,* cmdlet ini mengembalikan nilai Boolean.
Jika tidak, output tidak akan dikembalikan.

## CATATAN

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzureAccount](./Get-AzureAccount.md)


