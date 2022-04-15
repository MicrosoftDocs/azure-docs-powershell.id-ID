---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/enable-azsynapseworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Enable-AzSynapseWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Enable-AzSynapseWorkspace.md
ms.openlocfilehash: 4e37ac73e483ec8d37e79b6012f9d70cc08fe6ae
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142397087"
---
# Enable-AzSynapseWorkspace

## SYNOPSIS
Saat membuat ruang kerja analitik Azure Synapse, Anda dapat memilih untuk mengenkripsi semua data saat disimpan di ruang kerja 'dengan kunci yang dikelola pelanggan yang akan menyediakan enkripsi ganda ke ruang kerja. Anda mungkin perlu menyiapkan lingkungan enkripsi terlebih dahulu, seperti membuat brankas kunci dengan mengaktifkan perlindungan pembersihan dan menentukan Polisi Akses ke kubah kunci. Lalu gunakan cmdlet ini untuk mengaktifkan ruang kerja Azure Synapse Analytics baru yang enkripsi ganda diaktifkan menggunakan kunci yang dikelola pelanggan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/enable-azsynapseworkspace) untuk informasi terbaru.

## SYNTAX

### EnableByNameParameterSet (Default)
```
Enable-AzSynapseWorkspace [-ResourceGroupName <String>] -WorkspaceName <String> [-Name <String>]
 [-EncryptionKeyIdentifier <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### EnableByParentObjectParameterSet
```
Enable-AzSynapseWorkspace [-Name <String>] -WorkspaceObject <PSSynapseWorkspace>
 [-EncryptionKeyIdentifier <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### EnableByInputObjectParameterSet
```
Enable-AzSynapseWorkspace -InputObject <PSWorkspaceKey> [-EncryptionKeyIdentifier <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByResourceIdParameterSet
```
Enable-AzSynapseWorkspace -ResourceId <String> [-EncryptionKeyIdentifier <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Enable-AzSynapseWorkspace mengaktifkan ruang kerja Azure Synapse Analytics baru yang enkripsi ganda diaktifkan menggunakan kunci yang dikelola pelanggan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Enable-AzSynapseWorkspace -WorkspaceName ContosoWorkspace
```

Perintah ini mengaktifkan ruang kerja Azure Synapse Analytics baru bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
        $ws | Enable-AzSynapseWorkspace
```

Perintah ini mengaktifkan ruang kerja Azure Synapse Analytics baru bernama ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
PS C:\> Enable-AzSynapseWorkspace -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace/keys/default
```

Perintah ini mengaktifkan ruang kerja Azure Synapse Analytics baru melalui pipeline dengan ID sumber daya tertentu.

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

### -EncryptionKeyIdentifier
Pengidentifikasi kunci harus dalam format: https://{keyvaultname}.vault.azure.net/keys/{keyname}.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek input tombol ruang kerja, biasanya melewati pipeline.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.WorkspaceKey.PSWorkspaceKey
Parameter Sets: EnableByInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kunci enkripsi ruang kerja.

```yaml
Type: System.String
Parameter Sets: EnableByNameParameterSet, EnableByParentObjectParameterSet
Aliases: KeyName

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
Pengidentifikasi sumber daya Synapse SQL Pool.

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

### -Nama Ruang Kerja
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
objek input ruang kerja, biasanya melewati saluran.

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

### Microsoft.Azure.Commands.Synapse.Models.WorkspaceKey.PSWorkspaceKey

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.WorkspaceKey.PSWorkspaceKey

## CATATAN

## RELATED LINKS
