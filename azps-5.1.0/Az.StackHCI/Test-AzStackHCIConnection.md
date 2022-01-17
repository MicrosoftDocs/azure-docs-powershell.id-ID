---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/en-us/powershell/module/az.stackhci/test-azstackhciconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/StackHCI/help/Test-AzStackHCIConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/StackHCI/help/Test-AzStackHCIConnection.md
ms.openlocfilehash: 1183a2aa6bf452d77ebe3975024067244075e5fb
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136029917"
---
# Test-AzStackHCIConnection

## SYNOPSIS
Test-AzStackHCIConnection memverifikasi konektivitas dari node ter kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## SINTAKS

```
Test-AzStackHCIConnection [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESKRIPSI
Test-AzStackHCIConnection memverifikasi konektivitas dari node ter kluster lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## CONTOH

### CONTOH 1
```
Invoking on one of the cluster node. Success case.
```

Uji C:\PS-AzStackHCIConnection: Koneksi ke Titik Akhir Layanan HCI Tumpukan \> AzureTested: Hasil https://azurestackhci-df.azurefd.net/health Benar: Berhasil

### CONTOH 2
```
Invoking on one of the cluster node. Failed case.
```

Uji C:\PS-AzStackHCIConnection: Koneksi ke Titik Akhir Layanan HCI Tumpukan \> AzureTested: https://azurestackhci-df.azurefd.net/health IsRequired: True Hasil: Gagal FailedNodes: Node1inClus2, Node2inClus3

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

## INPUT

## OUTPUT

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Uji: Nama pengujian dilakukan.
### EndpointTested: Titik akhir yang digunakan dalam pengujian.
### IsRequired: True atau False
### Hasil: Berhasil atau Gagal
### FailedNodes: Daftar node yang gagal dilakukan pengujian.
## CATATAN

## LINK TERKAIT
