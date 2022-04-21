---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/add-azsynapsedataflowdebugsessionpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Add-AzSynapseDataFlowDebugSessionPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Add-AzSynapseDataFlowDebugSessionPackage.md
ms.openlocfilehash: 6838469fc1718ee0da698023d2f467120396499a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142706248"
---
# Add-AzSynapseDataFlowDebugSessionPackage

## SYNOPSIS
Tambahkan sumber daya alur data dan dependensinya ke dalam sesi debug alur data tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/add-azsynapsedataflowdebugsessionpackage) untuk informasi terbaru.

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
Perintah ini melampirkan sumber daya alur data dan dependensinya ke sesi debug tertentu. Urutan perintah PowerShell untuk alur kerja debug alur data harus:

Start-AzSynapseDataFlowDebugSession  
Add-AzSynapseDataFlowDebugSessionPackage  
Invoke-AzSynapseDataFlowDebugSessionCommand (ulangi langkah ini untuk perintah/target yang berbeda, atau ulangi langkah 2-3 untuk mengubah file paket)  
Stop-AzSynapseDataFlowDebugSession

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Add-AzSynapseDataFlowDebugSessionPackage -WorkspaceName ContosoWorkspace -PackageFile "D:\dataflowps\addpackage.json" -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc
```

Tambahkan paket alur data ke sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di bawah Ruang kerja Synapse "ContosoWorkspace". File Pakcage berisi sumber daya debug aliran data, daftar dataset debug resouce, daftar sumber daya debug layanan tertaut, pengaturan debug dan ID sesi. [-SessionId] parameter bersifat opsional, jika ditentukan, parameter akan menggantikan properti sessionId yang sudah ada dalam file kemasan.  

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Add-AzSynapseDataFlowDebugSessionPackage -PackageFile "D:\dataflowps\addpackage.json" -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc
```

Tambahkan paket alur data ke sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di bawah Ruang kerja Synapse "ContosoWorkspace" melalui pipeline.

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
Pengidentifikasi untuk sesi debug alur data Synapse.

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

### -Nama Ruang Kerja
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
objek input ruang kerja, biasanya melewati saluran.

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

### Microsoft.Azure.Commands.Synapse.Models.PSAddDataFlowToDebugSessionResponse

## NOTES

## RELATED LINKS
