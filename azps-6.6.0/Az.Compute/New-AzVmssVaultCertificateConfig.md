---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 5CC89899-00B6-424A-8896-FD32DE9DDA28
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmssvaultcertificateconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssVaultCertificateConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssVaultCertificateConfig.md
ms.openlocfilehash: fa505198346b896edb7a8c3e203d2cb7d55a36e1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139942477"
---
# New-AzVmssVaultCertificateConfig

## SYNOPSIS
Membuat konfigurasi sertifikat Key Vault.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/new-azvmssvaultcertificateconfig) untuk informasi terkini.

## SYNTAX

```
New-AzVmssVaultCertificateConfig [[-CertificateUrl] <String>] [[-CertificateStore] <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVmssVaultCertificateConfig** menentukan rahasia yang perlu diletakkan pada mesin virtual Virtual Machine Scale Set (VMSS).
Output cmdlet ini dimaksudkan untuk digunakan dengan cmdlet Add-AzVmssSecret cmdlet.

## EXAMPLES

### Contoh 1: Membuat konfigurasi sertifikat Key Vault
```
PS C:\> New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "MyCerts"
```

Perintah ini akan membuat konfigurasi sertifikat Key Vault yang menggunakan penyimpanan sertifikat bernama MyCerts yang terletak di URL sertifikat yang ditentukan.

## PARAMETERS

### -CertificateStore
Menentukan penyimpanan sertifikat pada mesin virtual dalam skala yang ditetapkan tempat sertifikat ditambahkan.
Ini hanya berlaku untuk Windows Skala Mesin Virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateUrl
Menentukan URI sertifikat yang disimpan di Key Vault.
Pengodean ini adalah pengodean base64 dari Objek JSON berikut yang dikodekan dalam UTF-8: { "data":"\<Base64-encoded-certificate\>", "dataType http=pfx", "password http"\<pfx-file-password\>.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.VaultCertificate

## CATATAN

## RELATED LINKS

[Add-AzVmssSecret](./Add-AzVmssSecret.md)
