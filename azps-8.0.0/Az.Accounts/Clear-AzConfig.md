---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/clear-azconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Clear-AzConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Clear-AzConfig.md
ms.openlocfilehash: 29b96246547b27b4972402d3d9c8f825c6f6aa03
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145506883"
---
# Clear-AzConfig

## SYNOPSIS
Menghapus nilai konfigurasi yang ditetapkan oleh pengguna.

## SYNTAX

### ClearAll (Default)
```
Clear-AzConfig [-Force] [-PassThru] [-AppliesTo <String>] [-Scope <ConfigScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClearByKey
```
Clear-AzConfig [-PassThru] [-AppliesTo <String>] [-Scope <ConfigScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-DefaultSubscriptionForLogin]
 [-DisplayBreakingChangeWarning] [-EnableDataCollection] [<CommonParameters>]
```

## DESCRIPTION
Menghapus nilai konfigurasi yang ditetapkan oleh pengguna. Secara default semua konfigurasi akan dihapus. Anda juga dapat menentukan kunci konfigurasi untuk dihapus.

## EXAMPLES

### Contoh 1
```powershell
Clear-AzConfig -Force
```

Bersihkan semua konfigurasi. `-Force` menekan permintaan untuk konfirmasi.

### Contoh 2
```powershell
Clear-AzConfig -EnableDataCollection
```

Kosongkan konfigurasi "EnableDataCollection".

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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClearByKey
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayBreakingChangeWarning
Mengontrol apakah pesan peringatan untuk melanggar perubahan ditampilkan atau disembunyikan. Saat diaktifkan, peringatan perubahan mencolok ditampilkan saat menjalankan cmdlet dengan melanggar perubahan dalam rilis mendatang.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClearByKey
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
Parameter Sets: ClearByKey
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Jangan meminta konfirmasi saat menghapus semua konfigurasi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClearAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true jika cmdlet dijalankan dengan benar.

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

### Tidak ada

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
