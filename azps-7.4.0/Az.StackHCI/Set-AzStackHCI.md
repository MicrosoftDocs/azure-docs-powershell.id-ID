---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/set-azstackhci
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Set-AzStackHCI.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Set-AzStackHCI.md
ms.openlocfilehash: 7ad8cc442b5ddfed209f3aade0cfdd5b492be96c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142171447"
---
# Set-AzStackHCI

## SYNOPSIS
Set-AzStackHCI memodifikasi properti sumber daya sumber daya cloud Microsoft.AzureStackHCI yang mewakili kluster lokal untuk mengaktifkan atau menonaktifkan fitur.

## SYNTAX

```
Set-AzStackHCI [[-ComputerName] <String>] [-Credential <PSCredential>] [-ResourceId <String>]
 [-EnableWSSubscription <Boolean>] [-DiagnosticLevel <DiagnosticLevel>] [-TenantId <String>]
 [-ArmAccessToken <String>] [-GraphAccessToken <String>] [-AccountId <String>] [-EnvironmentName <String>]
 [-UseDeviceAuthentication] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Set-AzStackHCI memodifikasi properti sumber daya sumber daya cloud Microsoft.AzureStackHCI yang mewakili kluster lokal untuk mengaktifkan atau menonaktifkan fitur.

## EXAMPLES

### CONTOH 1
```powershell
Set-AzStackHCI -EnableWSSubscription $true
```

```output
Result: Success
```

Memanggil di salah satu simpul kluster untuk mengaktifkan fitur Langganan Server Windows

### CONTOH 2
```powershell
Set-AzStackHCI -ComputerName ClusterNode1 -DiagnosticLevel Basic
```

```output
Result: Success
```

Memanggil dari simpul manajemen untuk mengatur tingkat diagnostik ke Dasar

## PARAMETERS

### -AccountId
Menentukan token akses ARM.
Menentukan ini bersama dengan ArmAccessToken dan GraphAccessToken akan menghindari masuk interaktif Azure.

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
Menentukan ini bersama dengan GraphAccessToken dan AccountId akan menghindari masuk interaktif Azure.

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
Menentukan salah satu simpul kluster di kluster lokal yang didaftarkan ke Azure.

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

### -Kredensial
Menentukan kredensial untuk ComputerName.
Defaultnya adalah pengguna saat ini menjalankan Cmdlet.

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
Menentukan apakah Langganan Server Windows harus diaktifkan atau dinonaktifkan.
Mengaktifkan fitur ini memulai tagihan melalui langganan Azure Anda untuk lisensi tamu Windows Server.

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
Menentukan Lingkungan Azure.
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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Menentukan token akses Graph.
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
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat, termasuk langganan, seperti dalam contoh berikut: \`/Subscriptions/\`subscription ID\`/providers/Microsoft.AzureStackHCI/clusters/MyCluster\`

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Hasil: Berhasil atau Gagal atau Dibatalkan.
## CATATAN

## RELATED LINKS
