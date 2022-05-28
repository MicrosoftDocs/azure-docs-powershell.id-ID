---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/get-aznetappfilesbackuppolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesBackupPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesBackupPolicy.md
ms.openlocfilehash: 57345f074758ae4121c95924ab8afe33ed8a5199
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145501095"
---
# Get-AzNetAppFilesBackupPolicy

## SYNOPSIS
Mendapatkan detail Kebijakan Pencadangan Azure NetApp Files (ANF).

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzNetAppFilesBackupPolicy -ResourceGroupName <String> -AccountName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzNetAppFilesBackupPolicy [-Name <String>] -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzNetAppFilesBackupPolicy [-Name <String>] -AccountObject <PSNetAppFilesAccount>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetAppFilesBackupPolicy** mendapatkan detail kebijakan pencadangan ANF.

## EXAMPLES

### Contoh 1
```powershell
Get-AzNetAppFilesBackupPolicy -ResourceGroupName "MyRG" -AccountName "MyAnfAccount" -Name "MyBackupPolicy"
```

Perintah ini mendapatkan kebijakan cadangan bernama "MyBackupPolicy" untuk akun "MyAnfAccount".

## PARAMETERS

### -AccountName
Nama akun ANF

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

### -AccountObject
Objek Akun yang berisi Kebijakan Pencadangan untuk dikembalikan

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Nama kebijakan pencadangan ANF

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BackupPolicyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya akun ANF

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

### -ResourceId
Id sumber daya Kebijakan Pencadangan ANF

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy

## NOTES

## RELATED LINKS

[New-AzNetAppFilesBackupPolicy](./New-AzNetAppFilesBackupPolicy.md)
 [Update-AzNetAppFilesBackupPolicy](./Update-AzNetAppFilesBackupPolicy.md)
 [Remove-AzNetAppFilesBackupPolicy](./Remove-AzNetAppFilesBackupPolicy.md)
 [Set-AzNetAppFilesBackupPolicy](./Set-AzNetAppFilesBackupPolicy.md)
 [Get-AzNetAppFilesBackup](./Get-AzNetAppFilesBackup.md)
 [New-AzNetAppFilesBackup](./New-AzNetAppFilesBackup.md)
 [Remove-AzNetAppFilesBackup](./Remove-AzNetAppFilesBackup.md)
 [Update-AzNetAppFilesBackup](./Update-AzNetAppFilesBackup.md)
 [Get-AzNetAppFilesVault](./Get-AzNetAppFilesVault.md)
 [Get-AzNetAppFilesVolume](./Get-AzNetAppFilessVolume.md)
 [New-AzNetAppFilesVolume](./New-AzNetAppFilessVolume.md)
 [Update-AzNetAppFilesVolume](./Update-AzNetAppFilessVolume.md)
 [Remove-AzNetAppFilesVolume](./Remove-AzNetAppFilessVolume.md)