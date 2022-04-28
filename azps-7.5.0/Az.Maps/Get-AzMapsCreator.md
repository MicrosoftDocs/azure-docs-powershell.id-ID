---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/get-azmapscreator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsCreator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsCreator.md
ms.openlocfilehash: 5c6ccf4b1d6195497b44c889d54859bc4d1b5e41
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144212318"
---
# Get-AzMapsCreator

## SYNOPSIS
Dapatkan sumber daya Peta Creator.

## SYNTAX

### Daftar (Default)
```
Get-AzMapsCreator -AccountName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzMapsCreator -AccountName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMapsCreator -InputObject <IMapsIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan sumber daya Peta Creator.

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya pembuat Peta di bawah Akun Peta
```powershell
Get-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01
```

```output
Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mencantumkan Peta sumber daya Pembuat di bawah Akun Peta.

### Contoh 2: Mendapatkan sumber daya pembuat Peta
```powershell
Get-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01
```

```output
Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mendapatkan sumber daya Peta Creator.

### Contoh 3: Mendapatkan sumber daya Peta Creator berdasarkan alur
```powershell
New-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01 -Location eastus2 -StorageUnit 3 | Get-AzMapsCreator
```

```output
Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mendapatkan sumber daya Peta Creator berdasarkan alur.

## PARAMETERS

### -AccountName
Nama Akun Peta.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -Name
Nama instans Peta Creator.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: CreatorName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.ICreator

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity>: Parameter Identitas
  - `[AccountName <String>]`: Nama Akun Peta.
  - `[CreatorName <String>]`: Nama instans Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

