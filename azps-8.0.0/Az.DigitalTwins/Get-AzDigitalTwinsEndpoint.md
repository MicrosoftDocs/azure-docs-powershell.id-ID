---
external help file: ''
Module Name: Az.DigitalTwins
online version: https://docs.microsoft.com/powershell/module/az.digitaltwins/get-azdigitaltwinsendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/Get-AzDigitalTwinsEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/Get-AzDigitalTwinsEndpoint.md
ms.openlocfilehash: b920b71c8860a8a7ede4257398c797a184574d78
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146618662"
---
# Get-AzDigitalTwinsEndpoint

## SYNOPSIS
Dapatkan Titik Akhir DigitalTwinsInstances.

## SYNTAX

### Daftar (Default)
```
Get-AzDigitalTwinsEndpoint -ResourceGroupName <String> -ResourceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDigitalTwinsEndpoint -EndpointName <String> -ResourceGroupName <String> -ResourceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDigitalTwinsEndpoint -InputObject <IDigitalTwinsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Titik Akhir DigitalTwinsInstances.

## EXAMPLES

### Contoh 1: Daftar AzDigitalTwinsEndpoint di ResourceGroup
```powershell
Get-AzDigitalTwinsEndpoint -ResourceGroupName youritemp -ResourceName youriDigitalTwinsTest
```

```output
Name                     Type
----                     ----
youriDigitalTwinEndpoint Microsoft.DigitalTwins/digitalTwinsInstances/endpoints
```

Mencantumkan semua AzDigitalTwinsEndpoints menurut ResourceGroupName

### Contoh 2: Dapatkan AzDigitalTwinsEndpoint by EndpointName
```powershell
Get-AzDigitalTwinsEndpoint -EndpointName youriDigitalTwinEndpoint -ResourceGroupName youritemp -ResourceName youriDigitalTwinsTest
```

```output
Name                     Type
----                     ----
youriDigitalTwinEndpoint Microsoft.DigitalTwins/digitalTwinsInstances/endpoints
```

Dapatkan AzDigitalTwinsEndpoint by EndpointName di ResourceGroup

### Contoh 3: Dapatkan Objek AzDigitalTwinsEndpoint oleh 'AzDigitalTwinsEndpoint'
```powershell
$GetAzDigitalTwinsEndpoint = Get-AzDigitalTwinsEndpoint -EndpointName youriDigitalTwinEndpoint -ResourceGroupName youritemp -ResourceName youriDigitalTwinsTest
Get-AzDigitalTwinsEndpoint -InputObject $GetAzDigitalTwinsEndpoint
```

```output
Name                     Type
----                     ----
youriDigitalTwinEndpoint Microsoft.DigitalTwins/digitalTwinsInstances/endpoints
```

Dapatkan Objek AzDigitalTwinsEndpoint by 'AzDigitalTwinsEndpoint'

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

### -EndpointName
Nama Sumber Daya Titik Akhir.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DigitalTwins.Models.IDigitalTwinsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi DigitalTwinsInstance.

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

### -ResourceName
Nama DigitalTwinsInstance.

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
Pengidentifikasi langganan.

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

### Microsoft.Azure.PowerShell.Cmdlets.DigitalTwins.Models.IDigitalTwinsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DigitalTwins.Models.Api20201031.IDigitalTwinsEndpointResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IDigitalTwinsIdentity>`: Parameter Identitas
  - `[EndpointName <String>]`: Nama Sumber Daya Titik Akhir.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi DigitalTwinsInstance.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi DigitalTwinsInstance.
  - `[ResourceName <String>]`: Nama DigitalTwinsInstance.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan.

## RELATED LINKS

