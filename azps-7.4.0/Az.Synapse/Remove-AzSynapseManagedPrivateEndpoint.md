---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/remove-azsynapsemanagedprivateendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Remove-AzSynapseManagedPrivateEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Remove-AzSynapseManagedPrivateEndpoint.md
ms.openlocfilehash: e29dbcac6fb8d06d29387c8b376b9fa0409eb386
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142000619"
---
# Remove-AzSynapseManagedPrivateEndpoint

## SYNOPSIS
Menghapus titik akhir privat terkelola dari ruang kerja.

## SYNTAX

### RemoveByName (Default)
```
Remove-AzSynapseManagedPrivateEndpoint -WorkspaceName <String> -Name <String> [-VirtualNetworkName <String>]
 [-PassThru] [-AsJob] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RemoveByObject
```
Remove-AzSynapseManagedPrivateEndpoint -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 [-VirtualNetworkName <String>] [-PassThru] [-AsJob] [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByInputObject
```
Remove-AzSynapseManagedPrivateEndpoint -InputObject <PSManagedPrivateEndpointResource>
 [-VirtualNetworkName <String>] [-PassThru] [-AsJob] [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzSynapseManagedPrivateEndpoint** menghapus titik akhir privat terkelola dari ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace -Name ContosoManagedPrivateEndpoint
```

Hapus titik akhir privat terkelola yang disebut ContosoManagedPrivateEndpoint dari ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Remove-AzSynapseManagedPrivateEndpoint -Name ContosoManagedPrivateEndpoint
```

Hapus titik akhir privat terkelola yang disebut ContosoManagedPrivateEndpoint dari ruang kerja ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
$privateendpint = Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace -Name ContosoManagedPrivateEndpoint
$privateendpint | Remove-AzSynapseManagedPrivateEndpoint
```

Hapus titik akhir privat terkelola yang disebut ContosoManagedPrivateEndpoint dari ruang kerja ContosoWorkspace melalui pipeline.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Paksa
Jangan meminta konfirmasi.

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

### -InputObject
Objek Titik Akhir Pribadi yang Dikelola Synapse.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSManagedPrivateEndpointResource
Parameter Sets: RemoveByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Titik Akhir Pribadi yang Dikelola Synapse.

```yaml
Type: System.String
Parameter Sets: RemoveByName, RemoveByObject
Aliases: ManagedPrivateEndpointName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

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

### -VirtualNetworkName
Nama Virtual Network terkelola adalah default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: VNetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: RemoveByName
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
Parameter Sets: RemoveByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSManagedPrivateEndpointResource

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
