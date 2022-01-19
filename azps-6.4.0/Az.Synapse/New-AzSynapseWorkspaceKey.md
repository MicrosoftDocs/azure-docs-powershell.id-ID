---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapseworkspacekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspaceKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspaceKey.md
ms.openlocfilehash: 58c6913d0ada4a5a1ce71b77edd7957fc277ee0c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136164990"
---
# New-AzSynapseWorkspaceKey

## SYNOPSIS
Membuat kunci ruang kerja.

## SYNTAX

### CreateByNameParameterSet (Default)
```
New-AzSynapseWorkspaceKey [-ResourceGroupName <String>] -WorkspaceName <String> -Name <String>
 -EncryptionKeyIdentifier <String> [-Activate] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CreateByParentObjectParameterSet
```
New-AzSynapseWorkspaceKey -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -EncryptionKeyIdentifier <String> [-Activate] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseWorkspaceKey** ini membuat kunci ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSynapseWorkspaceKey -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoWorkspaceKey -EncryptionKeyIdentifier https://<key-vault-url>/keys/<key-name>
```

Perintah ini membuat kunci ruang kerja bernama ContosoWorkspaceKey di bawah ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | New-AzSynapseWorkspaceKey -Name ContosoWorkspaceKey -EncryptionKeyIdentifier https://<key-vault-url>/keys/<key-name>
```

Perintah ini membuat kunci ruang kerja bernama ContosoWorkspaceKey di bawah ruang kerja ContosoWorkspace melalui pipeline.

## PARAMETERS

### -Activate
Menunjukkan apakah akan mengaktifkan ruang kerja setelah kunci terkelola pelanggan disediakan.

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

### -EncryptionKeyIdentifier
Pengidentifikasi kunci harus dalam format: https://{keyvaultname}.vault.azure.net/keys/{keyname}.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kunci ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: KeyName

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
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
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
Parameter Sets: CreateByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.WorkspaceKey.PSWorkspaceKey

## CATATAN

## RELATED LINKS
