---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DeploymentManager.dll-Help.xml
Module Name: Az.DeploymentManager
online version: https://docs.microsoft.com/powershell/module/az.deploymentmanager/get-azdeploymentmanagerrollout
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeploymentManager/DeploymentManager/help/Get-AzDeploymentManagerRollout.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeploymentManager/DeploymentManager/help/Get-AzDeploymentManagerRollout.md
ms.openlocfilehash: f16acbba0cdb20793f3b3909686d5fea6c7a5a3f
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145745974"
---
# Get-AzDeploymentManagerRollout

## SYNOPSIS
Mendapatkan peluncuran.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.deploymentmanager/get-azdeploymentmanagerrollout) untuk informasi terbaru.

## SYNTAX

### Interaktif (Default)
```
Get-AzDeploymentManagerRollout [-ResourceGroupName] <String> [[-Name] <String>] [-RetryAttempt <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzDeploymentManagerRollout [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InputObject
```
Get-AzDeploymentManagerRollout [-InputObject] <PSRollout> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDeploymentManagerRollout** mendapatkan peluncuran, dan mengembalikan objek yang mewakili peluncuran tersebut dengan semua informasi terperinci tentang kemajuan peluncuran.
Tentukan peluncuran berdasarkan nama dan nama grup sumber dayanya. Secara bergantian, Anda dapat menyediakan objek Peluncuran atau ResourceId.

Objek peluncuran yang dikembalikan berisi layanan, unit layanan, dan langkah-langkah yang telah disebarkan dan yang sedang berlangsung. Mereka yang belum disebarkan tidak dalam respons.

## EXAMPLES

### Contoh 1 Dapatkan peluncuran
```powershell
Get-AzDeploymentManagerRollout -ResourceGroupName ContosoResourceGroup -Name ContosoRollout
```

Perintah ini mendapatkan peluncuran bernama ContosoRollout di ContosoResourceGroup. 

### Contoh 2 Dapatkan dan tampilkan detail peluncuran
```powershell
Get-AzDeploymentManagerRollout -ResourceGroupName ContosoResourceGroup -Name ContosoRollout -Verbose
```

Perintah ini mendapatkan peluncuran bernama ContosoRollout di ContosoResourceGroup. Sakelar -Verbose menampilkan semua detail peluncuran secara hierarkis; menampilkan Layanan, ServiceUnits, dan langkah-langkah di bawah setiap ServiceUnit dan informasi kontekstual untuk setiap langkah untuk tampilan holistik peluncuran.

### Contoh 3: Mendapatkan peluncuran menggunakan pengidentifikasi sumber daya
```powershell
Get-AzDeploymentManagerRollout -ResourceId "/subscriptions/subscriptionId/resourcegroups/ContosoResourceGroup/providers/Microsoft.DeploymentManager/rollouts/ContosoRollout"
```

Perintah ini mendapatkan peluncuran bernama ContosoRollout di ContosoResourceGroup.

### Contoh 4: Dapatkan peluncuran menggunakan objek peluncuran.
```powershell
Get-AzDeploymentManagerRollout -InputObject $rolloutObject
```

Perintah ini mendapatkan peluncuran yang namanya dan ResourceGroup masing-masing cocok dengan properti Nama dan ResourceGroupName dari $rolloutObject.

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

### -InputObject
Objek peluncuran.

```yaml
Type: Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama peluncuran.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetryAttempt
Upaya coba lagi peluncuran.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: Interactive
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout

## NOTES

## RELATED LINKS
