---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 28BC1B99-946C-4A8D-9581-4D5CC0BCEF8B
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/set-AzKeyvaultcertificatepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultCertificatePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultCertificatePolicy.md
ms.openlocfilehash: 160c98b141dbde36786404b58c694772dc86d323
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424460"
---
# Set-AzKeyVaultCertificatePolicy

## SYNOPSIS
Membuat atau memperbarui kebijakan untuk sertifikat di kunci vault.

## SYNTAX

### Diperluas (Default)
```
Set-AzKeyVaultCertificatePolicy [-VaultName] <String> [-Name] <String> [-SecretContentType <String>]
 [-ReuseKeyOnRenewal <Boolean>] [-Disabled] [-SubjectName <String>]
 [-DnsNames <System.Collections.Generic.List`1[System.String]>]
 [-KeyUsage <System.Collections.Generic.List`1[System.String]>]
 [-Ekus <System.Collections.Generic.List`1[System.String]>] [-ValidityInMonths <Int32>] [-IssuerName <String>]
 [-CertificateType <String>] [-RenewAtNumberOfDaysBeforeExpiry <Int32>] [-RenewAtPercentageLifetime <Int32>]
 [-EmailAtNumberOfDaysBeforeExpiry <Int32>] [-EmailAtPercentageLifetime <Int32>] [-KeyType <String>]
 [-KeyNotExportable] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByValue
```
Set-AzKeyVaultCertificatePolicy [-VaultName] <String> [-Name] <String>
 [-EmailAtNumberOfDaysBeforeExpiry <Int32>] [-EmailAtPercentageLifetime <Int32>] [-KeyType <String>]
 [[-CertificatePolicy] <KeyVaultCertificatePolicy>] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzKeyVaultCertificatePolicy** membuat atau memperbarui kebijakan untuk sertifikat di kunci vault.

## EXAMPLES

### Contoh 1: Menetapkan kebijakan sertifikat
```
PS C:\>Set-AzKeyVaultCertificatePolicy -VaultName "ContosoKV01" -Name "TestCert01" -SecretContentType "application/x-pkcs12" -SubjectName "CN=contoso.com" -IssuerName "Self" -ValidityInMonths 6 -ReuseKeyOnRenewal $True
```

Perintah ini menetapkan kebijakan untuk sertifikat TestCert01 dalam kunci vault ContosoVAULT01.

## PARAMETERS

### -CertificatePolicy
Menentukan kebijakan sertifikat.

```yaml
Type: KeyVaultCertificatePolicy
Parameter Sets: ByValue
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateType
Menentukan tipe sertifikat untuk penerbit.

```yaml
Type: String
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dinonaktifkan
Menunjukkan bahwa kebijakan sertifikat dinonaktifkan.

```yaml
Type: SwitchParameter
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsNames
Menentukan nama DNS dalam sertifikat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ekus
Menentukan penggunaan tombol (EKU) yang disempurnakan dalam sertifikat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EmailAtNumberOfDaysBeforeExpiry
Menentukan berapa hari sebelum proses pemberitahuan otomatis dimulai.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EmailAtPercentageLifetime
Menentukan persentase masa berlaku setelah proses otomatis untuk pemberitahuan dimulai.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IssuerName
Menentukan nama penerbit untuk sertifikat ini.

```yaml
Type: String
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyNotExportable
Menunjukkan bahwa kunci tersebut tidak dapat diekspor.

```yaml
Type: SwitchParameter
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyType
Menentukan tipe kunci dari kunci yang mengembalikan sertifikat.
Nilai yang dapat diterima untuk parameter ini adalah:

- RSA
- RSA-HSM

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: RSA, RSA-HSM

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyUsage
Menentukan penggunaan kunci dalam sertifikat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama sertifikat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CertificateName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -RenewAtNumberOfDaysBeforeExpiry
Menentukan jumlah hari sebelum kedaluwarsa setelah proses otomatis untuk perpanjangan sertifikat dimulai.

```yaml
Type: Int32
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RenewAtPercentageLifetime
Menentukan persentase masa berlaku setelah proses otomatis untuk perpanjangan sertifikat dimulai.

```yaml
Type: Int32
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReuseKeyOnRenewal
Menunjukkan bahwa sertifikat menggunakan kembali kunci tersebut selama perpanjangan.

```yaml
Type: Boolean
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretContentType
Menentukan tipe konten rahasia vault kunci yang baru.
Nilai yang dapat diterima untuk parameter ini adalah:

- application/x-pkcs12
- application/x-pem-file

```yaml
Type: String
Parameter Sets: Expanded
Aliases: 
Accepted values: application/x-pkcs12, application/x-pem-file

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubjectName
Menentukan nama subjek sertifikat.

```yaml
Type: String
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValidityInMonths
Menentukan jumlah bulan sertifikat valid.

```yaml
Type: Int32
Parameter Sets: Expanded
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.KeyVaultCertificatePolicy

## CATATAN

## RELATED LINKS

[Get-AzKeyVaultCertificatePolicy](./Get-AzKeyVaultCertificatePolicy.md)

[New-AzKeyVaultCertificatePolicy](./New-AzKeyVaultCertificatePolicy.md)

