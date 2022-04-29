---
external help file: ''
Module Name: Az.HanaOnAzure
online version: https://docs.microsoft.com/powershell/module/az.hanaonazure/get-azsapmonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HanaOnAzure/help/Get-AzSapMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HanaOnAzure/help/Get-AzSapMonitor.md
ms.openlocfilehash: b1b6ebe1d7b0572a4eb1b96d3dc0f82f306a691c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144224763"
---
# Get-AzSapMonitor

## SYNOPSIS
Mendapatkan properti monitor SAP untuk langganan, grup sumber daya, dan nama sumber daya yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzSapMonitor [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzSapMonitor -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSapMonitor -InputObject <IHanaOnAzureIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti monitor SAP untuk langganan, grup sumber daya, dan nama sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan semua monitor SAP di bawah langganan
```powershell
Get-AzSapMonitor
```

```output
Location Name              Type
-------- ----              ----
westus2  ps-sapmonitor-t01 Microsoft.HanaOnAzure/sapMonitors
westus2  ps-spamonitor-t01 Microsoft.HanaOnAzure/sapMonitors
```

Perintah ini mendapatkan monitor SAP di bawah langganan.

### Contoh 2: Mendapatkan monitor SAP berdasarkan nama
```powershell
Get-AzSapMonitor -ResourceGroupName nancyc-hn1 -Name ps-spamonitor-t01
```

```output
Location Name              Type
-------- ----              ----
westus2  ps-spamonitor-t01 Microsoft.HanaOnAzure/sapMonitors
```

Perintah ini mendapatkan monitor SAP berdasarkan nama.

### Contoh 3: Mendapatkan monitor SAP berdasarkan objek
```powershell
$sap = Get-AzSapMonitor -ResourceGroupName nancyc-hn1 -Name ps-spamonitor-t01
Get-AzSapMonitor -InputObject $sap
```

```output
Location Name              Type
-------- ----              ----
westus2  ps-spamonitor-t01 Microsoft.HanaOnAzure/sapMonitors
```

Perintah ini mendapatkan monitor SAP berdasarkan objek.

### Contoh 4: Mendapatkan monitor SAP berdasarkan alur
```powershell
@{Id='/subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/nancyc-hn1/providers/Microsoft.HanaOnAzure/sapMonitors/ps-spamonitor-t01'} | Get-AzSapMonitor
```

```output
Location Name              Type
-------- ----              ----
westus2  ps-spamonitor-t01 Microsoft.HanaOnAzure/sapMonitors
```

Perintah ini mendapatkan monitor SAP berdasarkan alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.HanaOnAzure.Models.IHanaOnAzureIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya monitor SAP.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: SapMonitorName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -SubscriptionId
ID Langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### Microsoft.Azure.PowerShell.Cmdlets.HanaOnAzure.Models.IHanaOnAzureIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HanaOnAzure.Models.Api20200207Preview.ISapMonitor

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IHanaOnAzureIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi vault yang dihapus.
  - `[OperationKind <AccessPolicyUpdateKind?>]`: Nama operasi
  - `[ProviderInstanceName <String>]`: Nama instans penyedia.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ResourceName <String>]`: Nama sumber daya identitas.
  - `[SapMonitorName <String>]`: Nama sumber daya monitor SAP.
  - `[Scope <String>]`: Cakupan penyedia sumber daya sumber daya. Sumber daya induk diperluas oleh Identitas Terkelola.
  - `[SubscriptionId <String>]`: ID Langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[VaultName <String>]`: Nama vault

## RELATED LINKS

