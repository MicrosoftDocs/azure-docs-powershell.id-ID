---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapselinkedserviceencryptedcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseLinkedServiceEncryptedCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseLinkedServiceEncryptedCredential.md
ms.openlocfilehash: 9730807b5b68325a783efbca23f4344f16ba856e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144240614"
---
# New-AzSynapseLinkedServiceEncryptedCredential

## SYNOPSIS
Enkripsi kredensial dalam layanan tertaut dengan runtime integrasi yang ditentukan.

## SYNTAX

### CreateByName (Default)
```
New-AzSynapseLinkedServiceEncryptedCredential [-ResourceGroupName <String>] -WorkspaceName <String>
 -IntegrationRuntimeName <String> -DefinitionFile <String> [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateByObject
```
New-AzSynapseLinkedServiceEncryptedCredential -WorkspaceObject <PSSynapseWorkspace>
 -IntegrationRuntimeName <String> -DefinitionFile <String> [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
cmdlet New-AzSynapseLinkedServiceEncryptedCredential mengenkripsi kredensial dalam layanan tertaut dengan runtime integrasi yang ditentukan.

Pastikan prasyarat berikut terpenuhi:
* Opsi **akses jarak jauh** diaktifkan pada runtime integrasi yang dihost sendiri.
* Powershell 7.0 atau yang lebih tinggi digunakan untuk menjalankan cmdlet.

## EXAMPLES

### Contoh 1
```powershell
New-AzSynapseLinkedServiceEncryptedCredential -WorkspaceName ContosoWorkspace -ResourceGroupName ContosoRG -IntegrationRuntimeName "IR-LSEncryptedCredential" -DefinitionFile "D:\sqlLinkService.json" > "D:\SynapseEncryptedSQLServerLinkedService.json"
```

Perintah ini mengenkripsi kredensial dalam file D:\SynapseEncryptedSQLServerLinkedService.json dengan runtime integrasi bernama IR-LSEncryptedCredential.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | New-AzSynapseLinkedServiceEncryptedCredential -IntegrationRuntimeName "IR-LSEncryptedCredential" -DefinitionFile "D:\sqlLinkService.json" > "D:\SynapseEncryptedSQLServerLinkedService.json"
```

Perintah ini mengenkripsi kredensial dalam file D:\SynapseEncryptedSQLServerLinkedService.json dengan runtime integrasi bernama IR-LSEncryptedCredential melalui alur.

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

### -DefinitionFile
Jalur file JSON.

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

### -Force
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

### -IntegrationRuntimeName
Nama runtime integrasi.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: CreateByName
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
Parameter Sets: CreateByName
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
Parameter Sets: CreateByObject
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.String

## NOTES

## RELATED LINKS
