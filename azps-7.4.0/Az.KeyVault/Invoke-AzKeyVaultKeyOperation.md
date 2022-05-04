---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/invoke-azkeyvaultkeyoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Invoke-AzKeyVaultKeyOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Invoke-AzKeyVaultKeyOperation.md
ms.openlocfilehash: f9f363e2df2d492166b83582098be2b3203abee7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144574490"
---
# Invoke-AzKeyVaultKeyOperation

## SYNOPSIS
Melakukan operasi seperti "Encrypt", "Decrypt", "Wrap" atau "Unwrap" menggunakan kunci tertentu yang disimpan dalam brankas kunci atau hsm terkelola.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/invoke-azkeyvaultkeyoperation) untuk informasi terbaru.

## SYNTAX

### ByVaultName (Default)
```
Invoke-AzKeyVaultKeyOperation -Operation <String> -Algorithm <String> -Value <SecureString>
 [-VaultName] <String> [-Name] <String> [-Version <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHsmName
```
Invoke-AzKeyVaultKeyOperation -Operation <String> -Algorithm <String> -Value <SecureString> [-HsmName] <String>
 [-Name] <String> [-Version <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByKeyInputObject
```
Invoke-AzKeyVaultKeyOperation -Operation <String> -Algorithm <String> -Value <SecureString>
 [-InputObject] <PSKeyVaultKeyIdentityItem> [-Version <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Invoke-AzKeyVaultKeyOperation cmdlet mendukung
1. Mengenkripsi urutan byte arbitrer menggunakan kunci enkripsi.
2. Mendekripsi satu blok data terenkripsi.
3. Membungkus kunci konten menggunakan kunci tertentu.
4. Membongkar kunci konten menggunakan kunci yang ditentukan yang awalnya digunakan untuk membungkus kunci tersebut.

## EXAMPLES

### Mengenkripsi menggunakan kunci enkripsi
```powershell
$result = Invoke-AzKeyVaultKeyOperation -Operation Encrypt -Algorithm RSA1_5 -VaultName test-kv -Name test-key -Value (ConvertTo-SecureString -String "test" -AsPlainText -Force) ult
$result | fl
```

```output
KeyId     : https://test-kv.vault.azure.net/keys/test-key/375cdf20252043b79c8ca0c57b6c7679
Result    : e01HmkipqwCZyQd2QZ5XOTSA3rlZ719qqHHadzepFGtvTSoDwr+sBPmODVqScvq5/MBS9YyT+u6AM5hsFKD+h2FJOB6Pj/nwO5MZ/tZ8F974qAxXXT2qvdNm6pHKhREgPlCHmz+L6xK/8KOF+LS1E9wmuAt8ZPsJ7BtcT2bcvR4VmeOaUhvxcuNMV675nsFpwHBv6GWSfQA+RkDCIpmv6msdpK8NG6+la+fSPA6EKMJkmqF3SZ6RhSOjg00S7jXEWncIzdp6RRKYZFKY+QhqLgFVABL876IW4nDGYgdVSG7KnH0K56QqtK5L4MhvU4XYE69I4WiWbZ7rcVLE3cO/9A==
Algorithm : RSA1_5
```

Mengenkripsi string "uji" menggunakan test-key yang disimpan dalam test-kv. Hasil yang dikembalikan adalah format string Base64.

### Mendekripsi data terenkripsi
```powershell
$result
$result = Invoke-AzKeyVaultKeyOperation -Operation Decrypt -Algorithm RSA1_5 -VaultName test-kv -Name test-key -Value (ConvertTo-SecureString -String $result.Result -AsPlainText -Force) ult
$result | fl
```

```output
KeyId     : https://test-kv.vault.azure.net/keys/test-key/375cdf20252043b79c8ca0c57b6c7679
Result    : test
Algorithm : RSA1_5
```

Mendekripsi data terenkripsi yang dienkripsi menggunakan test-key yang disimpan dalam test-kv. 

### Mengenkripsi menggunakan kunci enkripsi
```powershell
$result = Invoke-AzKeyVaultKeyOperation -Operation Encrypt -Algorithm RSA1_5 -VaultName test-kv -Name test-key -Value (ConvertTo-SecureString -String "test" -AsPlainText -Force) 

$result | fl
```

```output
KeyId     : https://test-kv.vault.azure.net/keys/test-key/375cdf20252043b79c8ca0c57b6c7679
Result    : e01HmkipqwCZyQd2QZ5XOTSA3rlZ719qqHHadzepFGtvTSoDwr+sBPmODVqScvq5/MBS9YyT+u6AM5hsFKD+h2FJOB6Pj/nwO5MZ/tZ8F974qAxXXT2qvdNm6pHKhREgPlCHmz+L6xK/8KOF+LS1E9wmuAt8ZPsJ7BtcT2bcvR4VmeOaUhvxcuNMV675nsFpwHBv6GWSfQA+RkDCIpmv6msdpK8NG6+la+fSPA6EKMJkmqF3SZ6RhSOjg00S7jXEWncIzdp6RRKYZFKY+QhqLgFVABL876IW4nDGYgdVSG7KnH0K56QqtK5L4MhvU4XYE69I4WiWbZ7rcVLE3cO/9A==
Algorithm : RSA1_5
```

Mengenkripsi string "uji" menggunakan test-key yang disimpan dalam test-kv. Hasil yang dikembalikan adalah format string Base64.

### Membungkus kunci konten menggunakan kunci tertentu
```powershell
$result = Invoke-AzKeyVaultKeyOperation -Operation Wrap -Algorithm RSA1_5 -VaultName test-kv -Name test-key -Value (ConvertTo-SecureString -String "ovQIlbB0DgWhZA7sgkPxbg9H-Ly-VlNGPSgGrrZvlIo" -AsPlainText -Force) 

$result | fl
```

```output
KeyId     : https://test-kv.vault.azure.net/keys/test-key/375cdf20252043b79c8ca0c57b6c7679
Result    : e01HmkipqwCZyQd2QZ5XOTSA3rlZ719qqHHadzepFGtvTSoDwr+sBPmODVqScvq5/MBS9YyT+u6AM5hsFKD+h2FJOB6Pj/nwO5MZ/tZ8F974qAxXXT2qvdNm6pHKhREgPlCHmz+L6xK/8KOF+LS1E9wmuAt8ZPsJ7BtcT2bcvR4VmeOaUhvxcuNMV675nsFpwHBv6GWSfQA+RkDCIpmv6msdpK8NG6+la+fSPA6EKMJkmqF3SZ6RhSOjg00S7jXEWncIzdp6RRKYZFKY+QhqLgFVABL876IW4nDGYgdVSG7KnH0K56QqtK5L4MhvU4XYE69I4WiWbZ7rcVLE3cO/9A==
Algorithm : RSA1_5
```

Membungkus kunci simetris menggunakan kunci bernama test-key yang disimpan dalam test-kv. Hasil yang dikembalikan adalah string Base64.

### Membongkar kunci simetris menggunakan kunci tertentu
```powershell
Invoke-AzKeyVaultKeyOperation -Operation Unwrap -Algorithm RSA1_5 -VaultName test-kv -Name test-key -Value (ConvertTo-SecureString -String $result.Result -AsPlainText -Force) 
```

```output
KeyId     : https://test-kv.vault.azure.net/keys/test-key/375cdf20252043b79c8ca0c57b6c7679
Result    : ovQIlbB0DgWhZA7sgkPxbg9H-Ly-VlNGPSgGrrZvlIo
Algorithm : RSA1_5
```

 Membongkar kunci konten menggunakan kunci uji kunci tertentu yang disimpan dalam test-kv. 

## PARAMETERS

### -Algoritma
Pengidentifikasi algoritma

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: EncryptionAlgorithm, WrapAlgorithm

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -HsmName
Nama HSM.

```yaml
Type: System.String
Parameter Sets: ByHsmName
Aliases:

Required: True
Position: 0
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

### -Name
Nama kunci.

```yaml
Type: System.String
Parameter Sets: ByVaultName, ByHsmName
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operasi
Pengidentifikasi algoritma

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

### -Nilai
Nilai yang akan dioperasikan

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama vault.

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

### -Versi
Versi kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: KeyVersion

Required: False
Position: Named
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyOperationResult

## NOTES

## RELATED LINKS
