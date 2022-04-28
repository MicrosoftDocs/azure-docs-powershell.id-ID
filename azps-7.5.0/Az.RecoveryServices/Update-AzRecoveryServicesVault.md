---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/update-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Update-AzRecoveryServicesVault.md
ms.openlocfilehash: bd696ad3f2f437877dbccaa0f9459471e52903d4
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144220223"
---
# Update-AzRecoveryServicesVault

## SYNOPSIS
Memperbarui MSIdentity ke vault layanan pemulihan.

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
Cmdlet ini digunakan untuk menambahkan atau menghapus MSI dari vault layanan pemulihan. Gunakan param -IdentityType untuk menambahkan identitas SystemAssigned/UserAssigned ke RSVault. Gunakan switch RemoveSystemAssigned/RemoveUserAssigned untuk menghapus MSI dari vault.

## EXAMPLES

### Contoh 1: Menambahkan identitas SystemAssigned ke vault layanan pemulihan
```powershell
Update-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName" -IdentityType SystemAssigned
```

Cmdlet ini digunakan untuk menambahkan identitas SystemAssigned ke vault layanan pemulihan.

### Contoh 2: Menambahkan identitas UserAssigned ke vault layanan pemulihan
```powershell
$vault = Get-AzRecoveryServicesVault -Name "vaultName" -ResourceGroupName "resourceGroupName"
$identity1 = Get-AzUserAssignedIdentity -ResourceGroupName "resourceGroupName" -Name "UserIdentity1"
$identity2 = Get-AzUserAssignedIdentity -ResourceGroupName "resourceGroupName" -Name "UserIdentity2"
$updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -IdentityType UserAssigned -IdentityId $identity1.Id, $identity2.Id
$updatedVault.Identity | fl
```

```output
PrincipalId            :
TenantId               : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                   : UserAssigned
UserAssignedIdentities : {[/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/UserIdentity1,
                         Microsoft.Azure.Management.RecoveryServices.Models.UserIdentity],
                         [/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/UserIdentity2,
                         Microsoft.Azure.Management.RecoveryServices.Models.UserIdentity]}
```

Cmdlet pertama mengambil vault layanan pemulihan.
Cmdlet kedua dan ketiga mengambil MSI yang dibuat pengguna.
Cmdlet keempat menambahkan MSI pengguna ke vault.
Cmdlet kelima menunjukkan Identitas yang ditambahkan ke vault.

### Contoh 3: Menghapus identitas SystemAssigned dan UserAssigned dari vault
```powershell
$vault = Get-AzRecoveryServicesVault -Name "vaultName" -ResourceGroupName "resourceGroupName"
$updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -RemoveSystemAssigned
$AllUserIdentities =  $vault.Identity.UserAssignedIdentities.Keys | foreach {$_} 
$updatedVault = Update-AzRecoveryServicesVault -ResourceGroupName $vault.ResourceGroupName -Name $vault.Name -RemoveUserAssigned -IdentityId $AllUserIdentities
$updatedVault.Identity | fl
```

```output
PrincipalId            :
TenantId               :
Type                   : None
UserAssignedIdentities :
```

Cmdlet pertama mengambil vault layanan pemulihan.
Cmdlet kedua menghapus identitas SystemAssigned dari vault.
Cmdlet ketiga mengambil semua MSI pengguna sebagai daftar dari vault.
Cmdlet keempat menghapus semua MSI pengguna dari vault. Jika mau, Anda dapat memberikan identitas pengguna yang dipilih untuk dihapus sebagai dipisahkan koma, seperti dalam contoh sebelumnya.
Cmdlet kelima menunjukkan identitas di brankas, saat kami menghapus semua identitas, Jenis ditampilkan sebagai Tidak Ada.

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
Jenis MSI yang ditetapkan ke Vault Layanan Pemulihan.

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

### -Name

Menentukan nama vault layanan pemulihan yang akan diperbarui.

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
Berikan sakelar ini untuk menghapus UserAssigned Identity dari vault. Selain itu, berikan parameter IdenityId bersama dengan sakelar ini.

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

Menentukan nama grup sumber daya Azure tempat vault layanan pemulihan berada.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Models.Vault

## NOTES

## RELATED LINKS
