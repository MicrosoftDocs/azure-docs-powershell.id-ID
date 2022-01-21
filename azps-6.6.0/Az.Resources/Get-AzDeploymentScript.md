---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdeploymentscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeploymentScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeploymentScript.md
ms.openlocfilehash: a56e8be01ec36fce9de66ad76d3e280e90859790
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136342362"
---
# Get-AzDeploymentScript

## SYNOPSIS
Mendapatkan atau mencantumkan skrip penyebaran.

## SYNTAX

### ListDeploymentScript (Default)
```
Get-AzDeploymentScript [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetDeploymentScriptByName
```
Get-AzDeploymentScript [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetDeploymentScriptByResourceId
```
Get-AzDeploymentScript [-Id] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDeploymentScript** mendapatkan skrip penyebaran tunggal atau daftar skrip penyebaran.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzDeploymentScript
```

Mencantumkan skrip penyebaran dalam langganan dalam konteks pengguna saat ini.

### Contoh 2
```powershell
PS C:\> Get-AzDeploymentScript -ResourceGroupName DS-TestRg
```

Mencantumkan skrip penyebaran di grup sumber daya DS-TestRg.

### Contoh 3
```powershell
PS C:\> Get-AzDeploymentScript -Name MyDeploymentScript -ResourceGroupName DS-TestRg
```

Dapatkan skrip penyebaran dengan nama MyDeploymentScript dalam grup sumber daya DS-TestRG.

### Contoh 4
```powershell
PS C:\> Get-AzDeploymentScript -Id "/subscriptions/{subId}/resourceGroups/{rgName}/providers/Microsoft.Resources/deploymentScripts/{deploymentScriptName}"
```

Dapatkan skrip penyebaran dengan Id sumber daya yang diberikan. 

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Id sumber daya yang sepenuhnya memenuhi syarat dari skrip penyebaran.
Contoh: /subscriptions/{subId}/resourceGroups/{rgName}/providers/Microsoft.Resources/deploymentScripts/{deploymentScriptName}

```yaml
Type: String
Parameter Sets: GetDeploymentScriptByResourceId
Aliases: ResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama skrip penyebaran

```yaml
Type: String
Parameter Sets: GetDeploymentScriptByName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ListDeploymentScript
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: GetDeploymentScriptByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript

## CATATAN

## RELATED LINKS