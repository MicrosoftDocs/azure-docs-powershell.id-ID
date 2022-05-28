---
external help file: Microsoft.Azure.PowerShell.Cmdlets.GuestConfiguration.dll-Help.xml
Module Name: Az.GuestConfiguration
online version: https://docs.microsoft.com/powershell/module/az.guestconfiguration/get-azvmguestpolicystatushistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatusHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatusHistory.md
ms.openlocfilehash: 205ce9b5c6cbc35a15b1e94494dcd43c6188f186
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145518139"
---
# Get-AzVMGuestPolicyStatusHistory

## SYNOPSIS
Mendapatkan riwayat status kepatuhan kebijakan konfigurasi tamu untuk inisiatif jenis "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan jenis definisi "Inisiatif".

## SYNTAX

### InitiativeNameScope (Default)
```
Get-AzVMGuestPolicyStatusHistory [-ResourceGroupName] <String> [-VMName] <String> [-InitiativeName] <String>
 [-ShowOnlyChange] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InitiativeIdScope
```
Get-AzVMGuestPolicyStatusHistory [-ResourceGroupName] <String> [-VMName] <String> [[-InitiativeId] <String>]
 [-ShowOnlyChange] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzVMGuestPolicyStatusHistory mendapatkan riwayat status kepatuhan kebijakan konfigurasi tamu untuk inisiatif jenis "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan jenis definisi "Inisiatif".
Gunakan cmdlet Get-AzVMGuestPolicyStatus untuk mendapatkan detail status kepatuhan tunggal menggunakan ReportId yang dapat ditemukan dalam output cmdlet Get-AzVMGuestPolicyStatusHistory.

## EXAMPLES

### Contoh 1
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan menurut Id inisiatif. Sakelar ShowOnlyChange hanya memperlihatkan perubahan status historis.
Melompati status yang tidak berubah di antara dua pemeriksaan kepatuhan.

### Contoh 2
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan berdasarkan nama inisiatif.
Sakelar ShowOnlyChange hanya memperlihatkan perubahan status historis.
Melompati status yang tidak berubah di antara dua pemeriksaan kepatuhan.

### Contoh: 3
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan untuk semua kebijakan konfigurasi tamu yang ditetapkan ke VM.
Sakelar ShowOnlyChange hanya memperlihatkan perubahan status historis.
Melompati status yang tidak berubah di antara dua pemeriksaan kepatuhan.

### Contoh 4
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af"
```

Mendapatkan riwayat status kepatuhan berdasarkan Id inisiatif.

### Contoh 5
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17"
```

Mendapatkan riwayat status kepatuhan berdasarkan nama inisiatif.

### Contoh 6
```powershell
Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
```
Mendapatkan riwayat status kepatuhan untuk semua kebijakan konfigurasi tamu yang ditetapkan ke VM.

### Contoh 7
```powershell
$x = Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
$x[10].ReportId
Get-AzVMGuestPolicyStatus -ReportId $x[10].ReportId
```

Dapatkan status kebijakan konfigurasi tamu menurut ReportId.
ReportId adalah properti ReportId yang dapat ditemukan dalam hasil Get-AzVMGuestPolicyStatusHistory. (silakan lihat contoh lain)

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

Required: False
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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowOnlyChange
Menampilkan perubahan status historis hanya untuk kebijakan konfigurasi tamu.
Melompati status yang tidak berubah di antara dua eksekusi audit status kepatuhan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Nama VM.

```yaml
Type: System.String
Parameter Sets: (All)
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

### Microsoft.Azure.Commands.GuestConfiguration.Models.PolicyStatus
## NOTES

## RELATED LINKS
