---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 6424B740-DBFB-490C-AEAA-EDD60952B435
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azprovideroperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Get-AzProviderOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Get-AzProviderOperation.md
ms.openlocfilehash: 61e38afcccccd6a96e92983d24442740351320ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "136039818"
---
# Get-AzProviderOperation

## SYNOPSIS
Dapatkan operasi untuk penyedia sumber daya Azure yang dapat mengamankan menggunakan Azure RBAC.

## SYNTAX

```
Get-AzProviderOperation [[-OperationSearchString] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Sumber Get-AzProviderOperation operasi yang diekspos oleh penyedia sumber daya Azure.
Operasi bisa dibuat untuk membuat peran kustom di Azure RBAC.
Perintah akan mengambil string pencarian operasi (dengan kemungkinan wildcard( ) karakter yang menentukan *detail operasi untuk ditampilkan. Gunakan Get-AzProviderOperation * untuk mendapatkan semua operasi bagi semua penyedia sumber daya Azure. Gunakan Get-AzProviderOperation Microsoft.Compute/* untuk mendapatkan semua operasi penyedia sumber daya Microsoft.Compute.

## EXAMPLES

### Contoh 1: Mendapatkan semua tindakan untuk semua penyedia
```powershell
PS C:\> Get-AzProviderOperation *
```

### Contoh 2: Mendapatkan tindakan untuk penyedia sumber daya tertentu
```powershell
PS C:\> Get-AzProviderOperation Microsoft.Insights/*
```

### Contoh 3: Mendapatkan semua tindakan yang bisa dilakukan pada mesin virtual
```powershell
PS C:\> Get-AzProviderOperation */virtualMachines/*
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -OperationSearchString
String pencarian operasi (dengan kemungkinan karakter wildcard (*))

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: "*"
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceProviderOperation

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS
