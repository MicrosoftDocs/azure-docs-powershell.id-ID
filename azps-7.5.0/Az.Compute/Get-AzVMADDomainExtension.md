---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 49D17667-35C3-4A79-A0C8-C197DAA5CD90
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmaddomainextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMADDomainExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMADDomainExtension.md
ms.openlocfilehash: a178fcdc3c4dbba7501d29a8e59fa27523bf61d9
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145974361"
---
# Get-AzVMADDomainExtension

## SYNOPSIS
Mendapatkan informasi tentang ekstensi domain AD.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/get-azvmaddomainextension) untuk informasi terbaru.

## SYNTAX

```
Get-AzVMADDomainExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String> [-Status]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMADDomainExtension** mendapatkan informasi tentang ekstensi domain Azure Active Directory (AD) yang ditentukan.

## EXAMPLES

### Contoh 1

Mendapatkan informasi tentang ekstensi domain AD. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Get-AzVMADDomainExtension -Name 'AgentPool01' -ResourceGroupName myresourcegroup -VMName 'VM01'
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
Menentukan nama ekstensi domain.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Menunjukkan bahwa cmdlet ini mendapatkan tampilan instans ekstensi domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.VirtualMachineADDomainExtensionContext

## NOTES

## RELATED LINKS

[Set-AzVMADDomainExtension](./Set-AzVMADDomainExtension.md)


