---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/get-azwvdscalingplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/Get-AzWvdScalingPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/Get-AzWvdScalingPlan.md
ms.openlocfilehash: 71db3d1f091ca79726b0b9977a5d2de2f3ff3c29
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140138679"
---
# Get-AzWvdScalingPlan

## SYNOPSIS
Dapatkan rencana penskalaan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.desktopvirtualization/get-azwvdscalingplan) untuk informasi terkini.

## SYNTAX

### Daftar1 (Default)
```
Get-AzWvdScalingPlan [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzWvdScalingPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzWvdScalingPlan -InputObject <IDesktopVirtualizationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzWvdScalingPlan -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar2
```
Get-AzWvdScalingPlan -HostPoolName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan rencana penskalaan.

## EXAMPLES

### Contoh 1: Dapatkan Windows Skala Desktop Virtual menurut nama
```powershell
PS C:\> Get-AzWvdScalingPlan -ResourceGroupName ResourceGroupName -Name scalingPlan1

Location      Name             Type
--------      ----             ----
westcentralus scalingPlan1     Microsoft.DesktopVirtualization/scalingplans
```

Perintah ini mendapatkan Windows Skala Desktop Virtual dalam Grup Sumber Daya.

### Contoh 2: Daftar Windows Skala Desktop Virtual
```powershell
PS C:\> Get-AzWvdScalingPlan -ResourceGroupName ResourceGroupName

Location      Name             Type
--------      ----             ----
westcentralus scalingPlan1     Microsoft.DesktopVirtualization/scalingplans
westcentralus scalingPlan2     Microsoft.DesktopVirtualization/scalingplans
```

Perintah ini mencantumkan semua Windows Skala Desktop Virtual dalam Grup Sumber Daya.

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

### -HostPoolName
Nama kumpulan host dalam grup sumber daya yang ditentukan

```yaml
Type: System.String
Parameter Sets: List2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.IDesktopVirtualizationIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama rencana skala.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ScalingPlanName

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
Parameter Sets: Get, List, List2
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
Parameter Sets: Get, List, List1, List2
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

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.IDesktopVirtualizationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingPlan

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDesktopVirtualizationIdentity>: Parameter Identitas
  - `[ApplicationGroupName <String>]`: Nama grup aplikasi
  - `[ApplicationName <String>]`: Nama aplikasi di dalam grup aplikasi yang ditentukan
  - `[DesktopName <String>]`: Nama desktop dalam grup desktop yang ditentukan
  - `[HostPoolName <String>]`: Nama host pool dalam grup sumber daya yang ditentukan
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MsixPackageFullName <String>]`: Nama lengkap paket versi tertentu dari paket MSIX di dalam hostpool tertentu
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ScalingPlanName <String>]`: Nama rencana penskalaan.
  - `[SessionHostName <String>]`: Nama tuan rumah sesi dalam host pool yang ditentukan
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[UserSessionId <String>]`: Nama sesi pengguna dalam sesi host yang ditentukan
  - `[WorkspaceName <String>]`: Nama ruang kerja

## RELATED LINKS

