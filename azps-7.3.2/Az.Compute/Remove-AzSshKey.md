---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azsshkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzSshKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzSshKey.md
ms.openlocfilehash: 5cd10c395b61b82c6259f5e545a2ea8c4ddf479d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142347443"
---
# Remove-AzSshKey

## SYNOPSIS
Hapus sumber daya Kunci Publik SSH.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/remove-azsshkey) untuk informasi terbaru.

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
Hapus sumber daya Kunci Publik SSH.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzSshKey -ResourceGroupName "testRG" -Name "sshKey1"
```

Menghapus sumber daya Kunci Publik Ssh bernama "sshKey1" dalam Grup Sumber Daya "testRG"

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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSOperationStatusResponse

## CATATAN

## RELATED LINKS
