---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 6424B740-DBFB-490C-AEAA-EDD60952B435
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azprovideroperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzProviderOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzProviderOperation.md
ms.openlocfilehash: 81ad137cc3e198b864ae00330bcff10cd05b24c0
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145642778"
---
# Get-AzProviderOperation

## SYNOPSIS
Mendapatkan operasi untuk penyedia sumber daya Azure yang dapat diamankan menggunakan Azure RBAC.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azprovideroperation) untuk informasi terbaru.

## SYNTAX

```
Get-AzProviderOperation [[-OperationSearchString] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Get-AzProviderOperation mendapatkan operasi yang diekspos oleh penyedia sumber daya Azure.
Operasi dapat dibuat untuk membuat peran kustom di Azure RBAC.
Perintah mengambil sebagai input string pencarian operasi (dengan kemungkinan karakter wildcard(*) yang menentukan detail operasi yang akan ditampilkan. Gunakan Get-AzProviderOperation * untuk mendapatkan semua operasi untuk semua penyedia sumber daya Azure. Gunakan Get-AzProviderOperation Microsoft.Compute/* untuk mendapatkan semua operasi penyedia sumber daya Microsoft.Compute.

## EXAMPLES

### Contoh 1: Dapatkan semua tindakan untuk semua penyedia
```powershell
Get-AzProviderOperation *
```

### Contoh 2: Mendapatkan tindakan untuk penyedia sumber daya tertentu
```powershell
Get-AzProviderOperation Microsoft.Insights/*
```

### Contoh 3: Dapatkan semua tindakan yang dapat dilakukan pada komputer virtual
```powershell
Get-AzProviderOperation */virtualMachines/*
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
String pencarian operasi (dengan kemungkinan karakter kartubebas (*) )

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceProviderOperation

## NOTES
Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, sumber daya, grup, templat, penyebaran

## RELATED LINKS
