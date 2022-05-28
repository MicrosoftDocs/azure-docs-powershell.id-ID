---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnUserManagedHttpsParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnUserManagedHttpsParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnUserManagedHttpsParametersObject.md
ms.openlocfilehash: 800eb2a5885f4c8fd9987986e26ab0a5ad477409
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145510027"
---
# New-AzCdnUserManagedHttpsParametersObject

## SYNOPSIS
Buat objek dalam memori untuk UserManagedHttpsParameters.

## SYNTAX

```
New-AzCdnUserManagedHttpsParametersObject -CertificateSource <CertificateSource>
 -CertificateSourceParameterResourceGroupName <String> -CertificateSourceParameterSecretName <String>
 -CertificateSourceParameterSubscriptionId <String> -CertificateSourceParameterVaultName <String>
 -ProtocolType <ProtocolType> [-CertificateSourceParameterSecretVersion <String>]
 [-MinimumTlsVersion <MinimumTlsVersion>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UserManagedHttpsParameters.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -CertificateSource
Menentukan sumber sertifikat SSL.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.CertificateSource
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterResourceGroupName
Grup sumber daya Key Vault pengguna yang berisi sertifikat SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterSecretName
Nama Rahasia Key Vault (mewakili sertifikat lengkap PFX) dalam Key Vault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterSecretVersion
Versi (GUID) rahasia Key Vault di Key Vault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterSubscriptionId
Id langganan Key Vault pengguna yang berisi sertifikat SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterVaultName
Nama Key Vault pengguna yang berisi sertifikat SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTlsVersion
Versi protokol TLS yang akan digunakan untuk Https.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.MinimumTlsVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtocolType
Menentukan protokol ekstensi TLS yang digunakan untuk pengiriman yang aman.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ProtocolType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.UserManagedHttpsParameters

## NOTES

ALIAS

## RELATED LINKS

