---
external help file: Microsoft.Azure.PowerShell.Cmdlets.GuestConfiguration.dll-Help.xml
Module Name: Az.GuestConfiguration
online version: https://docs.microsoft.com/powershell/module/az.guestconfiguration/get-AzVMGuestPolicyStatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatus.md
ms.openlocfilehash: 01e48f51a84d3152031881b600051be13510c914
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145780534"
---
# Get-AzVMGuestPolicyStatus

## SYNOPSIS
Mendapatkan status kebijakan konfigurasi tamu (terperinci) untuk inisiatif jenis "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan jenis definisi "Inisiatif".

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.guestconfiguration/get-azvmguestpolicystatus) untuk informasi terbaru.

## SYNTAX

### VmScope (Default)
```
Get-AzVMGuestPolicyStatus [-ResourceGroupName] <String> [-VMName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InitiativeIdScope
```
Get-AzVMGuestPolicyStatus [-ResourceGroupName] <String> [-VMName] <String> [-InitiativeId] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InitiativeNameScope
```
Get-AzVMGuestPolicyStatus [-ResourceGroupName] <String> [-VMName] <String> [-InitiativeName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ReportIdScope
```
Get-AzVMGuestPolicyStatus [-ReportId] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzVMGuestPolicyStatus mendapatkan status kebijakan konfigurasi tamu untuk inisiatif jenis "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan jenis definisi "Inisiatif".
Cmdlet ini mendapatkan status kepatuhan VM dan alasan mengapa tidak mematuhi kebijakan individu dalam inisiatif.

## EXAMPLES

### Contoh 1
```powershell
Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
```

Dapatkan semua status kebijakan konfigurasi tamu terbaru untuk VM.
Status ini mencakup status kepatuhan VM untuk setiap kebijakan dalam semua inisiatif jenis "Konfigurasi Tamu", alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa kepatuhannya.
Hasilnya mencakup status terbaru, tidak termasuk status historis sebelumnya.

### Contoh 2
```powershell
Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af"
```

Dapatkan status kebijakan konfigurasi tamu terbaru berdasarkan Id inisiatif. Status ini mencakup status kepatuhan VM untuk setiap kebijakan dalam inisiatif, alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa kepatuhannya.
Hasilnya tidak termasuk status sebelumnya yang dihasilkan, itu hanya mencakup status terbaru untuk setiap kebijakan dalam inisiatif.

### Contoh: 3
```powershell
Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17"
```

Dapatkan status kebijakan konfigurasi tamu terbaru berdasarkan nama inisiatif.
Status ini mencakup status kepatuhan VM untuk setiap kebijakan dalam inisiatif, alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa kepatuhannya.
Hasilnya tidak termasuk status sebelumnya yang dihasilkan, itu hanya mencakup status terbaru untuk setiap kebijakan dalam inisiatif.

### Contoh 4
```powershell
Get-AzVMGuestPolicyStatus -ReportId "/subscriptions/4e6c6ed2-0bf6-41d7-9d21-a452c2cc7920/resourceGroups/MyResourceGroupName/providers/Microsoft.Compute/virtualMachines/MyVMName/providers/Microsoft.GuestConfiguration/guestConfigurationAssignments/MaximumPasswordAge/reports/c271f845-2c0a-4456-a441-e48fc332d0ac"
```

Dapatkan status kebijakan konfigurasi tamu menurut ReportId.
ReportId adalah properti ReportId yang dapat ditemukan dalam hasil Get-AzVMGuestPolicyStatus dengan nama inisiatifId atau Inisiatif (silakan lihat contoh lain)

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiativeId
Id Definisi kebijakan di mana jenis definisi adalah Inisiatif dan kategorinya adalah Konfigurasi Tamu

```yaml
Type: System.String
Parameter Sets: InitiativeIdScope
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiativeName
Nama kebijakan di mana jenis definisi adalah Inisiatif dan kategorinya adalah Konfigurasi Tamu

```yaml
Type: System.String
Parameter Sets: InitiativeNameScope
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportId
Id status kebijakan Konfigurasi Tamu.
Kebijakan di mana jenis definisi adalah Inisiatif dan kategori adalah Konfigurasi Tamu harus ditetapkan ke cakupan untuk mendapatkan status.

```yaml
Type: System.String
Parameter Sets: ReportIdScope
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: VmScope, InitiativeIdScope, InitiativeNameScope
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Nama VM.

```yaml
Type: System.String
Parameter Sets: VmScope, InitiativeIdScope, InitiativeNameScope
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.GuestConfiguration.Models.PolicyStatusDetailed
## NOTES

## RELATED LINKS
