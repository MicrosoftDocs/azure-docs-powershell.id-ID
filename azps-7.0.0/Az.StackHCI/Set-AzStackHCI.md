---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/set-azstackhci
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Set-AzStackHCI.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Set-AzStackHCI.md
ms.openlocfilehash: 57265ba0811fa46e9f585994d5f7ead65232f8f1
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136562909"
---
# Set-AzStackHCI

## SYNOPSIS
Set-AzStackHCI memodifikasi properti sumber daya dari sumber daya awan Microsoft.AzureStackHCI yang mewakili kluster lokal untuk mengaktifkan atau menonaktifkan fitur.

## SYNTAX

```
Set-AzStackHCI [[-ComputerName] <String>] [-Credential <PSCredential>] [-ResourceId <String>]
 [-EnableWSSubscription <Boolean>] [-DiagnosticLevel <DiagnosticLevel>] [-TenantId <String>]
 [-ArmAccessToken <String>] [-GraphAccessToken <String>] [-AccountId <String>] [-EnvironmentName <String>]
 [-UseDeviceAuthentication] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Set-AzStackHCI memodifikasi properti sumber daya dari sumber daya awan Microsoft.AzureStackHCI yang mewakili kluster lokal untuk mengaktifkan atau menonaktifkan fitur.

## EXAMPLES

### CONTOH 1
```powershell
PS C:\> Set-AzStackHCI -EnableWSSubscription $true
Result: Success
```

Faktur pada salah satu node kluster untuk mengaktifkan Windows Langganan Server

### CONTOH 2
```powershell
PS C:\> Set-AzStackHCI -ComputerName ClusterNode1 -DiagnosticLevel Basic
Result: Success
```

Faktur dari simpul manajemen untuk mengatur tingkat diagnostik ke Dasar

## PARAMETERS

### -AccountId
Menentukan token akses ARM.
Menentukan hal ini bersama dengan ArmAccessToken dan GraphAccessToken akan menghindari masuk interaktif Azure.

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

### -ArmAccessToken
Menentukan token akses ARM.
Menentukan hal ini bersama dengan GraphAccessToken dan AccountId akan menghindari masuk interaktif Azure.

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

### -ComputerName
Menentukan salah satu node kluster dalam kluster lokal yang terdaftar di Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Menentukan kredensial untuk ComputerName.
Default adalah pengguna saat ini yang menjalankan Cmdlet.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiagnosticLevel
Menentukan tingkat diagnostik untuk kluster.

```yaml
Type: DiagnosticLevel
Parameter Sets: (All)
Aliases:
Accepted values: Off, Basic, Enhanced

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWSSubscription
Menentukan apakah Windows Langganan Server harus diaktifkan atau dinonaktifkan.
Mengaktifkan fitur ini akan memulai tagihan melalui langganan Azure untuk Windows lisensi tamu Server.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentName
Menentukan Azure Environment.
Defaultnya adalah AzureCloud.
Nilai yang valid adalah AzureCloud, AzureChinaCloud, AzurePPE, AzureCanary, AzureUSGovernment

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $AzureCloud
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -GraphAccessToken
Menentukan token Graph akses.
Menentukan hal ini bersama dengan ArmAccessToken dan AccountId akan menghindari masuk interaktif Azure.

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

### -ResourceId
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat, termasuk langganan, seperti dalam contoh berikut ini: \` /Subscriptions/ ID langganan \` \` /providers/Microsoft.AzureStackHCI/clusters/MyCluster\`

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

### -TenantId
Menentukan Azure TenantId.

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

### -UseDeviceAuthentication
Gunakan autentikasi kode perangkat, bukan perintah browser interaktif.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Hasil: Berhasil atau Gagal atau Dibatalkan.
## CATATAN

## RELATED LINKS
