---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/get-azmapscreator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsCreator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsCreator.md
ms.openlocfilehash: f014741b21a15b9e8df6b3361d61bb141961298c
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136733282"
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

### Contoh 1: List all Peta Creator resources under a Peta Account
```powershell
PS C:\> Get-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mencantumkan Peta Creator di bawah Peta Anda.

### Contoh 2: Dapatkan sumber daya Peta Creator
```powershell
PS C:\> Get-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mendapatkan sumber Peta Creator.

### Contoh 3: Get a Peta Creator resource by pipeline
```powershell
PS C:\> New-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01 -Location eastus2 -StorageUnit 3 | Get-AzMapsCreator

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini mendapatkan sumber Peta Creator menurut saluran.

## PARAMETERS

### -Nama Akun
Nama akun Peta Anda.

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
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.ICreator

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama Peta Tersebut.
  - `[CreatorName <String>]`: Nama Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

