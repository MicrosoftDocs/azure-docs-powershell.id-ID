---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 70DB088D-4AF5-406B-8D66-118A0F766041
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/restore-azurekeyvaultsecret
schema: 2.0.0
ms.openlocfilehash: b8ce1dc13204cfeeb63f5b7eb45f57e2117da511
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141889236"
---
# Restore-AzureKeyVaultSecret

## SYNOPSIS
Membuat rahasia dalam kubah kunci dari rahasia yang dicadangkan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Restore-AzureKeyVaultSecret [-VaultName] <String> [-InputFile] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzureKeyVaultSecret** membuat rahasia dalam kubah kunci yang ditentukan.
Rahasia ini adalah replika rahasia yang dicadangkan dalam file input dan memiliki nama yang sama dengan rahasia aslinya.
Jika kubah kunci sudah memiliki rahasia dengan nama yang sama, cmdlet ini gagal daripada menimpa rahasia asli.
Jika cadangan berisi beberapa versi rahasia, semua versi akan dipulihkan.

Kubah kunci yang Anda pulihkan rahasianya bisa berbeda dari kubah kunci tempat Anda mencadangkan rahasia.
Namun, kubah kunci harus menggunakan langganan yang sama dan berada di kawasan Azure dalam geografi yang sama (misalnya, Amerika Utara).
Lihat Pusat Kepercayaan Microsoft Azure (https://azure.microsoft.com/support/trust-center/) untuk pemetaan kawasan Azure ke geografis.

## EXAMPLES

### Contoh 1: Memulihkan rahasia cadangan
```
PS C:\>Restore-AzureKeyVaultSecret -VaultName 'MyKeyVault' -InputFile "C:\Backup.blob"
```

Perintah ini memulihkan rahasia, termasuk semua versinya, dari file cadangan bernama Backup.blob ke dalam kubah kunci bernama MyKeyVault.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputFile
Menentukan berkas input yang berisi cadangan rahasia untuk dipulihkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci untuk memulihkan rahasia.

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

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.Secret

## CATATAN

## RELATED LINKS

[Set-AzureKeyVaultSecret](./Set-AzureKeyVaultSecret.md)

[Backup-AzureKeyVaultSecret](./Backup-AzureKeyVaultSecret.md)

[Get-AzureKeyVaultSecret](./Get-AzureKeyVaultSecret.md)

[Hapus-AzureKeyVaultSecret](./Remove-AzureKeyVaultSecret.md)

