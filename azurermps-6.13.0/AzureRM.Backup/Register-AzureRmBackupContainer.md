---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 394500DB-D2BB-4793-8D9F-2CAF4D892A55
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/register-azurermbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Register-AzureRmBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Register-AzureRmBackupContainer.md
ms.openlocfilehash: 3431650296c29f06131f946910d1cbc3dc6e6bb0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142359518"
---
# Register-AzureRmBackupContainer

## SYNOPSIS
Mendaftarkan wadah dengan kubah Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### V1VM
```
Register-AzureRmBackupContainer -Name <String> -ServiceName <String> [-Vault] <AzureRMBackupVault>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### V2VM
```
Register-AzureRmBackupContainer -Name <String> -ResourceGroupName <String> [-Vault] <AzureRMBackupVault>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Register-AzureRmBackupContainer** mendaftarkan kontainer dengan kubah Azure Backup.
Untuk mengonfigurasi pencadangan dengan menggunakan Azure Backup, daftarkan server atau mesin virtual Anda terlebih dahulu dengan kubah Cadangan.
Cmdlet ini mendaftarkan mesin virtual infrastruktur sebagai layanan (IaaS) dengan kubah yang ditentukan.
Operasi register mengaitkan mesin virtual Azure dengan kubah cadangan dan melacak mesin virtual melalui siklus hidup cadangan.

## EXAMPLES

### Contoh 1: Daftarkan mesin virtual ke kubah Cadangan
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> Register-AzureRmBackupContainer -Vault $Vault -Name "Contoso03Vm" -ServiceName "ContosoService27"
```

Perintah pertama mendapatkan kubah bernama Vault03 dengan menggunakan cmdlet Get-AzureRmBackupVault.
Perintah menyimpan kubah dalam variabel $Vault.
Perintah kedua mendaftarkan mesin virtual bernama Contoso03Vm dengan kubah di $Vault.
Mesin virtual itu milik layanan bernama ContosoService27.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama mesin virtual yang didaftarkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: V2VM
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan mesin virtual yang didaftarkan cmdlet ini.
Biasanya, nama layanan awan memiliki akhiran .cloudapp.net.
Jangan sertakan akhiran ketika Anda menentukan parameter ini.
Untuk mendapatkan informasi tentang mesin virtual, gunakan cmdlet Get-AzureRMVM.
Nama layanan adalah properti **DeploymentName** dari objek mesin virtual.

```yaml
Type: System.String
Parameter Sets: V1VM
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Vault
Menentukan kubah Cadangan tempat cmdlet ini mendaftarkan mesin virtual.
Untuk mendapatkan objek **AzureRmBackupVault** , gunakan cmdlet Get-AzureRmBackupVault.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter: Vault (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)


