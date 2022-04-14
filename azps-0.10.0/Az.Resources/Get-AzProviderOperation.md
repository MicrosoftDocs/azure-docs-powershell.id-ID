---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 6424B740-DBFB-490C-AEAA-EDD60952B435
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-Azprovideroperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzProviderOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzProviderOperation.md
ms.openlocfilehash: 21e1af2a36478f2e0b8e470660d0fbe2539a396e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142130615"
---
# Get-AzProviderOperation

## SYNOPSIS
Mendapatkan operasi untuk penyedia sumber daya Azure yang dapat disempurnakan menggunakan Azure RBAC.

## SYNTAX

```
Get-AzProviderOperation [[-OperationSearchString] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Get-AzProviderOperation mendapatkan operasi yang diekspos oleh penyedia sumber daya Azure.
Operasi dapat dibuat untuk membuat peran kustom di Azure RBAC.
Perintah diambil sebagai input string pencarian operasi (dengan karakter wildcard(*) yang mungkin, yang menentukan detail operasi untuk ditampilkan. Gunakan Get-AzProviderOperation * untuk mendapatkan semua operasi untuk semua penyedia sumber daya Azure. Gunakan Get-AzProviderOperation Microsoft.Compute/* untuk mendapatkan semua operasi penyedia sumber daya Microsoft.Compute.

## EXAMPLES

### Dapatkan semua tindakan untuk semua penyedia
```
PS C:\> Get-AzProviderOperation *
```

### Mendapatkan tindakan untuk penyedia sumber daya tertentu
```
PS C:\> Get-AzProviderOperation Microsoft.Insights/*
```

### Dapatkan semua tindakan yang dapat dilakukan di mesin virtual
```
PS C:\> Get-AzProviderOperation */virtualMachines/*
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationSearchString
String pencarian operasi (dengan karakter wildcard (*) yang memungkinkan)

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Parameter: OperationSearchString (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceProviderOperation

## CATATAN
Kata kunci: azure, Az, lengan, sumber daya, manajemen, manajer, sumber daya, grup, Template, penyebaran

## RELATED LINKS
