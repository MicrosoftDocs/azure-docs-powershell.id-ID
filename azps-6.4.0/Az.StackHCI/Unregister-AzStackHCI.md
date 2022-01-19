---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/unregister-azstackhci
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Unregister-AzStackHCI.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Unregister-AzStackHCI.md
ms.openlocfilehash: 5d793f1ab3efdae1255507844a10f53d57b119fd
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136208480"
---
# Unregister-AzStackHCI

## SYNOPSIS
Unregister-AzStackHCI menghapus sumber daya awan Microsoft.AzureStackHCI yang mewakili kluster lokal dan membatalkan pendaftaran kluster lokal dengan Azure.
Informasi terdaftar yang tersedia pada kluster digunakan untuk membatalkan pendaftaran kluster jika tidak ada parameter yang lolos.

## SYNTAX

```
Unregister-AzStackHCI [[-SubscriptionId] <String>] [[-ResourceName] <String>] [[-TenantId] <String>]
 [[-ResourceGroupName] <String>] [[-ArmAccessToken] <String>] [[-GraphAccessToken] <String>]
 [[-AccountId] <String>] [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [-UseDeviceAuthentication] [-DisableOnlyAzureArcServer] [[-Credential] <PSCredential>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Unregister-AzStackHCI menghapus sumber daya awan Microsoft.AzureStackHCI yang mewakili kluster lokal dan membatalkan pendaftaran kluster lokal dengan Azure.
Informasi terdaftar yang tersedia pada kluster digunakan untuk membatalkan pendaftaran kluster jika tidak ada parameter yang lolos.

## EXAMPLES

### CONTOH 1
```powershell
C:\PS\>Unregister-AzStackHCI
Result: Success
```

Melakukan faktur pada salah satu node kluster

### CONTOH 2
```powershell
C:\PS\>Unregister-AzStackHCI -ComputerName ClusterNode1
Result: Success
```

Melakukan faktur dari simpul manajemen

### CONTOH 3
```powershell
C:\PS\>Unregister-AzStackHCI -SubscriptionId "12a0f531-56cb-4340-9501-257726d741fd" -ArmAccessToken etyer..ere= -GraphAccessToken acyee..rerrer -AccountId user1@corp1.com -ResourceName DemoHCICluster3 -ResourceGroupName DemoHCIRG -Confirm:$False
Result: Success
```

Melakukan invoking dari WAC

### CONTOH 4
```powershell
C:\PS\>Unregister-AzStackHCI -SubscriptionId "12a0f531-56cb-4340-9501-257726d741fd" -ResourceName HciCluster1 -TenantId "c31c0dbb-ce27-4c78-ad26-a5f717c14557" -ResourceGroupName HciClusterRG -ArmAccessToken eerrer..ere= -GraphAccessToken acee..rerrer -AccountId user1@corp1.com -EnvironmentName AzureCloud -ComputerName node1hci -Credential Get-Credential
Result: Success
```

Melakukan permintaan dengan semua parameter

## PARAMETERS

### -AccountId
Menentukan token akses ARM.
Menentukan hal ini bersama dengan ArmAccessToken dan GraphAccessToken akan menghindari masuk interaktif Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
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
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Menentukan salah satu node kluster dalam kluster lokal yang sedang didaftarkan ke Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
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
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableOnlyAzureArcServer
Menentukan parameter ini $true hanya akan membatalkan pendaftaran node kluster dengan Arc untuk server dan pendaftaran HCI Azure Stack tidak akan diubah.

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

### -EnvironmentName
Menentukan Azure Environment.
Defaultnya adalah AzureCloud.
Nilai yang valid adalah AzureCloud, AzureChinaCloud, AzureUSGovernment, AzureGermanCloud, AzurePPE

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: $AzureCloud
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Menentukan bahwa pembatalan pendaftaran akan terus bahkan jika kami tidak dapat menghapus ekstensi Arc di simpul.

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
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kawasan
Menentukan Kawasan sumber daya yang dibuat di Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama Grup Sumber Daya Azure.
Jika tidak ditentukan \<LocalClusterName\> ,rg akan digunakan sebagai nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceName
Menentukan nama sumber daya dari sumber daya yang dibuat di Azure.
Jika tidak ditentukan, nama kluster lokal akan digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Menentukan Langganan Azure untuk membuat sumber daya

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

### -TenantId
Menentukan Azure TenantId.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
