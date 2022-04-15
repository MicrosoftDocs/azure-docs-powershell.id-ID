---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultKeyRotationPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultKeyRotationPolicy.md
ms.openlocfilehash: 3db129155b709351283e6a60a07619cc30b71dba
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142293082"
---
# Get-AzKeyVaultKeyRotationPolicy

## SYNOPSIS
Mendapatkan kebijakan rotasi kunci untuk kunci yang ditentukan dalam Key Vault.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/get-azkeyvaultkeyrotationpolicy) untuk informasi terbaru.

## SYNTAX

### ByVaultName (Default)
```
Get-AzKeyVaultKeyRotationPolicy [-VaultName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByKeyInputObject
```
Get-AzKeyVaultKeyRotationPolicy [-InputObject] <PSKeyVaultKeyIdentityItem>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini memerlukan kunci/mendapatkan izin. Mengembalikan kebijakan rotasi kunci untuk kunci yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzKeyVaultKeyRotationPolicy -VaultName test-kv -Name test-key
```

```output
Id              :
VaultName       : test-kv
KeyName         : test-key
LifetimeActions : {[Action: Notify, TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00]}
ExpiresIn       :
CreatedOn       :
UpdatedOn       :
```

Cmdlet ini mendapatkan kebijakan rotasi kunci untuk uji-kv.

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

### -InputObject
Objek kunci

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem
Parameter Sets: ByKeyInputObject
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kunci.

```yaml
Type: System.String
Parameter Sets: ByVaultName
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama kubah.

```yaml
Type: System.String
Parameter Sets: ByVaultName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyRotationPolicy

## CATATAN

## RELATED LINKS

[Set-AzKeyVaultKeyRotationPolicy.md](./Set-AzKeyVaultKeyRotationPolicy.md)

[Invoke-AzKeyVaultKeyRotation.md](./Invoke-AzKeyVaultKeyRotation.md)
