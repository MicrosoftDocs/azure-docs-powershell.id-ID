---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/get-aznetappfilesbackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesBackup.md
ms.openlocfilehash: a6b89ae964b7909fbb56edbb7c6d6717bf9c4004
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145556999"
---
# Get-AzNetAppFilesBackup

## SYNOPSIS
Mendapatkan detail Cadangan Azure NetApp Files (ANF).

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzNetAppFilesBackup -ResourceGroupName <String> -AccountName <String> -PoolName <String>
 [-VolumeName <String>] [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByAccountBackupFieldsParameterSet
```
Get-AzNetAppFilesBackup -ResourceGroupName <String> -AccountName <String> [-Name <String>]
 [-AccountBackupName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzNetAppFilesBackup [-Name <String>] [-AccountBackupName <String>] -VolumeObject <PSNetAppFilesVolume>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzNetAppFilesBackup [-Name <String>] -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetAppFilesBackup** mendapatkan detail cadangan ANF.

## EXAMPLES

### Contoh 1
```powershell
Get-AzNetAppFilesBackup -ResourceGroupName "MyRG" -AccountName "MyAccount" -PoolName "MyPool" -VolumeName "MyVolume" -Name "MyBackup"
```

Perintah ini mendapatkan cadangan bernama "MyAnfAccount" dari volume bernama "MyVolume".

### Contoh 2
```powershell
Get-AzNetAppFilesBackup -ResourceGroupName "MyRG" -AccountName "MyAccount" -AccountBackupName "MyBackup"
```

Perintah ini mendapatkan cadangan bernama "MyAnfAccount" dari Akun bernama "MyAccount".

## PARAMETERS

### -AccountBackupName
Nama cadangan ANF

```yaml
Type: System.String
Parameter Sets: ByAccountBackupFieldsParameterSet, ByParentObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountName
Nama akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet, ByAccountBackupFieldsParameterSet
Aliases:

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

### -Name
Nama cadangan ANF

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BackupName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolName
Nama kumpulan ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet, ByAccountBackupFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya Cadangan ANF

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumeName
Nama volume ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeObject
Objek volume yang berisi cadangan yang akan dikembalikan

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolume
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolume

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackup

## NOTES

## RELATED LINKS

[New-AzNetAppFilesBackup](./New-AzNetAppFilesBackup.md)
 [Remove-AzNetAppFilesBackup](./Remove-AzNetAppFilesBackup.md)
 [Update-AzNetAppFilesBackup](./Update-AzNetAppFilesBackup.md)
 [Get-AzNetAppFilesBackupPolicy](./Get-AzNetAppFilesBackupPolicy.md)
 [New-AzNetAppFilesBackupPolicy](./New-AzNetAppFilesBackupPolicy.md)
 [Update-AzNetAppFilesBackupPolicy](./Update-AzNetAppFilesBackupPolicy.md)
 [Remove-AzNetAppFilesBackupPolicy](./Remove-AzNetAppFilesBackupPolicy.md)
 [Get-AzNetAppFilesVault](./Get-AzNetAppFilesVault.md)
 [Get-AzNetAppFilesVolume](./Get-AzNetAppFilesVolume.md)
 [New-AzNetAppFilesVolume](./New-AzNetAppFilesVolume.md)
 [Update-AzNetAppFilesVolume](./Update-AzNetAppFilesVolume.md)
 [Remove-AzNetAppFilesVolume](./Remove-AzNetAppFilesVolume.md)