---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkersecretauthinfoobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerSecretAuthInfoObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerSecretAuthInfoObject.md
ms.openlocfilehash: 2f0b29342b875f8d24211b61f220ecc75b742eee
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145539754"
---
# New-AzServiceLinkerSecretAuthInfoObject

## SYNOPSIS
Buat objek dalam memori untuk SecretAuthInfo.

## SYNTAX

```
New-AzServiceLinkerSecretAuthInfoObject [-Name <String>] [-SecretKeyVaultUri <String>]
 [-SecretNameInKeyVault <String>] [-SecretValue <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SecretAuthInfo.

## EXAMPLES

### Contoh 1: Membuat info Autentikasi Rahasia dengan nilai mentah
```powershell
New-AzServiceLinkerSecretAuthInfoObject -Name user -SecretValue password
```

```output
AuthType Name
-------- ----
secret   user
```

Membuat info Autentikasi Rahasia dengan nilai mentah

### Contoh 2: Membuat info Autentikasi Rahasia dengan uri rahasia keyvault
```powershell
New-AzServiceLinkerSecretAuthInfoObject -Name user -SecretKeyVaultUri "https://servicelinker-kv-ref.vault.azure.net/secrets/test-secret/cc5d8095a54f4755b342f4e7884b5c84" 
```

```output
AuthType Name
-------- ----
secret   user
```

Membuat info Autentikasi Rahasia dengan uri rahasia keyvault

### Contoh 3: Buat info Autentikasi Rahasia dengan referensi rahasia keyvault (Ini hanya untuk AKS dan `-SecretStoreVaultId` harus diatur pada saat yang sama saat membuat linker)
```powershell
New-AzServiceLinkerSecretAuthInfoObject -Name user -SecretNameInKeyVault test-secret
```

```output
AuthType Name
-------- ----
secret   user
```

Buat info Autentikasi Rahasia dengan referensi rahasia keyvault Ini hanya untuk AKS dan `-SecretStoreVaultId` harus diatur pada saat yang sama saat membuat linker

## PARAMETERS

### -Name
Nama pengguna atau nama akun untuk autentikasi rahasia.

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

### -SecretKeyVaultUri
Uri rahasia Key Vault.

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

### -SecretNameInKeyVault
Nama rahasia dalam keyvault direfensikan oleh -SecretStoreKeyVaultId.

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

### -SecretValue
Nilai mentah rahasia.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.SecretAuthInfo

## NOTES

ALIAS

## RELATED LINKS

