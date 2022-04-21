---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azsshkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzSshKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzSshKey.md
ms.openlocfilehash: 9fefd4e22c721d89e05f4cb3883015f3bb4f9932
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142717012"
---
# Update-AzSshKey

## SYNOPSIS
Memperbarui sumber daya Kunci Publik SSH.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/update-azsshkey) untuk informasi terbaru.

## SYNTAX

### DefaultParameterSet (Default)
```
Update-AzSshKey -ResourceGroupName <String> -Name <String> -PublicKey <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIDParameterSet
```
Update-AzSshKey [-ResourceId] <String> -PublicKey <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Update-AzSshKey[-InputObject] <PSSshPublicKeyResource> -PublicKey <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui sumber daya Kunci Publik SSH.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $SshKey1 = Get-AzSshKey -ResourceGroupName "testRG" -Name "sshKey1"
PS C:\> Update-AzSshKey -ResourceGroupName "testRG" -Name "sshKey2" -PublicKey $SshKey1.publickey

```

Memperbarui nilai kunci publik 'sshKey2' dengan nilai kunci publik dari 'sshKey1'

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
Objek Kunci Publik PowerShell SSH

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

### -Nama
Menentukan nama sumber daya Kunci Publik Ssh untuk didapatkan.

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

Required: True
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

### -ResourceId
ID Sumber Daya untuk Sumber Daya Kunci Publik SSH Anda.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSSshPublicKeyResource

## NOTES

## RELATED LINKS
