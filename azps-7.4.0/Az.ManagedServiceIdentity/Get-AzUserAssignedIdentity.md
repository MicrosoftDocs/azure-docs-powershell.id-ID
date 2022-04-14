---
external help file: ''
Module Name: Az.ManagedServiceIdentity
online version: https://docs.microsoft.com/powershell/module/az.managedserviceidentity/get-azuserassignedidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzUserAssignedIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServiceIdentity/help/Get-AzUserAssignedIdentity.md
ms.openlocfilehash: 768b20cdaa3e446506d87fc1a880d69d0ebf5fa7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177647"
---
# Get-AzUserAssignedIdentity

## SYNOPSIS
Dapatkan identitasnya.

## SYNTAX

### Daftar (Default)
```
Get-AzUserAssignedIdentity [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzUserAssignedIdentity -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzUserAssignedIdentity -InputObject <IManagedServiceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzUserAssignedIdentity -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan identitasnya.

## EXAMPLES

### Contoh 1: Mencantumkan identitas yang ditetapkan pengguna di bawah langganan
```powershell
PS C:\>  Get-AzUserAssignedIdentity

Location      Name                                ResourceGroupName
--------      ----                                -----------------
eastus        AzSecPackAutoConfigUA-eastus        AzSecPackAutoConfigRG
eastus        uai-pwsh01                          azure-rg-test
eastus2       AzSecPackAutoConfigUA-eastus2       AzSecPackAutoConfigRG
```

Perintah ini mencantumkan identitas pengguna yang ditetapkan di bawah langganan.

### Contoh 2: Cantumkan identitas yang ditetapkan pengguna di bawah grup sumber daya
```powershell
PS C:\> Get-AzUserAssignedIdentity -ResourceGroupName azure-rg-test

Location Name       ResourceGroupName
-------- ----       -----------------
eastus   uai-pwsh01 azure-rg-test
```

Perintah ini mencantumkan identitas yang ditetapkan pengguna di bawah grup sumber daya.

### Contoh 3: Mendapatkan identitas yang ditetapkan pengguna
```powershell
PS C:\> Get-AzUserAssignedIdentity -ResourceGroupName azure-rg-test -Name uai-pwsh01

Location Name       ResourceGroupName
-------- ----       -----------------
eastus   uai-pwsh01 azure-rg-test
```

Perintah ini mendapatkan identitas yang ditetapkan pengguna.

### Contoh 4: Mendapatkan identitas yang ditetapkan pengguna menurut pipeline
```powershell
PS C:\> New-AzUserAssignedIdentity -ResourceGroupName azure-rg-test -Name uai-pwsh01 -Location eastus
 | Get-AzUserAssignedIdentity

Location Name       ResourceGroupName
-------- ----       -----------------
eastus   uai-pwsh01 azure-rg-test
```

Perintah ini mendapatkan identitas pengguna yang ditetapkan menurut saluran.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServiceIdentity.Models.IManagedServiceIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya identitas.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya tempat identitas berada.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan tempat identitas berada.

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServiceIdentity.Models.IManagedServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServiceIdentity.Models.Api20181130.IIdentity

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IManagedServiceIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama Grup Sumber Daya tempat identitas berada.
  - `[ResourceName <String>]`: Nama sumber daya identitas.
  - `[Scope <String>]`: Lingkup penyedia sumber daya sumber daya. Sumber daya induk diperluas oleh Identitas Terkelola.
  - `[SubscriptionId <String>]`: Id Langganan tempat identitas berada.

## RELATED LINKS

