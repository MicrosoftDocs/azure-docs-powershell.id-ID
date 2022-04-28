---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/remove-aznetappfilesactivedirectory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Remove-AzNetAppFilesActiveDirectory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Remove-AzNetAppFilesActiveDirectory.md
ms.openlocfilehash: 5aa36e38e206d3ffa4f9d2dfe27da415b5a8e2b0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144184094"
---
# Remove-AzNetAppFilesActiveDirectory

## SYNOPSIS
Menghapus konfigurasi direktori aktif Azure NetApp Files (ANF).

## SYNTAX

### ByFieldsParameterSet (Default)
```
Remove-AzNetAppFilesActiveDirectory -ResourceGroupName <String> -AccountName <String>
 -ActiveDirectoryId <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Remove-AzNetAppFilesActiveDirectory -ActiveDirectoryId <String> -AccountObject <PSNetAppFilesAccount>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Remove-AzNetAppFilesActiveDirectory -InputObject <PSNetAppFilesActiveDirectory> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzNetAppFilesActiveDirectory** menghapus konfigurasi direktori aktif ANF.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzNetAppFilesActiveDirectory -ResourceGroupName "MyRG" -AccountName "MyAccount" -ActiveDirectoryId "MyActiveDirectoryId"
```

Perintah ini menghapus konfigurasi direktori aktif ANF baru dengan nama "MyADName".

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
Akun untuk objek Direktori Aktif

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

### -ActiveDirectoryId
ID direktori aktif ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
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

### -InputObject
Objek direktori aktif yang akan dihapus

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesActiveDirectory
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan apakah Direktori Aktif yang ditentukan berhasil dihapus

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

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesActiveDirectory

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesActiveDirectory

## NOTES

## RELATED LINKS
