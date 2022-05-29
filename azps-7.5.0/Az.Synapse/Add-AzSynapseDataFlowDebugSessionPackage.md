---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/add-azsynapsedataflowdebugsessionpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Add-AzSynapseDataFlowDebugSessionPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Add-AzSynapseDataFlowDebugSessionPackage.md
ms.openlocfilehash: 4657ce07911ca73c55f7c21bc6dc13e1fee0c6c8
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145710891"
---
# Add-AzSynapseDataFlowDebugSessionPackage

## SYNOPSIS
Tambahkan sumber daya aliran data dan dependensinya ke dalam sesi debug aliran data tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/add-azsynapsedataflowdebugsessionpackage) untuk informasi terbaru.

## SYNTAX

### AddByName (Default)
```
Add-AzSynapseDataFlowDebugSessionPackage -WorkspaceName <String> -PackageFile <String> [-SessionId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AddByObject
```
Add-AzSynapseDataFlowDebugSessionPackage -WorkspaceObject <PSSynapseWorkspace> -PackageFile <String>
 [-SessionId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini melampirkan sumber daya aliran data dan dependensinya ke sesi debug tertentu. Urutan perintah PowerShell untuk alur kerja debug aliran data harus:

Start-AzSynapseDataFlowDebugSession  
Add-AzSynapseDataFlowDebugSessionPackage  
Invoke-AzSynapseDataFlowDebugSessionCommand (ulangi langkah ini untuk perintah/target yang berbeda, atau ulangi langkah 2-3 untuk mengubah file paket)  
Stop-AzSynapseDataFlowDebugSession

## EXAMPLES

### Contoh 1
```powershell
Add-AzSynapseDataFlowDebugSessionPackage -WorkspaceName ContosoWorkspace -PackageFile "D:\dataflowps\addpackage.json" -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc
```

Tambahkan paket aliran data ke sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di bawah ruang kerja Synapse "ContosoWorkspace". File Pakcage berisi sumber daya debug aliran data, daftar sumber daya debug himpunan data, daftar sumber daya debug layanan tertaut, pengaturan debug, dan ID sesi. Parameter [-SessionId] bersifat opsional, jika ditentukan, parameter tersebut akan menggantikan properti sessionId yang ada dalam file paket.  

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Add-AzSynapseDataFlowDebugSessionPackage -PackageFile "D:\dataflowps\addpackage.json" -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc
```

Tambahkan paket aliran data ke sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di bawah ruang kerja Synapse "ContosoWorkspace" melalui alur.

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

### -PackageFile
Jalur file JSON.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: File

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionId
Pengidentifikasi untuk sesi debug aliran data Synapse.

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

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: AddByName
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
Parameter Sets: AddByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSAddDataFlowToDebugSessionResponse

## NOTES

## RELATED LINKS
