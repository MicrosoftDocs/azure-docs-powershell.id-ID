---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.ManagedServices/new-AzManagedServicesEligibleApproverObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleApproverObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleApproverObject.md
ms.openlocfilehash: e004bc825edcdd420a39ff81e6af5e6552ae3f4d
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145691344"
---
# New-AzManagedServicesEligibleApproverObject

## SYNOPSIS
Buat objek dalam memori untuk EligibleApprover.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.managedservices/new-azmanagedserviceseligibleapproverobject) untuk informasi terbaru.

## SYNTAX

```
New-AzManagedServicesEligibleApproverObject -PrincipalId <String> [-PrincipalIdDisplayName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk EligibleApprover.

## EXAMPLES

### Contoh 1: Membuat objek pemberi izin otorisasi yang memenuhi syarat Azure Lighthouse
```powershell
New-AzManagedServicesEligibleApproverObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Approvers group"
```

```output
PrincipalId                          PrincipalIdDisplayName
-----------                          ----------------------
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Approvers group
```

Membuat objek pemberi izin otorisasi yang memenuhi syarat Azure Lighthouse.

## PARAMETERS

### -PrincipalId
Pengidentifikasi perwakilan Azure Active Directory.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalIdDisplayName
Nama tampilan prinsipal Azure Active Directory.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.EligibleApprover

## NOTES

ALIAS

## RELATED LINKS

