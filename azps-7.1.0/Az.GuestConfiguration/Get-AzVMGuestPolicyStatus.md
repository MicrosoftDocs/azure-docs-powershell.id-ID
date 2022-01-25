---
external help file: Microsoft.Azure.PowerShell.Cmdlets.GuestConfiguration.dll-Help.xml
Module Name: Az.GuestConfiguration
online version: https://docs.microsoft.com/powershell/module/az.guestconfiguration/get-AzVMGuestPolicyStatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatus.md
ms.openlocfilehash: 95d3d581119d7306ddcc617e3517e00d6de79e82
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136740423"
---
# Get-AzVMGuestPolicyStatus

## SYNOPSIS
Mendapatkan status kebijakan konfigurasi tamu (mendetail) untuk inisiatif tipe "Konfigurasi Tamu" yang ditetapkan pada VM.
Inisiatif adalah kebijakan tipe definisi "Inisiatif".

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
Cmdlet Get-AzVMGuestPolicyStatus baru mendapatkan status kebijakan konfigurasi tamu untuk inisiatif tipe "Konfigurasi Tamu" yang ditetapkan pada VM.
Inisiatif adalah kebijakan tipe definisi "Inisiatif".
Cmdlet ini memperoleh status kepatuhan VM dan alasannya tidak mematuhi kebijakan individual dalam inisiatif tersebut.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
```

Dapatkan semua status kebijakan konfigurasi tamu terbaru untuk VM.
Status ini mencakup status kepatuhan VM untuk setiap kebijakan dalam semua inisiatif mengetikkan "Konfigurasi Tamu", alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa untuk kepatuhan.
Hasilnya menyertakan status terbaru, tidak menyertakan status riwayat sebelumnya.

### Contoh 2
```powershell
PS C:\> Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af"
```

Mendapatkan status kebijakan konfigurasi tamu terbaru berdasarkan Id inisiatif. Status tersebut mencakup status kepatuhan VM untuk setiap kebijakan dalam inisiatif, alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa untuk kepatuhan.
Hasil tidak menyertakan status sebelumnya yang dihasilkan, ini hanya mencakup status terbaru untuk setiap kebijakan dalam inisiatif tersebut.

### Contoh 3
```powershell
PS C:\> Get-AzVMGuestPolicyStatus -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17"
```

Mendapatkan status kebijakan konfigurasi tamu terbaru berdasarkan nama inisiatif.
Status tersebut mencakup status kepatuhan VM untuk setiap kebijakan dalam inisiatif, alasan kepatuhan, waktu pemeriksaan kepatuhan, informasi sumber daya yang diperiksa untuk kepatuhan.
Hasil tidak menyertakan status sebelumnya yang dihasilkan, ini hanya mencakup status terbaru untuk setiap kebijakan dalam inisiatif tersebut.

### Contoh 4
```powershell
PS C:\> Get-AzVMGuestPolicyStatus -ReportId "/subscriptions/4e6c6ed2-0bf6-41d7-9d21-a452c2cc7920/resourceGroups/MyResourceGroupName/providers/Microsoft.Compute/virtualMachines/MyVMName/providers/Microsoft.GuestConfiguration/guestConfigurationAssignments/MaximumPasswordAge/reports/c271f845-2c0a-4456-a441-e48fc332d0ac"
```

Dapatkan status kebijakan konfigurasi tamu menurut ReportId.
ReportId adalah properti ReportId yang dapat ditemukan dalam hasil analisisGet-AzVMGuestPolicyStatus berdasarkan inisiatifId atau Nama inisiatif (silakan rujuk contoh lainnya)

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
Id Definisi dari kebijakan di mana tipe definisi adalah Inisiatif dan kategori adalah Konfigurasi Tamu

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
Nama kebijakan di mana tipe definisi adalah Inisiatif dan kategori adalah Konfigurasi Tamu

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
Kebijakan ketika tipe definisi adalah Inisiatif dan kategori adalah Konfigurasi Tamu harus ditetapkan pada lingkup untuk mendapatkan status.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.GuestConfiguration.Models.PolicyStatusDetailed
## CATATAN

## RELATED LINKS
