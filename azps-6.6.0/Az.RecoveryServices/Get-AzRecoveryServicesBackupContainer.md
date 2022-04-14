---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 1097FF29-1C23-4960-930C-5C1227419359
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupContainer.md
ms.openlocfilehash: fc049aefb9bc25ce4cb73590e3aaf879e66721e1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142225189"
---
# Get-AzRecoveryServicesBackupContainer

## SYNOPSIS

Mendapatkan pencadangan kontainer.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupcontainer) untuk informasi terbaru.

## SYNTAX

```
Get-AzRecoveryServicesBackupContainer [-ContainerType] <ContainerType> [[-BackupManagementType] <String>]
 [[-FriendlyName] <String>] [[-ResourceGroupName] <String>] [[-Status] <ContainerRegistrationStatus>]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupContainer** mendapatkan wadah cadangan. Wadah Cadangan merangkum sumber data yang dimodelkan sebagai item cadangan.
Untuk tipe Kontainer "Azure VM" , output mencantumkan semua kontainer yang namanya sama persis dengan yang dilewatkan sebagai nilai untuk parameter Friendly Name. Untuk tipe kontainer lainnya, output memberikan daftar kontainer dengan nama yang mirip dengan nilai yang dilewati untuk parameter Nama yang mudah dikenali.
Mengatur konteks kubah menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Mendapatkan wadah tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> Get-AzRecoveryServicesBackupContainer -ContainerType "AzureVM" -Status "Registered" -FriendlyName "V2VM" -VaultId $vault.ID
```

Perintah ini mendapatkan wadah bernama V2VM tipe AzureVM.

### Contoh 2: Mendapatkan semua kontainer dari tipe tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> Get-AzRecoveryServicesBackupContainer -ContainerType Windows -BackupManagementType MARS -VaultId $vault.ID
```

Perintah ini mendapatkan semua wadah Windows yang dilindungi oleh agen Azure Backup.
Parameter **BackupManagementType** hanya diperlukan untuk kontainer Windows.

## PARAMETERS

### -BackupManagementType

Kelas sumber daya yang dilindungi. Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM
- MARS
- AzureWorkload
- AzureStorage

Parameter ini digunakan untuk membedakan mesin Windows yang dicadangkan menggunakan agen MARS atau mesin cadangan lainnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, MARS, AzureWorkload, AzureStorage

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerType

Menentukan tipe wadah cadangan.
Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM
- Windows
- AzureStorage
- AzureVMAppContainer

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerType
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, Windows, AzureStorage, AzureVMAppContainer

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -FriendlyName

Menentukan nama kontainer yang mudah didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName

Menentukan nama grup sumber daya.
Parameter ini hanya untuk mesin virtual Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Menentukan status registrasi kontainer.
Nilai yang dapat diterima untuk parameter ini adalah:

- Terdaftar

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerRegistrationStatus
Parameter Sets: (All)
Aliases:
Accepted values: Registered

Required: False
Position: 5
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupManagementServer](./Get-AzRecoveryServicesBackupManagementServer.md)

[Unregister-AzRecoveryServicesBackupContainer](./Unregister-AzRecoveryServicesBackupContainer.md)
