---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.addomainservices/get-azaddomainservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/Get-AzADDomainService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/Get-AzADDomainService.md
ms.openlocfilehash: a50665fbf29b6836f5ec24f9f6439549abbe71e0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144226012"
---
# Get-AzADDomainService

## SYNOPSIS
Operasi Dapatkan Layanan Domain mengambil representasi json dari Layanan Domain.

## SYNTAX

### Daftar (Default)
```
Get-AzADDomainService [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzADDomainService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzADDomainService -InputObject <IAdDomainServicesIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzADDomainService -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Operasi Dapatkan Layanan Domain mengambil representasi json dari Layanan Domain.

## EXAMPLES

### Contoh 1: Dapatkan Semua ADDomainService Secara default
```powershell
Get-AzADDomainService
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Dapatkan Semua ADDomainService Secara default

### Contoh 2: Dapatkan ADDomainService Menurut ResourceGroup dan nama
```powershell
Get-AzADDomainService -Name youriADdomain -ResourceGroupName youriADdomain
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Mendapatkan ADDomainService Menurut ResourceGroup dan nama

### Contoh 3: Dapatkan semua ADDomainService Menurut ResourceGroup
```powershell
Get-AzADDomainService -ResourceGroupName youriADdomain
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Mendapatkan semua ADDomainService Menurut ResourceGroup

### Contoh 4: Dapatkan ADDomainService dengan InputObject
```powershell
$getAzAddomain = Get-AzADDomainService -Name youriADdomain -ResourceGroupName youriADdomain
Get-AzADDomainService -InputObject $getAzAddomain
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Mendapatkan ADDomainService dengan InputObject

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.IAdDomainServicesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama layanan domain.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DomainServiceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya dalam langganan pengguna.
Nama tidak peka huruf besar/kecil.

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
Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.IAdDomainServicesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.IDomainService

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAdDomainServicesIdentity>: Parameter Identitas
  - `[DomainServiceName <String>]`: Nama layanan domain.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya dalam langganan pengguna. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

