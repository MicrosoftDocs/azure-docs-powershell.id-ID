---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/update-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
ms.openlocfilehash: 8fd129b2a2a9fcb0b7bbbd69d8b443d4148ddb25
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141797360"
---
# Update-AzRecoveryServicesVault

## SYNOPSIS
Memperbarui MSIdentity ke kubah layanan pemulihan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/update-azrecoveryservicesvault) untuk informasi terbaru.

## SYNTAX

### AzureRSVaultAddMSIdentity
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
Cmdlet ini digunakan untuk menambahkan atau menghapus MSI dari kubah layanan pemulihan. Gunakan param -IdentityType untuk menambahkan identitas SystemAssigned/UserAssigned ke RSVault. Gunakan sakelar RemoveSystemAssigned/RemoveUserAssigned untuk menghapus MSI dari kubah.

## EXAMPLES

### Contoh 1: Menambahkan identitas SystemAssigned ke kubah layanan pemulihan
```powershell
PS C:\> Update-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName" -IdentityType SystemAssigned
```

Cmdlet ini digunakan untuk menambahkan identitas SystemAssigned ke kubah layanan pemulihan.

### Contoh 2: Tambahkan identitas UserAssigned ke kubah layanan pemulihan
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
Cmdlet pertama mengambil kubah layanan pemulihan.
Cmdlet kedua dan ketiga mengambil MSI yang dibuat pengguna.
Cmdlet keempat menambahkan MSI pengguna ke kubah.
Cmdlet kelima memperlihatkan identitas yang ditambahkan ke kubah.

### Contoh 3: Remove SystemAssigned and UserAssigned identities from the vault
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

Cmdlet pertama mengambil kubah layanan pemulihan.
Cmdlet kedua menghapus identitas SystemAssigned dari kubah.
Cmdlet ketiga mengambil semua MSI pengguna sebagai daftar dari kubah.
Cmdlet keempat menghapus semua MSI pengguna dari kubah. Jika anda ingin, Anda bisa menyediakan identitas pengguna yang dipilih untuk dihapus sebagai koma dipisahkan, seperti dalam contoh sebelumnya.
Cmdlet kelima memperlihatkan identitas dalam kubah, saat kami menghapus semua identitas, Tipe ditampilkan sebagai Tidak Ada.

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
ID ARM dari UserAssigned Identity yang akan ditambahkan/dihapus. Ini adalah daftar Id Identitas yang dipisahkan koma.

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
Tipe MSI yang ditetapkan ke Vault Layanan Pemulihan.

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

Menentukan nama kubah layanan pemulihan untuk diperbarui.

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
Berikan sakelar ini untuk menghapus SystemAssigned Identity dari kubah.

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
Berikan sakelar ini untuk menghapus UserAssigned Identity dari kubah. Juga, berikan parameter IdenityId bersama dengan sakelar ini.

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

Menentukan nama grup sumber daya Azure tempat kubah layanan pemulihan ada.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Models.Vault

## CATATAN

## RELATED LINKS
