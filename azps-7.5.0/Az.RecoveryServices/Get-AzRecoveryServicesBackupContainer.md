---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 1097FF29-1C23-4960-930C-5C1227419359
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupContainer.md
ms.openlocfilehash: 9ffab12f2be16bd4c27a4798a3259f24d12702b9
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145650154"
---
# Get-AzRecoveryServicesBackupContainer

## SYNOPSIS

Mendapatkan kontainer Backup.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupcontainer) untuk informasi terbaru.

## SYNTAX

```
Get-AzRecoveryServicesBackupContainer [-ContainerType] <ContainerType> [[-BackupManagementType] <String>]
 [[-FriendlyName] <String>] [[-ResourceGroupName] <String>] [[-Status] <ContainerRegistrationStatus>]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupContainer** mendapatkan kontainer cadangan. Kontainer Backup merangkum sumber data yang dimodelkan sebagai item cadangan.
Untuk jenis Kontainer "Azure VM" , output mencantumkan semua kontainer yang namanya sama persis dengan yang diteruskan sebagai nilai untuk parameter Nama Yang Mudah Diingat. Untuk jenis kontainer lainnya, output memberikan daftar kontainer dengan nama yang mirip dengan nilai yang diteruskan untuk parameter Nama yang mudah diingat.
Atur konteks vault dengan menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Mendapatkan kontainer tertentu

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
Get-AzRecoveryServicesBackupContainer -ContainerType "AzureVM" -Status "Registered" -FriendlyName "V2VM" -VaultId $vault.ID
```

Perintah ini mendapatkan kontainer bernama V2VM jenis AzureVM.

### Contoh 2: Mendapatkan semua kontainer dari jenis tertentu

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
Get-AzRecoveryServicesBackupContainer -ContainerType Windows -BackupManagementType MAB -VaultId $vault.ID
```

Perintah ini mendapatkan semua kontainer Windows yang dilindungi oleh agen Azure Backup.
Parameter **BackupManagementType** hanya diperlukan untuk kontainer Windows.

## PARAMETERS

### -BackupManagementType

Kelas sumber daya yang dilindungi. Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM
- MAB
- AzureWorkload
- AzureStorage

Parameter ini digunakan untuk membedakan Windows mesin yang dicadangkan menggunakan agen MARS atau mesin cadangan lainnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, MAB, AzureWorkload, AzureStorage

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerType

Menentukan jenis kontainer cadangan.
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

Menentukan nama kontainer yang mudah diingat untuk didapatkan.

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
Parameter ini hanya untuk komputer virtual Azure.

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

Menentukan status pendaftaran kontainer.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupManagementServer](./Get-AzRecoveryServicesBackupManagementServer.md)

[Batalkan pendaftaran-AzRecoveryServicesBackupContainer](./Unregister-AzRecoveryServicesBackupContainer.md)
