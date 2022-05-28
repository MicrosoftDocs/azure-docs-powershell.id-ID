---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/disable-azsynapseactivedirectoryonlyauthentication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Disable-AzSynapseActiveDirectoryOnlyAuthentication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Disable-AzSynapseActiveDirectoryOnlyAuthentication.md
ms.openlocfilehash: 5a7c44caed4b82fa6bc1c8f5e27bd9dea03e5f90
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522666"
---
# Disable-AzSynapseActiveDirectoryOnlyAuthentication

## SYNOPSIS
Menonaktifkan autentikasi Azure Active Directory (Azure AD) saja untuk ruang kerja Synapse tertentu.

## SYNTAX

### DisableByNameParameterSet (Default)
```
Disable-AzSynapseActiveDirectoryOnlyAuthentication [-ResourceGroupName <String>] -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableByParentObjectParameterSet
```
Disable-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceObject <PSSynapseWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableByResourceIdParameterSet
```
Disable-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzSynapseActiveDirectoryOnlyAuthentication menonaktifkan autentikasi** hanya Azure Active Directory (Azure AD) untuk ruang kerja Synapse tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Disable-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceName ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace False Consistent 3/23/2022 8:27:47 AM

Perintah ini menonaktifkan Azure AD hanya autentikasi untuk ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -WorkspaceName ContosoWorkspace
PS C:\> $ws | Disable-AzSynapseActiveDirectoryOnlyAuthentication
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace False Consistent 3/23/2022 8:27:47 AM

Perintah ini menonaktifkan Azure AD hanya autentikasi untuk ruang kerja ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
PS C:\> Disable-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace False Consistent 3/23/2022 8:27:47 AM

Perintah ini menonaktifkan Azure AD hanya autentikasi untuk ruang kerja ContosoWorkspace oleh ResourceId.

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
Parameter Sets: DisableByNameParameterSet
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
Parameter Sets: DisableByResourceIdParameterSet
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
Parameter Sets: DisableByNameParameterSet
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
Parameter Sets: DisableByParentObjectParameterSet
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
