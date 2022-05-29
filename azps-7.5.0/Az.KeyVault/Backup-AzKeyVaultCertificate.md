---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultCertificate.md
ms.openlocfilehash: 64f81866b1e61459c2f2042c4bec3bd6d5627c7b
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145772003"
---
# Cadangan-SertifikatAzKeyVault

## SYNOPSIS
Mencadangkan sertifikat dalam brankas kunci.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/backup-azkeyvaultcertificate) untuk informasi terbaru.

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
Cmdlet **Backup-AzKeyVaultCertificate** mencadangkan sertifikat tertentu dalam brankas kunci dengan mengunduhnya dan menyimpannya dalam file.
Jika sertifikat memiliki beberapa versi, semua versinya akan disertakan dalam cadangan.
Karena konten yang diunduh dienkripsi, konten tersebut tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan sertifikat yang dicadangkan ke brankas kunci apa pun dalam langganan tempat sertifikat dicadangkan, selama vault berada dalam geografi Azure yang sama.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin menyimpan salinan sertifikat offline jika Anda secara tidak sengaja menghapus yang asli dari vault.
 
- Anda membuat sertifikat menggunakan Key Vault dan sekarang ingin mengkloning objek ke wilayah Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua instans aplikasi terdistribusi Anda.
Gunakan cmdlet **Backup-AzKeyVaultCertificate** untuk mengambil sertifikat dalam format terenkripsi lalu gunakan cmdlet **Restore-AzKeyVaultCertificate** dan tentukan brankas kunci di wilayah kedua.

## EXAMPLES

### Contoh 1: Mencadangkan sertifikat dengan nama file yang dibuat secara otomatis
```powershell
Backup-AzKeyVaultCertificate -VaultName 'mykeyvault' -Name 'mycert'
```

```output
C:\Users\username\mykeyvault-mycert-1527029447.01191
```

Perintah ini mengambil sertifikat bernama MyCert dari brankas kunci bernama MyKeyVault dan menyimpan cadangan sertifikat tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan sertifikat ke nama file tertentu
```powershell
Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyCert' -OutputFile 'C:\Backup.blob'
```

```output
C:\Backup.blob
```

Perintah ini mengambil sertifikat bernama MyCert dari brankas kunci bernama MyKeyVault dan menyimpan cadangan sertifikat tersebut ke file bernama Backup.blob.

### Contoh 3: Cadangkan sertifikat yang diambil sebelumnya ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
$cert = Get-AzKeyVaultCertificate -VaultName 'MyKeyVault' -Name 'MyCert'
Backup-AzKeyVaultCertificate -Certificate $cert -OutputFile 'C:\Backup.blob' -Force
```

```output
C:\Backup.blob
```

Perintah ini membuat cadangan sertifikat bernama $cert. Nama dalam vault bernama $cert. VaultName ke file bernama Backup.blob, secara diam-diam menimpa file jika sudah ada.

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
Timpa file yang diberikan jika ada

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
Rahasia yang akan dicadangkan, disalurkan dari output panggilan pengambilan.

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

### -Name
Nama rahasia.
Cmdlet membangun FQDN rahasia dari nama vault, lingkungan dan nama rahasia yang saat ini dipilih.

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
Jika tidak ditentukan, nama file default akan dihasilkan.

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
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateIdentityItem

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
