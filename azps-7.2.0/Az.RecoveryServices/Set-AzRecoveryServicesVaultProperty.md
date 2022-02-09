---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
ms.openlocfilehash: 2692302dae195a89c1b49350513376ba693c0d22
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138291915"
---
# Set-AzRecoveryServicesVaultProperty

## SYNOPSIS
Memperbarui properti Vault.

## SYNTAX

### AzureRSVaultSoftDelteParameterSet (Default)
```
Set-AzRecoveryServicesVaultProperty -SoftDeleteFeatureState <String> [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureRSVaultCMKParameterSet
```
Set-AzRecoveryServicesVaultProperty [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 -EncryptionKeyId <String> [-KeyVaultSubscriptionId <String>] [-InfrastructureEncryption]
 [-UseSystemAssignedIdentity <Boolean>] [-UserAssignedIdentity <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRecoveryServicesVaultProperty** memperbarui properti vault layanan Pemulihan. Cmdlet ini dapat digunakan untuk mengaktifkan/menonaktifkan penghapusan sementara atau mengatur enkripsi CMK untuk vault dengan dua kumpulan parameter berbeda. 
**Properti SoftDeleteFeatureState** dari vault dapat dinonaktifkan hanya jika tidak ada wadah terdaftar di vault. InfrastructurEncryption hanya dapat diatur saat pertama kali pengguna memperbarui vault CMK.

## EXAMPLES

### Contoh 1: Update SoftDeleteFeatureState of a vault
```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $props = Set-AzRecoveryServicesVaultProperty -VaultId $vault.Id -SoftDeleteFeatureState Enable
```

Perintah pertama akan mendapatkan objek Vault, lalu menyimpannya dalam $vault variabel.
Perintah kedua Memperbarui properti SoftDeleteFeatureState dari vault ke status "Diaktifkan".

### Contoh 2: Perbarui enkripsi CMK dari vault untuk menggunakan SystemAssigned MSIdentity

```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
PS C:\> $key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
PS C:\> Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -InfrastructureEncryption -VaultId $vault.ID -UseSystemAssignedIdentity $true
```

Cmdlet pertama mendapatkan RSVault untuk memperbarui properti enkripsi. Cmdlet kedua mendapatkan azure key vault. Cmdlet ketiga mendapatkan kunci dari key vault.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault agar diakses melalui identitas SystemAssigned. Gunakan -InfrastructureEncryption param untuk mengaktifkan enkripsi infrastruktur untuk pembaruan pertama kalinya. 

### Contoh 3: Perbarui enkripsi CMK dari vault untuk menggunakan userAssigned MSIdentity

```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
PS C:\> $key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
PS C:\> Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -VaultId $vault.ID -UseSystemAssignedIdentity $false -UserAssignedIdentity $vault.Identity.UserAssignedIdentities.Keys[0]
```

Cmdlet pertama mendapatkan RSVault untuk memperbarui properti enkripsi. Cmdlet kedua mendapatkan azure key vault. Cmdlet ketiga mendapatkan kunci dari key vault.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault agar diakses melalui identitas UserAssigned.

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

### -EncryptionKeyId
KeyId dari kunci enkripsi yang akan digunakan untuk CMK.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InfrastructureEncryption
Mengaktifkan enkripsi infrastruktur di vault ini. Enkripsi infrastruktur harus diaktifkan saat mengonfigurasi enkripsi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultSubscriptionId
Id Langganan Vault Utama.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftDeleteFeatureState
SoftDeleteFeatureState Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultSoftDelteParameterSet
Aliases:
Accepted values: Enable, Disable

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentity
ID ARM dari Identitas YangSigned Pengguna untuk digunakan untuk enkripsi CMK. Sediakan parameter ini jika UseSystemAssignedIdentity $false.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSystemAssignedIdentity
Bendera Boolean untuk menunjukkan apakah SystemAssigned Identity akan digunakan untuk enkripsi CMK. Accepted Camples: $true, $false

```yaml
Type: System.Boolean
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultId
ID ARM dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.VaultSoftDeleteFeatureState

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Backup.Models.BackupResourceVaultConfigResource

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesVault](./Get-AzRecoveryServicesVault.md)

[Get-AzRecoveryServicesVaultProperty](./Get-AzRecoveryServicesVaultProperty.md)
