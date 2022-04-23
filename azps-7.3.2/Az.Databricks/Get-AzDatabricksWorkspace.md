---
external help file: ''
Module Name: Az.Databricks
online version: https://docs.microsoft.com/powershell/module/az.databricks/get-azdatabricksworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksWorkspace.md
ms.openlocfilehash: a270c46e00af731ad9b7916a09cef327875047eb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143184923"
---
# Get-AzDatabricksWorkspace

## SYNOPSIS
Mendapatkan ruang kerja.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databricks/get-azdatabricksworkspace) untuk informasi terbaru.

## SYNTAX

### List1 (Default)
```
Get-AzDatabricksWorkspace [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzDatabricksWorkspace -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDatabricksWorkspace -InputObject <IDatabricksIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzDatabricksWorkspace -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan ruang kerja.

## EXAMPLES

### Contoh 1: Mendapatkan ruang kerja Databricks dengan nama
```powershell
PS C:\> Get-AzDatabricksWorkspace -Name databricks-test -ResourceGroupName databricks-rg-rqb2yo

Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Perintah ini mendapatkan ruang kerja Databricks dalam grup sumber daya.

### Contoh 2: Mencantumkan semua ruang kerja Databricks dalam langganan
```powershell
PS C:\> Get-AzDatabricksWorkspace

ame                ResourceGroupName    Location       Managed Resource Group ID
----                -----------------    --------       -------------------------
workspace1xfmkv     databricks-rg-13vdtb eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace1xfmkv-s41tghmif7cle
workspace-pwsh01    databricks-rg-13vdtb eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace-pwsh01-sdenr3zv5tyh9
workspacewqpya1     databricks-rg-13vdtb eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspacewqpya1-mhsacdo0pb15e
workspace2b8i61     databricks-rg-1jxsia eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace2b8i61-xmkef5d6j7483
workspace2rzshd     databricks-rg-1jxsia eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace2rzshd-oql04khm89rx3
```

Perintah ini mencantumkan semua ruang kerja Databricks dalam langganan.

### Contoh 3: Mencantumkan semua ruang kerja Databricks dalam grup sumber daya
```powershell
PS C:\> Get-AzDatabricksWorkspace -ResourceGroupName databricks-rg-rqb2yo

Name            ResourceGroupName    Location       Managed Resource Group ID
----            -----------------    --------       -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
workspacefnw9gd databricks-rg-rqb2yo eastus         /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspacefnw9gd-ik7n2yfmzhuxq
workspace3o1d60 databricks-rg-rqb2yo East US 2 EUAP /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3o1d60-gancyx6kjmw71
```

Perintah ini mencantumkan semua ruang kerja Databricks dalam grup sumber daya.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama ruang kerja.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: WorkspaceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20210401Preview.IWorkspace

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDatabricksIdentity>: Parameter Identitas
  - `[GroupId <String>]`: Nama sumber daya tautan privat
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PeeringName <String>]`: Nama ruang kerja vNet peering.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja.

## RELATED LINKS

