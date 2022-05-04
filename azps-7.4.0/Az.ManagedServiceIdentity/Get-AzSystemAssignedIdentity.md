---
external help file: ''
Module Name: Az.ManagedServiceIdentity
online version: https://docs.microsoft.com/powershell/module/az.managedserviceidentity/get-azsystemassignedidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzSystemAssignedIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzSystemAssignedIdentity.md
ms.openlocfilehash: f58545ceeb39b9061232b354142a55f7067dfa4d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144734806"
---
# Get-AzSystemAssignedIdentity

## SYNOPSIS
Mendapatkan systemAssignedIdentity yang tersedia di bawah cakupan RP yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.managedserviceidentity/get-azsystemassignedidentity) untuk informasi terbaru.

## SYNTAX

```
Get-AzSystemAssignedIdentity -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan systemAssignedIdentity yang tersedia di bawah cakupan RP yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan identitas yang ditetapkan sistem yang tersedia di bawah cakupan RP yang ditentukan
```powershell
PS C:\> Get-AzSystemAssignedIdentity -Scope "/subscriptions/00000000-0000-0000-00000000000/resourcegroups/lucas-rg-test/providers/Microsoft.Web/sites/functionportal01"

Name            Location ResourceGroupName
----            -------- -----------------
ubuntu-portal01 eastus   azure-rg-test
```

Perintah ini mendapatkan identitas yang ditetapkan sistem yang tersedia di bawah cakupan RP yang ditentukan.

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

### -Cakupan
Cakupan penyedia sumber daya sumber daya.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServiceIdentity.Models.Api20181130.ISystemAssignedIdentity

## NOTES

ALIAS

## RELATED LINKS

