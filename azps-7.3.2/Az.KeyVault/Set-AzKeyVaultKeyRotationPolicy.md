---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultKeyRotationPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultKeyRotationPolicy.md
ms.openlocfilehash: 6298b29959ac59ff482c29bbd3d5933dbc4793d7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140556322"
---
# Set-AzKeyVaultKeyRotationPolicy

## SYNOPSIS
Mengatur kebijakan rotasi tombol untuk tombol tertentu di Key Vault.

## SYNTAX

### ByVaultName (Default)
```
Set-AzKeyVaultKeyRotationPolicy [-ExpiresIn <TimeSpan>]
 [-KeyRotationLifetimeAction <PSKeyRotationLifetimeAction[]>] [-VaultName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

###  ByKeyRotationPolicyInputObject
```
Set-AzKeyVaultKeyRotationPolicy [-KeyRotationPolicy] <PSKeyRotationPolicy>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByKeyInputObject
```
Set-AzKeyVaultKeyRotationPolicy [-ExpiresIn <TimeSpan>]
 [-KeyRotationLifetimeAction <PSKeyRotationLifetimeAction[]>] [-InputObject] <PSKeyVaultKeyIdentityItem>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini memerlukan izin pembaruan utama. Opsi ini akan mengembalikan kebijakan rotasi tombol untuk tombol yang ditentukan.

## EXAMPLES

### Contoh 1: Mengatur waktu kedaluwarsa kebijakan rotasi tombol
```powershell
$t = New-TimeSpan -Days 50
Set-AzKeyVaultKeyRotationPolicy -VaultName test-kv -Name test-key -ExpiresIn $t
```

```output
Id              : https://test-kv.vault.azure.net/keys/test-key/rotationpolicy
VaultName       : test-kv
KeyName         : test-key
LifetimeActions : {[Action: Notify, TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00]}
ExpiresIn       : 50.00:00:00
CreatedOn       : 12/10/2021 3:21:51 AM +00:00
UpdatedOn       : 12/10/2021 3:22:14 AM +00:00
```

Cmdlet ini mengatur kebijakan rotasi utama kedaluwarsa waktu uji kunci sebagai 50 hari.

### Contoh 2: Mengatur kebijakan rotasi tombol dengan InputObject
```powershell
$key = Get-AzKeyVaultKey -VaultName test-kv -Name test-key
$action = [Microsoft.Azure.Commands.KeyVault.Models.PSKeyRotationLifetimeAction]::new()
$action.Action = "Rotate"
$action.TimeBeforeExpiry = New-TimeSpan -Days 30
Set-AzKeyVaultKeyRotationPolicy -InputObject $key -KeyRotationLifetimeAction $action
```

```output
Id              : https://test-kv.vault.azure.net/keys/test-key/rotationpolicy
VaultName       : test-kv
KeyName         : test-key
LifetimeActions : {[Action: Rotate, TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00], [Action: Notify,
                  TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00]}
ExpiresIn       : 50.00:00:00
CreatedOn       : 12/10/2021 3:21:51 AM +00:00
UpdatedOn       : 12/14/2021 5:26:28 AM +00:00
```

Cmdlet ini mengatur kebijakan rotasi utama kedaluwarsa waktu uji kunci sebagai 50 hari.

### Contoh 3: Mengatur kebijakan rotasi tombol dengan objek PSKeyRotationPolicy
```powershell
$key = Get-AzKeyVaultKey -VaultName test-kv -Name test-key
$policy = Get-AzKeyVaultKeyRotationPolicy $key
$policy.ExpiresIn = New-TimeSpan -Days 60
Set-AzKeyVaultKeyRotationPolicy -KeyRotationPolicy $policy
```

```output
LifetimeActions : {[Action: Rotate, TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00], [Action: Notify,
                  TimeAfterCreate: , TimeBeforeExpiry: 30.00:00:00]}
ExpiresIn       : 60.00:00:00
CreatedOn       : 12/10/2021 3:21:51 AM +00:00
UpdatedOn       : 12/14/2021 5:34:00 AM +00:00
```

Cmdlet ini mengatur kebijakan rotasi utama kedaluwarsa waktu uji kunci sebagai 50 hari.

## PARAMETERS

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiresIn
Rentang waktu ketika kebijakan rotasi tombol akan kedaluwarsa.
Setidaknya harus 28 hari.

```yaml
Type: TimeSpan
Parameter Sets: ByVaultName, ByKeyInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek utama

```yaml
Type: PSKeyVaultKeyIdentityItem
Parameter Sets: ByKeyInputObject
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyRotationLifetimeAction
Objek PSKeyRotationLifetimeAction.

```yaml
Type: PSKeyRotationLifetimeAction[]
Parameter Sets: ByVaultName, ByKeyInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyRotationPolicy
Objek PSKeyRotationPolicy.

```yaml
Type: PSKeyRotationPolicy
Parameter Sets:  ByKeyRotationPolicyInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kunci.

```yaml
Type: String
Parameter Sets: ByVaultName
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama Vault.

```yaml
Type: String
Parameter Sets: ByVaultName
Aliases:

Required: True
Position: 0
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyRotationPolicy

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyRotationPolicy

## CATATAN

## RELATED LINKS

[Get-AzKeyVaultKeyRotationPolicy.md](./Get-AzKeyVaultKeyRotationPolicy.md)

[Invoke-AzKeyVaultKeyRotation.md](./Invoke-AzKeyVaultKeyRotation.md)