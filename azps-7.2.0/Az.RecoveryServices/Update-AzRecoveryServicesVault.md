---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/update-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
ms.openlocfilehash: 0e139ba3ce8741f52d0461c0fcdc285ff5a1f13d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139917925"
---
# Update-AzRecoveryServicesVault

## SYNOPSIS
Memperbarui MSIdentity ke vault layanan pemulihan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.recoveryservices/update-azrecoveryservicesvault) untuk informasi terkini.

## SYNTAX

### AzureRSVaultAddMSIdentity (Default)
```
Update-AzRecoveryServicesVault [-ResourceGroupName] <String> [-Name] <String> -IdentityType <MSIdentity>
 [-IdentityId <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureRSVaultRemoveMSIdentity
```
Update-AzRecoveryServicesVault [-ResourceGroupName] <String> [-Name] <String> [-IdentityId <String[]>]
 [-RemoveUserAssigned] [-RemoveSystemAssigned] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini digunakan untuk menambahkan atau menghapus MSI dari vault layanan pemulihan. Gunakan -IdentityType param untuk menambahkan Identitas SystemAssigned/UserAssigned ke RSVault. Gunakan sakelar RemoveSystemAssigned/RemoveUserAssigned untuk menghapus MSI dari vault.

## EXAMPLES

### Contoh 1: Tambahkan Identitas SystemAssigned ke vault layanan pemulihan
```powershell
PS C:\> Update-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName" -IdentityType SystemAssigned
```

Cmdlet ini digunakan untuk menambahkan identitas SystemAssigned ke vault layanan pemulihan.

### Contoh 2: Tambahkan identitas UserAssigned ke vault layanan pemulihan
```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -Name "vaultName" -ResourceGroupName "resourceGroupName"
PS C:\> $identity1 = Get-AzUserAssignedIdentity -ResourceGroupName "resourceGroupName" -Name "UserIdentity1"
PS C:\> $identity2 = Get-AzUserAssignedIdentity -ResourceGroupName "resourceGroupName" -Name "UserIdentity2"
PS C:\> $updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -IdentityType UserAssigned -IdentityId $identity1.Id, $identity2.Id
PS C:\>  $updatedVault.Identity | fl

PrincipalId            :
TenantId               : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                   : UserAssigned
UserAssignedIdentities : {[/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/UserIdentity1,
                         Microsoft.Azure.Management.RecoveryServices.Models.UserIdentity],
                         [/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/UserIdentity2,
                         Microsoft.Azure.Management.RecoveryServices.Models.UserIdentity]}
```

Cmdlet pertama mengambil vault layanan pemulihan.
Cmdlet kedua dan ketiga mengambil pengguna yang membuat MSIS.
Cmdlet keempat menambahkan API pengguna ke vault.
Cmdlet kelima memperlihatkan Identitas yang ditambahkan ke penyimpanan.

### Contoh 3: Hapus identitas SystemAssigned dan UserAssigned dari vault
```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -Name "vaultName" -ResourceGroupName "resourceGroupName"
PS C:\> $updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -RemoveSystemAssigned
PS C:\> $AllUserIdentities =  $vault.Identity.UserAssignedIdentities.Keys | foreach {$_} 
PS C:\> $updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -RemoveUserAssigned -IdentityId $AllUserIdentities
PS C:\> $updatedVault.Identity | fl

PrincipalId            :
TenantId               :
Type                   : None
UserAssignedIdentities :
```

Cmdlet pertama mengambil vault layanan pemulihan.
Cmdlet kedua menghapus identitas SystemAssigned dari vault.
Cmdlet ketiga mengambil semua MSIS pengguna sebagai daftar dari vault.
Cmdlet keempat menghapus semua MSIS pengguna dari vault. Jika mau, Anda bisa memberi identitas pengguna yang dipilih agar dihapus sebagai koma yang dipisahkan, seperti di contoh sebelumnya.
Cmdlet kelima memperlihatkan identitas di vault, saat kami menghapus semua identitas, Type ditampilkan sebagai Tidak Ada.

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

### -IdentityId
ID ARM dari Identitas UserAssigned untuk ditambahkan/dihapus. Ini adalah daftar Id Identitas yang dipisahkan tanda koma.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Tipe MSI yang ditetapkan untuk Vault Layanan Pemulihan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.MSIdentity
Parameter Sets: AzureRSVaultAddMSIdentity
Aliases:
Accepted values: SystemAssigned, None, UserAssigned

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama

Menentukan nama vault layanan pemulihan untuk diperbarui.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSystemAssigned
Berikan sakelar ini untuk menghapus SystemAssigned Identity dari vault.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRSVaultRemoveMSIdentity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveUserAssigned
Sediakan sakelar ini untuk menghapus Identitas PenggunaAssigned dari vault. Selain itu, sediakan parameter IdenityId bersama dengan sakelar ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRSVaultRemoveMSIdentity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName

Tentukan nama grup sumber daya Azure tempat penyimpanan layanan pemulihan disajikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Models.Vault

## CATATAN

## RELATED LINKS
