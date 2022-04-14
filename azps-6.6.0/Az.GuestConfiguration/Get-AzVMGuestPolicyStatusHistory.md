---
external help file: Microsoft.Azure.PowerShell.Cmdlets.GuestConfiguration.dll-Help.xml
Module Name: Az.GuestConfiguration
online version: https://docs.microsoft.com/powershell/module/az.guestconfiguration/get-azvmguestpolicystatushistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatusHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/GuestConfiguration/GuestConfiguration/help/Get-AzVMGuestPolicyStatusHistory.md
ms.openlocfilehash: 02a4d57be32edb1128f5c528125f53b4e563ce69
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142232155"
---
# Get-AzVMGuestPolicyStatusHistory

## SYNOPSIS
Mendapatkan riwayat status kepatuhan kebijakan konfigurasi tamu untuk inisiatif tipe "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan tipe definisi "Inisiatif".

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.guestconfiguration/get-azvmguestpolicystatushistory) untuk informasi terbaru.

## SYNTAX

### InisiatifNameScope (Default)
```
Get-AzVMGuestPolicyStatusHistory [-ResourceGroupName] <String> [-VMName] <String> [-InitiativeName] <String>
 [-ShowOnlyChange] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InisiatifIdScope
```
Get-AzVMGuestPolicyStatusHistory [-ResourceGroupName] <String> [-VMName] <String> [[-InitiativeId] <String>]
 [-ShowOnlyChange] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzVMGuestPolicyStatusHistory mendapatkan riwayat status kepatuhan kebijakan konfigurasi tamu untuk inisiatif tipe "Konfigurasi Tamu" yang ditetapkan ke VM.
Inisiatif adalah kebijakan tipe definisi "Inisiatif".
Gunakan cmdlet Get-AzVMGuestPolicyStatus untuk mendapatkan detail status kepatuhan tunggal menggunakan ReportId yang dapat ditemukan dalam output cmdlet Get-AzVMGuestPolicyStatusHistory.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan menurut Id inisiatif. Sakelar ShowOnlyChange hanya memperlihatkan perubahan status riwayat.
Lewati status yang tidak berubah antara dua pemeriksaan kepatuhan.

### Contoh 2
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan menurut nama inisiatif.
Sakelar ShowOnlyChange hanya memperlihatkan perubahan status riwayat.
Lewati status yang tidak berubah antara dua pemeriksaan kepatuhan.

### Contoh 3
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -ShowOnlyChange
```

Mendapatkan riwayat status kepatuhan untuk semua kebijakan konfigurasi tamu yang ditetapkan ke VM.
Sakelar ShowOnlyChange hanya memperlihatkan perubahan status riwayat.
Lewati status yang tidak berubah antara dua pemeriksaan kepatuhan.

### Contoh 4
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeId "/providers/Microsoft.Authorization/policySetDefinitions/3fa7cbf5-c0a4-4a59-85a5-cca4d996d5af"
```

Mendapatkan riwayat status kepatuhan menurut Id inisiatif.

### Contoh 5
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName" -InitiativeName "b5a822e0-ba98-4e54-9278-5d9833aa9b17"
```

Mendapatkan riwayat status kepatuhan menurut nama inisiatif.

### Contoh 6
```powershell
PS C:\> Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
```
Mendapatkan riwayat status kepatuhan untuk semua kebijakan konfigurasi tamu yang ditetapkan ke VM.

### Contoh 7
```powershell
PS C:\>$x = Get-AzVMGuestPolicyStatusHistory -ResourceGroupName "MyResourceGroupName" -VMName "MyVMName"
PS C:\>$x[10].ReportId
/subscriptions/4e6c6ed2-0bf6-41d7-9d21-a452c2cc7920/resourceGroups/MyResourceGroupName/providers/Microsoft.Compute/virtualMachines/MyVMName/providers/Microsoft.GuestConfiguration/guestConfigurationAssignments/MaximumPasswordAge/reports/c271f845-2c0a-4456-a441-e48fc332d0ac
PS C:\> Get-AzVMGuestPolicyStatus -ReportId $x[10].ReportId
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

### -InisiatifId
Id Definisi kebijakan di mana tipe definisi adalah Inisiatif dan kategori adalah Konfigurasi Tamu

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
Memperlihatkan perubahan status riwayat hanya untuk kebijakan konfigurasi tamu.
Melewati status yang tidak berubah antara dua audit status kepatuhan dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
## OUTPUTS

### Microsoft.Azure.Commands.GuestConfiguration.Models.PolicyStatus
## CATATAN

## RELATED LINKS
