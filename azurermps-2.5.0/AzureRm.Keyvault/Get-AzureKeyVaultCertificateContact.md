---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 200C68A3-A79C-4517-8E5D-8128F6C73A5C
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurekeyvaultcertificatecontact
schema: 2.0.0
ms.openlocfilehash: d6d2070afcb4a5b9b0b13af1fa54dc93621c5a97
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425372"
---
# Get-AzureKeyVaultCertificateContact

## SYNOPSIS
Mendapatkan kontak yang terdaftar untuk pemberitahuan sertifikat untuk vault kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureKeyVaultCertificateContact [-VaultName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureKeyVaultCertificateContact** mendapatkan kontak yang terdaftar untuk pemberitahuan sertifikat untuk penyimpanan kunci di Azure Key Vault.

## EXAMPLES

### Contoh 1: Mendapatkan semua kontak sertifikat
```
PS C:\>$Contacts = Get-AzureKeyVaultCertificateContact -VaultName "Contoso"
```

Perintah ini akan memasukkan semua kontak untuk objek sertifikat di kunci vault Contoso, lalu menyimpannya dalam $Contacts variabel.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Daftar<Microsoft.Azure.Commands.KeyVault.Models.KeyVaultCertificateContact>

## CATATAN

## RELATED LINKS

[Add-AzureKeyVaultCertificateContact](./Add-AzureKeyVaultCertificateContact.md)

[Remove-AzureKeyVaultCertificateContact](./Remove-AzureKeyVaultCertificateContact.md)

