---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/test-azstackhciconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
ms.openlocfilehash: d599d37da26c733b9085a4d8dafdaa061057c628
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136338417"
---
# Test-AzStackHCIConnection

## SYNOPSIS
Test-AzStackHCIConnection memverifikasi konektivitas dari node ter kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## SYNTAX

```
Test-AzStackHCIConnection [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
Test-AzStackHCIConnection memverifikasi konektivitas dari node ter kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## EXAMPLES

### CONTOH 1
```powershell
C:\PS\>Test-AzStackHCIConnection
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Succeeded
```
Voking pada salah satu node kluster. Kasus berhasil.

### CONTOH 2
```powershell
C:\PS\>Test-AzStackHCIConnection
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Failed
FailedNodes: Node1inClus2, Node2inClus3
```
Voking pada salah satu node kluster. Gagalkan huruf.

## PARAMETERS

### -ComputerName
Menentukan salah satu node kluster dalam kluster lokal yang sedang didaftarkan ke Azure.

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

### -Credential
Menentukan kredensial untuk ComputerName.
Default adalah pengguna saat ini yang menjalankan Cmdlet.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
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
Position: 1
Default value: $AzureCloud
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kawasan
Menentukan Kawasan untuk disambungkan.
Tidak digunakan kecuali wilayah Canary.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Uji: Nama pengujian dilakukan.
### EndpointTested: Titik akhir yang digunakan dalam pengujian.
### IsRequired: True atau False
### Hasil: Berhasil atau Gagal
### FailedNodes: Daftar node yang gagal dilakukan pengujian.
## CATATAN

## RELATED LINKS
