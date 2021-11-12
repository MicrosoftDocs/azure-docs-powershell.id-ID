---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 0E1C05B0-8CF6-4C03-AA05-B13A4059A280
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/new-azurekeyvaultcertificateorganizationdetails
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/New-AzureKeyVaultCertificateOrganizationDetails.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/New-AzureKeyVaultCertificateOrganizationDetails.md
ms.openlocfilehash: 5a5c66d86e2de6c7dd1052d7d054cd025d6500426f0fd89be6329f1f5bc6708c
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413750"
---
# New-AzureKeyVaultCertificateOrganizationDetails

## SYNOPSIS
Membuat objek detail organisasi sertifikat dalam memori.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureKeyVaultCertificateOrganizationDetails [-Id <String>]
 [-AdministratorDetails <System.Collections.Generic.List`1[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateAdministratorDetails]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureKeyVaultCertificateOrganizationDetails** membuat objek detail organisasi sertifikat dalam memori.

## EXAMPLES

### Contoh 1: Membuat objek detail organisasi
```powershell
PS C:\> $AdminDetails = New-AzureKeyVaultCertificateAdministratorDetails -FirstName "Patti" -LastName "Fuller" -EmailAddress "Patti.Fuller@contoso.com" -PhoneNumber "1234567890"
PS C:\> New-AzureKeyVaultCertificateOrganizationDetails -AdministratorDetails $AdminDetails

Id AdministratorDetails
-- --------------------
   {Patti}
```

Perintah pertama membuat objek detail administrator sertifikat, lalu menyimpannya di $AdminDetails variabel.
Perintah kedua membuat objek detail organisasi sertifikat, lalu menyimpannya di $OrgDetails variabel.

## PARAMETERS

### -AdministratorDetails
Menentukan administrator organisasi sertifikat.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateAdministratorDetails]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan pengidentifikasi untuk organisasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateAdministratorDetails, Microsoft.Azure.Commands.KeyVault, Version=5.1.0.0, Culture=neutral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultCertificateOrganizationDetails

## CATATAN

## RELATED LINKS

[New-AzureKeyVaultCertificateAdministratorDetails](./New-AzureKeyVaultCertificateAdministratorDetails.md)

