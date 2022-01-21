---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/get-azmapsaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsAccount.md
ms.openlocfilehash: a2a9be89d99aa9d9018d8d3d3167ede13eab5abe
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136387472"
---
# Get-AzMapsAccount

## SYNOPSIS
Dapatkan akun Peta.

## SYNTAX

### Daftar1 (Default)
```
Get-AzMapsAccount [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzMapsAccount -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMapsAccount -InputObject <IMapsIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzMapsAccount -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan akun Peta.

## EXAMPLES

### Contoh 1: List all Peta Accounts under a subscription
```powershell
PS C:\> Get-AzMapsAccount

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount01 Microsoft.Maps/accounts Gen1
```

Perintah ini mencantumkan semua Peta Akun di bawah langganan.

### Contoh 2: List all Peta Accounts under a resource group
```powershell
PS C:\> Get-AzMapsAccount -ResourceGroupName azure-rg-test

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount01 Microsoft.Maps/accounts Gen1
```

Perintah ini mencantumkan semua Peta Akun di bawah grup sumber daya.

### Contoh 3: Dapatkan Peta Baru
```powershell
PS C:\> Get-AzMapsAccount -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount01

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount01 Microsoft.Maps/accounts Gen1
```

Perintah ini akan mendapatkan Peta Akun.

### Contoh 4: Get a Peta Account by pipeline
```powershell
PS C:\> New-AzMapsAccount -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount01 -SkuName S0 -Location eastus | Get-AzMapsAccount

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount01 Microsoft.Maps/accounts Gen1
```

Perintah ini memiliki saluran Peta saluran.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Maps.Models.IMapsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama akun Peta.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.IMapsAccount

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama akun Peta Anda.
  - `[CreatorName <String>]`: Nama Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

