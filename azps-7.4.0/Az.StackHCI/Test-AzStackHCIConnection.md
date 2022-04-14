---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/test-azstackhciconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
ms.openlocfilehash: 310c828337471ac6020233d09b800308f622bf5f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142171442"
---
# Test-AzStackHCIConnection

## SYNOPSIS
Test-AzStackHCIConnection memverifikasi konektivitas dari simpul tergugus lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

## SYNTAX

```
Test-AzStackHCIConnection [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
Test-AzStackHCIConnection memverifikasi konektivitas dari simpul tergugus lokal ke layanan Azure yang diperlukan oleh Azure Stack HCI.

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
Memanggil salah satu simpul kluster. Kasus keberhasilan.

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
Memanggil salah satu simpul kluster. Kasus gagal.

## PARAMETERS

### -ComputerName
Menentukan salah satu simpul kluster di kluster lokal yang sedang didaftarkan ke Azure.

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

### -Kredensial
Menentukan kredensial untuk ComputerName.
Defaultnya adalah pengguna saat ini menjalankan Cmdlet.

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

### -Kawasan
Menentukan Kawasan yang akan disambungkan.
Tidak digunakan kecuali itu adalah kawasan Canary.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Uji: Nama uji yang dilakukan.
### EndpointTested: Titik akhir yang digunakan dalam pengujian.
### IsRequired: True atau False
### Hasil: Berhasil atau Gagal
### FailedNodes: Daftar node yang gagal dilakukan pengujian.
## CATATAN

## RELATED LINKS
