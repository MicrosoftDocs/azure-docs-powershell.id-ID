---
external help file: ''
Module Name: Az.ManagedServiceIdentity
online version: https://docs.microsoft.com/powershell/module/az.managedserviceidentity/get-azsystemassignedidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzSystemAssignedIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzSystemAssignedIdentity.md
ms.openlocfilehash: 7cfce5781378db145067a5957255c1f91c60532f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141835984"
---
# Get-AzSystemAssignedIdentity

## SYNOPSIS
Mendapatkan systemAssignedIdentity yang tersedia di bawah lingkup RP yang ditentukan.

## SYNTAX

```
Get-AzSystemAssignedIdentity -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan systemAssignedIdentity yang tersedia di bawah lingkup RP yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan identitas sistem yang ditetapkan yang tersedia di bawah lingkup RP yang ditentukan
```powershell
PS C:\> Get-AzSystemAssignedIdentity -Scope "/subscriptions/00000000-0000-0000-00000000000/resourcegroups/lucas-rg-test/providers/Microsoft.Web/sites/functionportal01"

Name            Location ResourceGroupName
----            -------- -----------------
ubuntu-portal01 eastus   azure-rg-test
```

Perintah ini mendapatkan identitas sistem yang ditetapkan yang tersedia di bawah lingkup RP yang ditentukan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup penyedia sumber daya sumber daya.
Sumber daya induk diperluas oleh Identitas Terkelola.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServiceIdentity.Models.Api20181130.ISystemAssignedIdentity

## CATATAN

ALIAS

## RELATED LINKS

