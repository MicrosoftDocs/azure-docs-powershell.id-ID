---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azsshkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzSshKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzSshKey.md
ms.openlocfilehash: c8861e11c96f970ca38e8aa8aacfb5b9df6440f1
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136720291"
---
# New-AzSshKey

## SYNOPSIS
Membuat sumber daya Kunci Publik LINUX.

## SYNTAX

```
New-AzSshKey -ResourceGroupName <String> -Name <String> [-PublicKey <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat sumber daya Kunci Publik LINUX.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSshKey -ResourceGroupName "testRG" -Name "sshkey1" -PublicKey $publicKey
```

Membuat sumber daya Kunci LINUX dengan kunci publik yang disediakan. 

### Contoh 2
```powershell
PS C:\> New-AzSshKey -ResourceGroupName "testRG" -Name "sshkey1" 
```

Membuat sumber daya Kunci LINUX tanpa menyediakan kunci publik. Pasangan kunci akan dihasilkan dan disimpan dalam ~~ dan disimpan dalam \. ~ . Kunci publik juga akan disimpan dalam sumber daya KunciBUNGA.

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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PublicKey
Nilai Kunci Publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSSshPublicKeyResource

## CATATAN

## RELATED LINKS
