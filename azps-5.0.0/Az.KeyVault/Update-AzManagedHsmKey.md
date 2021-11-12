---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/az.keyvault/update-azmanagedhsmkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/KeyVault/KeyVault/help/Update-AzManagedHsmKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/KeyVault/KeyVault/help/Update-AzManagedHsmKey.md
ms.openlocfilehash: 79d01f96fe776432f650d827b16ba83f48b84ddd
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409591"
---
# Update-AzManagedHsmKey

## SYNOPSIS
Memperbarui atribut kunci dalam HSM yang dikelola.

## SINTAKS

### Default (Default)
```
Update-AzManagedHsmKey [-HsmName] <String> [-Name] <String> [[-Version] <String>] [-Enable <Boolean>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-KeyOps <String[]>] [-Tag <Hashtable>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Update-AzManagedHsmKey [-InputObject] <PSKeyVaultKeyIdentityItem> [[-Version] <String>] [-Enable <Boolean>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-KeyOps <String[]>] [-Tag <Hashtable>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Update-AzManagedHsmKey** memperbarui atribut tombol yang dapat diedit di HSM yang dikelola.

## CONTOH

### Contoh 1: Ubah kunci untuk mengaktifkannya, serta atur tanggal kedaluwarsa dan tag
```powershell
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = 'true'}
PS C:\> Update-AzManagedHsmKey -HsmName testmhsm -Name testkey001 -Expires $Expires -Enable $True -Tag $Tags -PassThru

Vault/HSM Name : testmhsm
Name           : testkey001
Version        : 49b74a39dab605bd336628dc094dc31b
Id             : https://testmhsm.managedhsm.azure.net:443/keys/testkey001/49b74a39dab605bd336628dc094dc31b
Enabled        : True
Expires        : 10/14/2022 9:46:55 AM
Not Before     :
Created        : 10/14/2020 3:39:16 AM
Updated        : 10/14/2020 9:47:06 AM
Recovery Level : Recoverable+Purgeable
Tags           : Name        Value
                 Severity    high
                 Accounting  true
```

Perintah pertama membuat objek **DateTime** menggunakan cmdlet **Get-Date.** Objek tersebut menentukan waktu dua tahun di masa mendatang. Perintah menyimpan tanggal itu dalam $Expires variabel.
Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .
Perintah kedua membuat variabel untuk menyimpan nilai tag dengan tingkat keparahan tinggi dan Akuntansi.
Perintah terakhir mengubah kunci bernama testkey001. Perintah mengaktifkan kunci, mengatur waktu kedaluwarsanya ke waktu yang disimpan di $Expires, dan mengatur tag yang disimpan di $Tags.

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

### -Aktifkan
Nilai true mengaktifkan kunci dan nilai false akan menonaktifkan kunci tersebut.
Jika tidak ditentukan, status diaktifkan/dinonaktifkan yang sudah ada tetap tidak berubah.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kedaluwarsa
Waktu kedaluwarsa kunci dalam waktu UTC.
Jika tidak ditentukan, waktu kedaluwarsa kunci yang sudah ada tetap tidak berubah.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HsmName
Nama HSM. Cmdlet menyusun FQDN dari HSM yang dikelola berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek utama

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyOps
Operasi yang bisa dijalankan dengan kunci.
Jika tidak ditentukan, operasi kunci yang sudah ada dari kunci tetap tidak berubah.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kunci.
Cmdlet menyusun FQDN kunci dari nama HSM yang dikelola, lingkungan dan nama kunci yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotBefore
Waktu UTC sebelum kunci mana yang tidak bisa digunakan.
Jika tidak ditentukan, atribut NotBefore yang sudah ada dari kunci tetap tidak berubah.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, mengembalikan objek bundel tombol yang diperbarui.

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

### -Tag
Hashtable mewakili tag kunci.
Jika tidak ditentukan, tag kunci yang sudah ada tetap tidak berubah.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Versi
Versi utama.
Cmdlet menyusun FQDN kunci dari nama HSM yang dikelola, lingkungan yang saat ini dipilih, nama kunci dan versi kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: KeyVersion

Required: False
Position: 2
Default value: None
Accept pipeline input: False
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUT

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKey

## CATATAN

## LINK TERKAIT

[Add-AzManagedHsmKey](./Add-AzManagedHsmKey.md)

[Backup-AzManagedHsmKey](./Backup-AzManagedHsmKey.md)

[Remove-AzManagedHsmKey](./Remove-AzManagedHsmKey.md)

[Undo-AzManagedHsmKeyRemoval](./Undo-AzManagedHsmKeyRemoval.md)

[Get-AzManagedHsmKey](./Get-AzManagedHsmKey.md)

[Restore-AzManagedHsmKey](./Restore-AzManagedHsmKey.md)