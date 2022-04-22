---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
ms.openlocfilehash: dcb4cddbeb15c3109ac435cd42551189999b10d3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143010863"
---
# Set-AzRecoveryServicesVaultProperty

## SYNOPSIS
Memperbarui properti Vault.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultproperty) untuk informasi terbaru.

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
Cmdlet **Set-AzRecoveryServicesVaultProperty** memperbarui properti kubah layanan Pemulihan. Cmdlet ini dapat digunakan untuk mengaktifkan/menonaktifkan penghapusan lunak atau mengatur enkripsi CMK untuk kubah dengan dua rangkaian parameter yang berbeda. 
**Properti SoftDeleteFeatureState** dari kubah hanya dapat dinonaktifkan jika tidak ada kontainer terdaftar dalam kubah. InfrastructurEncryption hanya dapat diatur saat pertama kali pengguna memperbarui kubah CMK.

## EXAMPLES

### Contoh 1: Memperbarui SoftDeleteFeatureState dari kubah
```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $props = Set-AzRecoveryServicesVaultProperty -VaultId $vault.Id -SoftDeleteFeatureState Enable
```

Perintah pertama mendapatkan objek Vault lalu menyimpannya dalam variabel $vault.
Perintah kedua Memperbarui properti SoftDeleteFeatureState dari kubah ke status "Diaktifkan".

### Contoh 2: Memperbarui enkripsi CMK kubah untuk menggunakan SystemAssigned MSIdentity

```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
PS C:\> $key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
PS C:\> Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -InfrastructureEncryption -VaultId $vault.ID -UseSystemAssignedIdentity $true
```

Cmdlet pertama mendapatkan RSVault untuk memperbarui properti enkripsi. Cmdlet kedua mendapatkan kubah tombol azure. Cmdlet ketiga mendapatkan kunci dari kubah kunci.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault untuk diakses melalui identitas SystemAssigned. Gunakan param -InfrastructureEncryption untuk mengaktifkan enkripsi infrastruktur untuk pembaruan pertama kalinya. 

### Contoh 3: Memperbarui enkripsi CMK dari kubah untuk menggunakan userAssigned MSIdentity

```
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
PS C:\> $keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
PS C:\> $key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
PS C:\> Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -VaultId $vault.ID -UseSystemAssignedIdentity $false -UserAssignedIdentity $vault.Identity.UserAssignedIdentities.Keys[0]
```

Cmdlet pertama mendapatkan RSVault untuk memperbarui properti enkripsi. Cmdlet kedua mendapatkan kubah tombol azure. Cmdlet ketiga mendapatkan kunci dari kubah kunci.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault untuk diakses melalui identitas UserAssigned.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
KeyId kunci enkripsi yang akan digunakan untuk CMK.

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
Mengaktifkan enkripsi infrastruktur pada kubah ini. Enkripsi infrastruktur harus diaktifkan ketika mengonfigurasi enkripsi.

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
Id Langganan Key Vault.

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
SoftDeleteFeatureState dari Vault Layanan Pemulihan.

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
ARM Id of UserAssigned Identity yang akan digunakan untuk enkripsi CMK. Berikan parameter ini jika UseSystemAssignedIdentity $false.

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
Bendera Boolean untuk menunjukkan apakah SystemAssigned Identity akan digunakan untuk enkripsi CMK. Vaules yang Diterima: $true, $false

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
ARM ID dari Vault Layanan Pemulihan.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.VaultSoftDeleteFeatureState

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Backup.Models.BackupResourceVaultConfigResource

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesVault](./Get-AzRecoveryServicesVault.md)

[Get-AzRecoveryServicesVaultProperty](./Get-AzRecoveryServicesVaultProperty.md)
