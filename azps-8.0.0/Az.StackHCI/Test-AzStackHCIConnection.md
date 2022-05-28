---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/test-azstackhciconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
ms.openlocfilehash: 310c828337471ac6020233d09b800308f622bf5f
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145514851"
---
# Test-AzStackHCIConnection

## SYNOPSIS
Test-AzStackHCIConnection memverifikasi konektivitas dari simpul kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## SYNTAX

```
Test-AzStackHCIConnection [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
Test-AzStackHCIConnection memverifikasi konektivitas dari simpul kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## EXAMPLES

### CONTOH 1
```powershell
Test-AzStackHCIConnection
```

```output
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Succeeded
```
Memanggil pada salah satu node kluster. Kasus sukses.

### CONTOH 2
```powershell
Test-AzStackHCIConnection
```

```output
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Failed
FailedNodes: Node1inClus2, Node2inClus3
```
Memanggil pada salah satu node kluster. Kasus gagal.

## PARAMETERS

### -ComputerName
Menentukan salah satu node kluster di kluster lokal yang sedang didaftarkan ke Azure.

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
Defaultnya adalah pengguna saat ini yang menjalankan Cmdlet.

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
Menentukan Lingkungan Azure.
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

### -Wilayah
Menentukan Wilayah yang akan disambungkan.
Tidak digunakan kecuali itu adalah wilayah Canary.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Uji: Nama pengujian yang dilakukan.
### EndpointTested: Titik akhir yang digunakan dalam pengujian.
### IsRequired: True atau False
### Hasil: Berhasil atau Gagal
### FailedNodes: Daftar simpul tempat pengujian gagal.
## NOTES

## RELATED LINKS
