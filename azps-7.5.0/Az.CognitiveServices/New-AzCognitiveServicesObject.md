---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CognitiveServices.dll-Help.xml
Module Name: Az.CognitiveServices
online version: https://docs.microsoft.com/powershell/module/az.cognitiveservices/new-azcognitiveservicesobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/New-AzCognitiveServicesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/New-AzCognitiveServicesObject.md
ms.openlocfilehash: f6b04f52380b99b6a4e5e5d2b387ca711edf69dd
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145736920"
---
# New-AzCognitiveServicesObject

## SYNOPSIS
Membuat Objek Cognitive Services

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cognitiveservices/new-azcognitiveservicesobject) untuk informasi terbaru.

## SYNTAX

```
New-AzCognitiveServicesObject [-Type] <CognitiveServicesObjectType> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Objek Cognitive Services

## EXAMPLES

### Contoh 1
```powershell
New-AzCognitiveServicesObject -Type DeploymentProperties
```

Membuat Objek Cognitive Services DeploymentProperties

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

### -Type
Jenis Objek Cognitive Services.

```yaml
Type: Microsoft.Azure.Commands.Management.CognitiveServices.CognitiveServicesObjectType
Parameter Sets: (All)
Aliases:
Accepted values: DeploymentProperties, CommitmentPlanProperties

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Management.CognitiveServices.Models.DeploymentProperties

### Microsoft.Azure.Management.CognitiveServices.Models.CommitmentPlanProperties

## NOTES

## RELATED LINKS
