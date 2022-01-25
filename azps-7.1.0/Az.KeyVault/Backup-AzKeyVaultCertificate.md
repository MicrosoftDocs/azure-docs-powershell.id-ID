---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultCertificate.md
ms.openlocfilehash: 89b79221eaa36f486e75a375083f01a27072ad2d
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136733549"
---
# Backup-AzKeyVaultCertificate

## SYNOPSIS
Mencadangkan sertifikat di kunci vault.

## SYNTAX

### ByCertificateName (Default)
```
Backup-AzKeyVaultCertificate [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByCertificate
```
Backup-AzKeyVaultCertificate [-InputObject] <PSKeyVaultCertificateIdentityItem> [[-OutputFile] <String>]
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzKeyVaultCertificate** mencadangkan sertifikat tertentu dalam kunci vault dengan mengunduh dan menyimpannya dalam sebuah file.
Jika sertifikat memiliki beberapa versi, semua versinya akan disertakan dalam cadangan.
Karena dienkripsi, konten yang diunduh tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan sertifikat yang dicadangkan ke vault kunci apa pun dalam langganan yang menjadi sumber cadangan, selama vault tersebut berada di Azure geography yang sama.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin mempertahankan salinan offline sertifikat jika Anda tidak sengaja menghapus yang asli dari vault.
 
- Anda membuat sertifikat menggunakan Key Vault dan sekarang ingin kloning objek ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzKeyVaultCertificate** untuk mengambil sertifikat dalam format terenkripsi lalu gunakan cmdlet **Restore-AzKeyVaultCertificate** dan menentukan kunci vault di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan sertifikat dengan nama file yang dihasilkan secara otomatis
```powershell
PS C:\Users\username\> Backup-AzKeyVaultCertificate -VaultName 'mykeyvault' -Name 'mycert'

C:\Users\username\mykeyvault-mycert-1527029447.01191
```

Perintah ini mengambil sertifikat yang bernama MyCert dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan sertifikat itu ke file yang otomatis dinamai untuk Anda, dan menampilkan nama file tersebut.

### Contoh 2: Mencadangkan sertifikat ke nama file tertentu
```powershell
PS C:\> Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyCert' -OutputFile 'C:\Backup.blob'

C:\Backup.blob
```

Perintah ini mengambil sertifikat yang bernama MyCert dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan sertifikat itu ke file bernama Backup.blob.

### Contoh 3: Mencadangkan sertifikat yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
PS C:\> $cert = Get-AzKeyVaultCertificate -VaultName 'MyKeyVault' -Name 'MyCert'
PS C:\> Backup-AzKeyVaultCertificate -Certificate $cert -OutputFile 'C:\Backup.blob' -Force

C:\Backup.blob
```

Perintah ini membuat cadangan sertifikat bernama $cert. Nama di vault bernama $cert. VaultName ke file bernama Backup.blob, akan menimpa file tanpa masalah jika file sudah ada.

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

### -Force
Menimpa file tertentu jika ada

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

### -InputObject
Rahasia untuk dicadangkan, dibuat salurannya dari output panggilan pengambilan.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateIdentityItem
Parameter Sets: ByCertificate
Aliases: Certificate

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama rahasia.
Cmdlet menyusun FQDN rahasia dari nama vault, lingkungan yang saat ini dipilih dan nama rahasia.

```yaml
Type: System.String
Parameter Sets: ByCertificateName
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFile
File output.
File output untuk menyimpan cadangan sertifikat.
Jika tidak ditentukan, nama file default akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama Vault.
Cmdlet menyusun FQDN dari vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: ByCertificateName
Aliases:

Required: True
Position: 0
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

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateIdentityItem

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS
