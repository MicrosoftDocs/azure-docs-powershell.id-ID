---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/get-azproviderhubnotificationregistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Get-AzProviderHubNotificationRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Get-AzProviderHubNotificationRegistration.md
ms.openlocfilehash: bf7686e2114328a5bf0c09bae91aff364175ec92
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145657048"
---
# Get-AzProviderHubNotificationRegistration

## SYNOPSIS
Mendapatkan detail pendaftaran pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.providerhub/get-azproviderhubnotificationregistration) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzProviderHubNotificationRegistration -ProviderNamespace <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzProviderHubNotificationRegistration -Name <String> -ProviderNamespace <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzProviderHubNotificationRegistration -InputObject <IProviderHubIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail pendaftaran pemberitahuan.

## EXAMPLES

### Contoh 1: Cantumkan semua pendaftaran pemberitahuan menurut ProviderNamespace.
```powershell
Get-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso"
```

```output
Name
----
notificationRegistrationTest1
notificationRegistrationTest2
```

Cantumkan semua pendaftaran pemberitahuan di namespace layanan penyedia.

### Contoh 2: Dapatkan pendaftaran pemberitahuan berdasarkan nama.
```powershell
Get-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso" -Name "notificationRegistrationTest"
```

```output
Name
----
notificationRegistrationTest
```

Dapatkan pendaftaran pemberitahuan berdasarkan nama.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Pendaftaran pemberitahuan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: NotificationRegistrationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderNamespace
Nama penyedia sumber daya yang dihosting dalam ProviderHub.

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

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.INotificationRegistration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IProviderHubIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[NestedResourceTypeFirst <String>]`: Jenis sumber daya anak pertama.
  - `[NestedResourceTypeSecond <String>]`: Jenis sumber daya anak kedua.
  - `[NestedResourceTypeThird <String>]`: Jenis sumber daya anak ketiga.
  - `[NotificationRegistrationName <String>]`: Pendaftaran pemberitahuan.
  - `[ProviderNamespace <String>]`: Nama penyedia sumber daya yang dihosting dalam ProviderHub.
  - `[ResourceType <String>]`: Jenis sumber daya.
  - `[RolloutName <String>]`: Nama peluncuran.
  - `[Sku <String>]`: SKU.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

