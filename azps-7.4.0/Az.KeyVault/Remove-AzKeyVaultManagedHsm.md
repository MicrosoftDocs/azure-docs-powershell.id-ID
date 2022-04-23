---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/remove-azkeyvaultmanagedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedHsm.md
ms.openlocfilehash: 139677d1b19234423cd31ef5439a2becbea29dfb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143226755"
---
# Remove-AzKeyVaultManagedHsm

## SYNOPSIS
Menghapus/Membersihkan HSM yang dikelola.

## SYNTAX

### RemoveManagedHsmByName (Default)
```
Remove-AzKeyVaultManagedHsm [-Name] <String> [[-ResourceGroupName] <String>] [-Force] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### RemoveDeletedManagedHsmByName
```
Remove-AzKeyVaultManagedHsm [-Name] <String> [-Location] <String> [-InRemovedState] [-Force] [-AsJob]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### RemoveManagedHsmByInputObject
```
Remove-AzKeyVaultManagedHsm [-InputObject] <PSManagedHsm> [-Force] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### RemoveDeletedManagedHsmByInputObject
```
Remove-AzKeyVaultManagedHsm [-InputObject] <PSManagedHsm> [-InRemovedState] [-Force] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### RemoveManagedHsmByResourceId
```
Remove-AzKeyVaultManagedHsm [-ResourceId] <String> [-Force] [-AsJob] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### RemoveDeletedManagedHsmByResourceId
```
Remove-AzKeyVaultManagedHsm [-ResourceId] <String> [-Location] <String> [-InRemovedState] [-Force] [-AsJob]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzKeyVaultManagedHsm** menghapus HSM terkelola yang ditentukan.
Tindakan ini juga menghapus semua kunci yang terdapat dalam contoh tersebut.
Perhatikan bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Menghapus HSM terkelola
```powershell
Remove-AzKeyVaultManagedHsm -HsmName 'myhsm' -Force
```

```output
True
```

Perintah ini menghapus HSM terkelola bernama myhsm dari langganan Anda saat ini.

### Contoh 2: Menghapus hsm yang dikelola dari grup sumber daya tertentu
```powershell
Remove-AzKeyVaultManagedHsm -HsmName 'myhsm' -ResourceGroupName "myrg1" -PassThru
```

```output
True
```

Perintah ini menghapus HSM terkelola bernama myhsm dari grup sumber daya bernama myrg1.
Jika Anda tidak menentukan nama grup sumber daya, cmdlet mencari HSM terkelola bernama untuk dihapus dalam langganan Anda saat ini.

### Contoh 3: Membersihkan hsm terkelola yang dihapus
```powershell
PS C:\> Remove-AzKeyVaultManagedHsm -Name 'myhsm' -Location "eastus" -Force -PassThru
```

```output
True
```

Perintah ini membersihkan HSM yang dikelola bernama myhsm yang terletak di eastus.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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

### -Paksa
Menunjukkan bahwa cmdlet tidak meminta konfirmasi kepada Anda.
Secara default, cmdlet ini meminta Anda untuk mengonfirmasi bahwa Anda ingin menghapus HSM yang dikelola.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek HSM yang dikelola untuk dihapus.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm
Parameter Sets: RemoveManagedHsmByInputObject, RemoveDeletedManagedHsmByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InRemovedState
Hapus kumpulan HSM terkelola yang sebelumnya dihapus secara permanen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveDeletedManagedHsmByName, RemoveDeletedManagedHsmByInputObject, RemoveDeletedManagedHsmByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi kumpulan HSM yang dikelola yang dihapus.

```yaml
Type: System.String
Parameter Sets: RemoveDeletedManagedHsmByName, RemoveDeletedManagedHsmByResourceId
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama HSM yang dikelola untuk dihapus.

```yaml
Type: System.String
Parameter Sets: RemoveManagedHsmByName, RemoveDeletedManagedHsmByName
Aliases: HsmName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk HSM yang dikelola Azure untuk dihapus.

```yaml
Type: System.String
Parameter Sets: RemoveManagedHsmByName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya ManagedHsm.

```yaml
Type: System.String
Parameter Sets: RemoveManagedHsmByResourceId, RemoveDeletedManagedHsmByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengesampingkan langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak mempengaruhi cmdlet berikutnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzKeyVaultManagedHsm](./Get-AzKeyVaultManagedHsm.md)

[New-AzKeyVaultManagedHsm](./New-AzKeyVaultManagedHsm.md)

[Update-AzKeyVaultManagedHsm](./Update-AzKeyVaultManagedHsm.md)