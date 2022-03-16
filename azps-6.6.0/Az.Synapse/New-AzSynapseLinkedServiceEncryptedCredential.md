---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapselinkedserviceencryptedcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseLinkedServiceEncryptedCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseLinkedServiceEncryptedCredential.md
ms.openlocfilehash: 6f081074220500e1016ca935160c996d484be896
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140129481"
---
# New-AzSynapseLinkedServiceEncryptedCredential

## SYNOPSIS
Enkripsi kredensial dalam layanan tertaut dengan runtime integrasi tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.synapse/new-azsynapselinkedserviceencryptedcredential) untuk informasi terkini.

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
Kredensial enkripsi cmdlet New-AzSynapseLinkedServiceEncryptedCredential dalam layanan tertaut dengan runtime integrasi tertentu.

Harap pastikan persyaratan berikut ini terpenuhi:
* **Opsi akses** jarak jauh diaktifkan pada runtime integrasi yang dihosting sendiri.
* Powershell 7.0 atau lebih tinggi digunakan untuk menjalankan cmdlet.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSynapseLinkedServiceEncryptedCredential -WorkspaceName ContosoWorkspace -ResourceGroupName ContosoRG -IntegrationRuntimeName "IR-LSEncryptedCredential" -DefinitionFile "D:\sqlLinkService.json" > "D:\SynapseEncryptedSQLServerLinkedService.json"
```

Perintah ini mengenkripsi kredensial di file D:\SynapseEncryptedSQLServerLinkedService.json dengan runtime integrasi yang bernama IR-LSEncryptedCredential.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | New-AzSynapseLinkedServiceEncryptedCredential -IntegrationRuntimeName "IR-LSEncryptedCredential" -DefinitionFile "D:\sqlLinkService.json" > "D:\SynapseEncryptedSQLServerLinkedService.json"
```

Perintah ini mengenkripsi kredensial di file D:\SynapseEncryptedSQLServerLinkedService.json dengan runtime integrasi IR-LSEncryptedCredential melalui saluran.

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
Jangan minta konfirmasi.

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
objek input ruang kerja, biasanya melewati saluran.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS
