---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzConfig.md
ms.openlocfilehash: 4d9395aa4f3b58538661332cf3d40278c649ab8b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513111"
---
# Get-AzConfig

## SYNOPSIS
Mendapatkan konfigurasi Azure PowerShell.

## SYNTAX

```
Get-AzConfig [-AppliesTo <String>] [-Scope <ConfigScope>] [-DefaultProfile <IAzureContextContainer>]
 [-DefaultSubscriptionForLogin] [-DisplayBreakingChangeWarning] [-EnableDataCollection] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan konfigurasi Azure PowerShell.
Secara default mencantumkan semua konfigurasi. Anda dapat memfilter hasilnya menggunakan berbagai parameter.

> [!NOTE]
> Konfigurasi memiliki prioritas. Secara umum, cakupan Proses memiliki prioritas yang lebih tinggi daripada cakupan CurrentUser; konfigurasi yang berlaku untuk cmdlet tertentu memiliki prioritas yang lebih tinggi daripada yang berlaku untuk modul, sekali lagi lebih tinggi dari Az.
> Untuk mengurangi kebingungan, hasilnya `Get-AzConfig` menunjukkan konfigurasi yang berlaku. Ini adalah kombinasi dari semua konfigurasi, tetapi tidak benar-benar semua konfigurasi. Namun, Anda selalu dapat melihatnya dengan menerapkan parameter filter yang berbeda, seperti `-Scope`.

## EXAMPLES

### Contoh 1
```powershell
Get-AzConfig
```

```output
Key                           Value Applies To Scope       Help Message
---                           ----- ---------- -----       ------------
EnableDataCollection          False Az         CurrentUser When enabled, Azure PowerShell cmdlets send telemetry data to Microsoft to improve the custom…
DefaultSubscriptionForLogin         Az         Default     Subscription name or GUID. Sets the default context for Azure PowerShell when logging in with…
DisplayBreakingChangeWarning  True  Az         Default     Controls if warning messages for breaking changes are displayed or suppressed. When enabled, …
```

Mendapatkan semua konfigurasi.

### Contoh 2
```powershell
Get-AzConfig -EnableDataCollection
```

```output
Key                           Value Applies To Scope       Help Message
---                           ----- ---------- -----       ------------
EnableDataCollection          False Az         CurrentUser When enabled, Azure PowerShell cmdlets send telemetry data to Microsoft to improve the custom…
```

Mendapatkan konfigurasi "EnableDataCollection".

## PARAMETERS

### -TerapkanKe
Menentukan bagian mana dari Azure PowerShell konfigurasi yang berlaku.
Potensi nilai:
- "Az": konfigurasi berlaku untuk semua modul dan cmdlet Azure PowerShell.
- Nama modul: konfigurasi berlaku untuk modul Azure PowerShell tertentu.
Misalnya, "Az.Storage".
- Nama cmdlet: konfigurasi berlaku untuk cmdlet Azure PowerShell tertentu.
Misalnya, "Get-AzKeyVault".
Jika tidak ditentukan, saat mendapatkan atau menghapus konfigurasi, konfigurasi default ke semua di atas; saat memperbarui, defaultnya adalah "Az".

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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayBreakingChangeWarning
Kontrol jika pesan peringatan untuk melanggar perubahan ditampilkan atau ditekan. Saat diaktifkan, peringatan perubahan mencolok ditampilkan saat menjalankan cmdlet dengan perubahan yang melanggar dalam rilis mendatang.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDataCollection
Saat diaktifkan, Azure PowerShell cmdlet mengirim data telemetri ke Microsoft untuk meningkatkan pengalaman pelanggan.
Untuk informasi selengkapnya, lihat pernyataan privasi kami: https://aka.ms/privacy

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Menentukan cakupan perubahan konfigurasi, misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini.
Secara default adalah CurrentUser.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSConfig

## NOTES

## RELATED LINKS
