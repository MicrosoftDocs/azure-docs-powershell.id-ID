---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapseactivedirectoryonlyauthentication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseActiveDirectoryOnlyAuthentication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseActiveDirectoryOnlyAuthentication.md
ms.openlocfilehash: ae7373c38a0ec4f43dc3efb6f944695e8d3afa83
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145534714"
---
# Get-AzSynapseActiveDirectoryOnlyAuthentication

## SYNOPSIS
Mendapatkan autentikasi hanya Azure Active Directory (Azure AD) untuk ruang kerja Synapse tertentu.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzSynapseActiveDirectoryOnlyAuthentication [-ResourceGroupName <String>] -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByParentObjectParameterSet
```
Get-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceObject <PSSynapseWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseActiveDirectoryOnlyAuthentication mendapatkan autentikasi** hanya Azure Active Directory (Azure AD) untuk ruang kerja Synapse tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseActiveDirectoryOnlyAuthentication -WorkspaceName ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini hanya mendapatkan status autentikasi Azure AD untuk ruang kerja Synapse ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseActiveDirectoryOnlyAuthentication
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini hanya mendapatkan status autentikasi Azure AD untuk ruang kerja Synapse ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
PS C:\> Get-AzSynapseActiveDirectoryOnlyAuthentication -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace
```

WorkspaceName AzureADOnlyAuthenticationProperty State CreationDate
-------------     --------------------------------- -----      ------------
ContosoWorkspace True Consistent 3/23/2022 8:27:47 AM

Perintah ini hanya mendapatkan autentikasi Azure AD untuk ruang kerja ContosoWorkspace by ResourceId.

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
Parameter Sets: GetByNameParameterSet
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
Parameter Sets: GetByResourceIdParameterSet
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
Parameter Sets: GetByNameParameterSet
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
Parameter Sets: GetByParentObjectParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSAzureADOnlyAuthentication

## NOTES

## RELATED LINKS
