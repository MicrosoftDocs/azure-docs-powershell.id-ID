---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsemanagedidentitysqlcontrolsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseManagedIdentitySqlControlSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseManagedIdentitySqlControlSetting.md
ms.openlocfilehash: ee6efdec0cfc022a356c21d475b68e8e56de7d57
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142205425"
---
# Set-AzSynapseManagedIdentitySqlControlSetting

## SYNOPSIS
Pembaruan identitas terkelola SQL mengontrol pengaturan ke ruang kerja.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/set-azsynapsemanagedidentitysqlcontrolsetting) untuk informasi terbaru.

## SYNTAX

### ByNameParameterSet (Default)
```
Set-AzSynapseManagedIdentitySqlControlSetting [-ResourceGroupName <String>] -WorkspaceName <String>
 -Enabled <Boolean> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Set-AzSynapseManagedIdentitySqlControlSetting -WorkspaceObject <PSSynapseWorkspace> -Enabled <Boolean>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Set-AzSynapseManagedIdentitySqlControlSetting -ResourceId <String> -Enabled <Boolean>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Set-AzSynapseManagedIdentitySqlControlSetting** memperbarui identitas terkelola SQL pengaturan kontrol ke ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSynapseManagedIdentitySqlControlSetting -WorkspaceName ContosoWorkspace -Enabled $true
```

Perintah ini memungkinkan identitas terkelola SQL mengontrol pengaturan ke ruang kerja untuk ContosoWorkspace ruang kerja.

### Contoh 2
```powershell
PS C:\> Set-AzSynapseManagedIdentitySqlControlSetting -WorkspaceName ContosoWorkspace -Enabled $false
```

Perintah ini menonaktifkan identitas terkelola SQL pengaturan kontrol ke ruang kerja untuk Ruang Kerja ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Set-AzSynapseManagedIdentitySqlControlSetting -Enabled $true
```

Perintah ini memungkinkan identitas terkelola SQL mengontrol pengaturan ke ruang kerja untuk ruang kerja ContosoWorkspace melalui pipeline.

### Contoh 4
```powershell
PS C:\> Set-AzSynapseManagedIdentitySqlControlSetting -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd3/resourcegroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace -Enabled $true
```

Perintah ini memungkinkan identitas terkelola SQL mengontrol pengaturan ke ruang kerja untuk ruang kerja ContosoWorkspace melalui ID sumber daya ruang kerja.

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

### -Difungsikan
Menunjukkan apakah mengaktifkan pengaturan kontrol SQL identitas terkelola.
Tentukan $True untuk mengaktifkan pengaturan kontrol SQL identitas terkelola, atau $False untuk menonaktifkan pengaturan kontrol SQL identitas terkelola.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSManagedIdentitySqlControlSettingsModel

## CATATAN

## RELATED LINKS
