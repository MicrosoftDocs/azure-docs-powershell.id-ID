---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/enable-azsynapseactivedirectoryonlyauthentication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Enable-AzSynapseActiveDirectoryOnlyAuthentication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Enable-AzSynapseActiveDirectoryOnlyAuthentication.md
ms.openlocfilehash: 84854ec3119a10e9c361cfeab10875d0176d19ee
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145710604"
---
# Enable-AzSynapseActiveDirectoryOnlyAuthentication

## SYNOPSIS
Mengaktifkan autentikasi Azure Active Directory (Azure AD) hanya untuk ruang kerja Synapse tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/enable-azsynapseactivedirectoryonlyauthentication) untuk informasi terbaru.

## SYNTAX

### EnableByNameParameterSet (Default)
```
Enable-AzSynapseActiveDirectoryOnlyAuthentication [-ResourceGroupName <String>] -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByParentObjectParameterSet
```
Enable-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceObject <PSSynapseWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByResourceIdParameterSet
```
Enable-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzSynapseActiveDirectoryOnlyAuthentication memungkinkan autentikasi** hanya Azure Active Directory (Azure AD) untuk ruang kerja Synapse tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Enable-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceName ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini memungkinkan autentikasi Azure AD hanya untuk ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -WorkspaceName ContosoWorkspace
PS C:\> $ws | Enable-AzSynapseActiveDirectoryOnlyAuthentication
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini memungkinkan Azure AD hanya autentikasi untuk ruang kerja ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
PS C:\> Enable-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini memungkinkan autentikasi Azure AD hanya untuk ruang kerja ContosoWorkspace oleh ResourceId.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: EnableByNameParameterSet
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
Parameter Sets: EnableByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: EnableByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: EnableByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSAzureADOnlyAuthentication

## NOTES

## RELATED LINKS
