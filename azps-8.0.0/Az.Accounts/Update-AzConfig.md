---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/update-azconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Update-AzConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Update-AzConfig.md
ms.openlocfilehash: 25380b560417b25ffda21553b9f8d5d8ea2e2ec1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145519027"
---
# Update-AzConfig

## SYNOPSIS
Memperbarui konfigurasi Azure PowerShell.

## SYNTAX

```
Update-AzConfig [-AppliesTo <String>] [-Scope <ConfigScope>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [-DefaultSubscriptionForLogin <String>] [-DisplayBreakingChangeWarning <Boolean>]
 [-EnableDataCollection <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui konfigurasi Azure PowerShell.
Bergantung pada konfigurasi mana yang akan diperbarui, Anda dapat menentukan cakupan tempat konfigurasi dipertahankan dan modul atau cmdlet mana yang diterapkannya.

> [!NOTE]
> Tidak disarankan untuk memperbarui konfigurasi dalam beberapa proses PowerShell. Lakukan dalam satu proses, atau pastikan pembaruan berada di lingkup Proses (`-Scope Process`) untuk menghindari efek samping yang tidak terduga.

## EXAMPLES

### Contoh 1
```powershell
Update-AzConfig -DefaultSubscriptionForLogin "Name of subscription"
```

```output
Key                         Value                Applies To Scope       Help Message
---                         -----                ---------- -----       ------------
DefaultSubscriptionForLogin Name of subscription Az         CurrentUser Subscription name or GUID. Sets the default context for Azure PowerShell when lo…
```

Mengatur konfigurasi "DefaultSubscriptionForLogin" sebagai "Nama langganan". Ketika `Connect-AzAccount` langganan yang ditentukan akan dipilih sebagai langganan default.

### Contoh 2
```powershell
Update-AzConfig -DisplayBreakingChangeWarning $false -AppliesTo "Az.KeyVault"
```

```output
Key                          Value Applies To  Scope       Help Message
---                          ----- ----------  -----       ------------
DisplayBreakingChangeWarning False Az.KeyVault CurrentUser Controls if warning messages for breaking changes are displayed or suppressed. When enabled,…
```

Mengatur konfigurasi "DisplayBreakingChangeWarnings" sebagai "$false" untuk modul "Az.KeyVault". Ini mencegah semua pesan peringatan untuk perubahan mencolok yang akan datang dalam modul Az.KeyVault agar tidak diminta.

### Contoh: 3
```powershell
Update-AzConfig -EnableDataCollection $true
```

```output
Key                  Value Applies To Scope       Help Message
---                  ----- ---------- -----       ------------
EnableDataCollection True  Az         CurrentUser When enabled, Azure PowerShell cmdlets send telemetry data to Microsoft to improve the customer experi…
```

Mengatur konfigurasi "EnableDataCollection" sebagai "$true". Ini memungkinkan pengiriman data telemetri.
Mengatur konfigurasi ini setara dengan `Enable-AzDataCollection` dan `Disable-AzDataCollection`.

## PARAMETERS

### -AppliesTo
Menentukan bagian mana dari Azure PowerShell konfigurasi yang berlaku.
Potensi nilai:
- "Az": konfigurasi berlaku untuk semua modul dan cmdlet Azure PowerShell.
- Nama modul: konfigurasi berlaku untuk modul Azure PowerShell tertentu.
Misalnya, "Az.Storage".
- Nama cmdlet: konfigurasi berlaku untuk cmdlet Azure PowerShell tertentu.
Misalnya, "Get-AzKeyVault".
Jika tidak ditentukan, saat mendapatkan atau menghapus konfigurasi, konfigurasi default ke semua hal di atas; saat memperbarui, defaultnya adalah "Az".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DefaultSubscriptionForLogin
Nama langganan atau GUID.
Mengatur konteks default untuk Azure PowerShell saat masuk tanpa menentukan langganan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayBreakingChangeWarning
Mengontrol apakah pesan peringatan untuk melanggar perubahan ditampilkan atau disembunyikan. Saat diaktifkan, peringatan perubahan mencolok ditampilkan saat menjalankan cmdlet dengan melanggar perubahan dalam rilis mendatang.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableDataCollection
Saat diaktifkan, Azure PowerShell cmdlet mengirim data telemetri ke Microsoft untuk meningkatkan pengalaman pelanggan.
Untuk informasi selengkapnya, lihat pernyataan privasi kami: https://aka.ms/privacy

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cakupan
Menentukan cakupan perubahan konfigurasi, misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini.
Secara default, ini adalah CurrentUser.

```yaml
Type: Microsoft.Azure.PowerShell.Common.Config.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, Process, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSConfig

## NOTES

## RELATED LINKS
