---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azsshkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzSshKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzSshKey.md
ms.openlocfilehash: f6195c5308ca5c2184504960deaaed9ef07acbc6
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499726"
---
# Remove-AzSshKey

## SYNOPSIS
Menghapus sumber daya Kunci Umum SSH.

## SYNTAX

### DefaultParameterSet (Default)
```
Remove-AzSshKey -ResourceGroupName <String> -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceIDParameterSet
```
Remove-AzSshKey [-ResourceId] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Remove-AzSshKey [-InputObject] <PSSshPublicKeyResource> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus sumber daya Kunci Umum SSH.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzSshKey -ResourceGroupName "testRG" -Name "sshKey1"
```

Menghapus sumber daya Kunci Umum Ssh bernama "sshKey1" di Grup Sumber Daya "testRG"

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
Objek Kunci Umum PowerShell SSH

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSSshPublicKeyResource
Parameter Sets: InputObjectParameterSet
Aliases: SshKey

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Menentukan nama sumber daya Kunci Umum Ssh yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sshkeyName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceId
ID Sumber Daya untuk Sumber Daya Kunci Umum SSH Anda.

```yaml
Type: System.String
Parameter Sets: ResourceIDParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSOperationStatusResponse

## NOTES

## RELATED LINKS
