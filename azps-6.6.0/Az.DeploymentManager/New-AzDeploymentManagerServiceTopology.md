---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DeploymentManager.dll-Help.xml
Module Name: Az.DeploymentManager
online version: https://docs.microsoft.com/powershell/module/az.deploymentmanager/new-azdeploymentmanagerservicetopology
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeploymentManager/DeploymentManager/help/New-AzDeploymentManagerServiceTopology.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeploymentManager/DeploymentManager/help/New-AzDeploymentManagerServiceTopology.md
ms.openlocfilehash: 9a77158cf9b1eab4ae633856370ed49f29cc183d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142052021"
---
# New-AzDeploymentManagerServiceTopology

## SYNOPSIS
Membuat topologi layanan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.deploymentmanager/new-azdeploymentmanagerservicetopology) untuk informasi terbaru.

## SYNTAX

```
New-AzDeploymentManagerServiceTopology -ResourceGroupName <String> -Name <String> -Location <String>
 [-ArtifactSourceId <String>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDeploymentManagerServiceTopology** menciptakan topologi layanan.

Anda dapat mengubah objek ServiceTopology yang dikembalikan secara lokal, lalu menerapkan perubahan pada topologi menggunakan cmdlet Set-AzDeploymentManagerServiceTopology.
Objek yang dikembalikan 

Objek yang dikembalikan memiliki bidang ResourceId yang dapat dirujuk dalam sumber daya peluncuran untuk menunjukkan bahwa layanan yang dideklarasikan dalam topologi layanan ini akan digunakan dalam peluncuran.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzDeploymentManagerServiceTopology -ResourceGroupName ContosoResourceGroup -Name ContosoServiceTopology -Location "Central US" -ArtifactSourceId "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourcegroups/ContosoResourceGroup/providers/Microsoft.DeploymentManager/artifactSources/ContosoArtifactSource"
```

Cmdlet ini membuat topologi layanan baru dalam grup sumber daya ContosoResourceGroup dengan nama ContosoServiceTopology dan di lokasi As Tengah. Sumber artefak ResourceId menunjukkan bahwa artefak yang diperlukan untuk definisi unit layanan dalam topologi ini perlu dibaca dari sumber artefak yang ditentukan.

### Contoh 2
```powershell
PS C:\> New-AzDeploymentManagerServiceTopology -ResourceGroupName ContosoResourceGroup -Name ContosoServiceTopology -Location "Central US"
```

Cmdlet ini membuat topologi layanan baru dalam grup sumber daya ContosoResourceGroup dengan nama ContosoServiceTopology dan di lokasi As Tengah. Tidak adanya referensi sumber artefak menunjukkan bahwa artefak yang diperlukan untuk definisi unit layanan dalam topologi ini akan disediakan sebagai URI SAS absolut dalam unit layanan.

## PARAMETERS

### -ArtifactSourceId
Pengidentifikasi sumber artefak, di mana artefak yang menyusun topologi disimpan.

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

### -Lokasi
Lokasi topologi.

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
Nama topologi.

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
Grup sumber daya.

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

### -Tag
Tabel hash yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSServiceTopologyResource

## CATATAN

## RELATED LINKS
