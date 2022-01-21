---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azsshkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzSshKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzSshKey.md
ms.openlocfilehash: 23c7a792d22e74f3e3c123c0352153894ecf3790
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136557085"
---
# Get-AzSshKey

## SYNOPSIS
Mendapatkan properti sumber daya KUNCI Publik LINUX.

## SYNTAX

### DefaultParameterSet (Default)
```
Get-AzSshKey [-ResourceGroupName <String>] [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceIDParameterSet
```
Get-AzSshKey [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti sumber daya KUNCI Publik LINUX.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSshKey -ResourceGroupName "testRG" -Name "SshKey1"
```

Contoh ini mengambil sumber daya Kunci Publik Linux tertentu.

### Contoh 2
```powershell
PS C:\> Get-AzSshKey -ResourceGroupName "testRG"
```

Contoh ini mengambil daftar sumber daya Kunci Publik Resources yang berada di Grup Sumber Daya: "testRG"

### Contoh 3
```powershell
PS C:\> Get-AzSshKey 
```

Contoh ini mengambil semua sumber daya Kunci Publik Bisnis di langganan. 

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

### -Nama
Menentukan nama Sumber Daya Kunci Publik Filem yang akan dapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sshkeyName

Required: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceId
ID Sumber Daya untuk Sumber Daya Kunci Publik BISNIS ANDA.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSSshPublicKeyResource

## CATATAN

## RELATED LINKS
