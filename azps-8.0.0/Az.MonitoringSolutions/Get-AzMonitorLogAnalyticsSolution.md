---
external help file: ''
Module Name: Az.MonitoringSolutions
online version: https://docs.microsoft.com/powershell/module/az.monitoringsolutions/get-azmonitorloganalyticssolution
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MonitoringSolutions/help/Get-AzMonitorLogAnalyticsSolution.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MonitoringSolutions/help/Get-AzMonitorLogAnalyticsSolution.md
ms.openlocfilehash: b2adb6512546dfa2c1490138844a19fdc69d7eb1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145558035"
---
# Get-AzMonitorLogAnalyticsSolution

## SYNOPSIS
Mengambil solusi pengguna.

## SYNTAX

### List1 (Default)
```
Get-AzMonitorLogAnalyticsSolution [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzMonitorLogAnalyticsSolution -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMonitorLogAnalyticsSolution -InputObject <IMonitoringSolutionsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzMonitorLogAnalyticsSolution -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengambil solusi pengguna.

## EXAMPLES

### Contoh 1: Mendapatkan solusi analitik log monitor berdasarkan nama
```powershell
Get-AzMonitorLogAnalyticsSolution -ResourceGroupName azureps-monitor -Name 'Containers(azureps-monitor)'
```

```output
Name                      Type                                     Location
----                      ----                                     --------
Containers(azureps-monitor) Microsoft.OperationsManagement/solutions West US 2
```

Perintah ini mendapatkan solusi analitik log monitor berdasarkan nama.

### Contoh 2: Mendapatkan solusi analitik log monitor menurut id sumber daya
```powershell
@{Id = "/subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourcegroups/azureps-manual-test/providers/Microsoft.OperationsManagement/solutions/Containers(monitoringworkspace-t01)"} | Get-AzMonitorLogAnalyticsSolution
```

```output
Name                                Type                                     Location
----                                ----                                     --------
Containers(monitoringworkspace-t01) Microsoft.OperationsManagement/solutions East US
```

Perintah ini mendapatkan solusi analitik log monitor berdasarkan id sumber daya.

### Contoh 3: Mendapatkan solusi analitik log monitor berdasarkan objek
```powershell
$monitor = New-AzMonitorLogAnalyticsSolution -ResourceGroupName azureps-monitor -Type "Microsoft.OperationsManagement/solutions" -Location "West US 2" -WorkspaceResourceId workspaceResourceId
Get-AzMonitorLogAnalyticsSolution -InputObject $monitor
```

```output
Name                      Type                                     Location
----                      ----                                     --------
Containers(azureps-monitor) Microsoft.OperationsManagement/solutions West US 2
```

Perintah ini mendapatkan solusi analitik log monitor berdasarkan objek.

### Contoh 4: Mendapatkan semua solusi analitik log monitor di bawah grup sumber daya
```powershell
Get-AzMonitorLogAnalyticsSolution -ResourceGroupName azureps-monitor
```

```output
Name                      Type                                     Location
----                      ----                                     --------
Containers(azureps-monitor) Microsoft.OperationsManagement/solutions West US 2
```

Perintah ini mendapatkan semua solusi analitik log monitor di bawah grup sumber daya.

### Contoh 5: Mendapatkan semua solusi analitik log monitor di bawah langganan
```powershell
Get-AzMonitorLogAnalyticsSolution 
```

```output
Name                                Type                                     Location
----                                ----                                     --------
Containers(monitoringworkspace-t01) Microsoft.OperationsManagement/solutions East US
Containers(azureps-monitor)           Microsoft.OperationsManagement/solutions West US 2
```

Perintah ini mendapatkan semua solusi analitik log monitor di bawah langganan.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.MonitoringSolutions.Models.IMonitoringSolutionsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Solusi Pengguna.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: SolutionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang akan didapatkan.
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

### Microsoft.Azure.PowerShell.Cmdlets.MonitoringSolutions.Models.IMonitoringSolutionsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MonitoringSolutions.Models.Api20151101Preview.ISolution

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMonitoringSolutionsIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ManagementAssociationName <String>]`: Nama Manajemen PenggunaAssosiasi.
  - `[ManagementConfigurationName <String>]`: Nama Konfigurasi Manajemen Pengguna.
  - `[ProviderName <String>]`: Nama penyedia untuk sumber daya induk.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang akan didapatkan. Nama ini tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama sumber daya induk.
  - `[ResourceType <String>]`: Jenis sumber daya untuk sumber daya induk
  - `[SolutionName <String>]`: Nama Solusi Pengguna.
  - `[SubscriptionId <String>]`: Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

