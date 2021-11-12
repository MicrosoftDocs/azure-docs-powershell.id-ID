---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: 987BD670-20F3-4105-A5BE-03E712AB2B56
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Add-AzureRmVmssWinRMListener.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Add-AzureRmVmssWinRMListener.md
ms.openlocfilehash: d2ed576131ad2ff33ae7e5c7e5be091ca8f4a50e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423008"
---
# Add-AzureRmVmssWinRMListener

## SYNOPSIS
Menambahkan pendengar WinRM pada VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVmssWinRMListener [-VirtualMachineScaleSet] <VirtualMachineScaleSet> [[-Protocol] <ProtocolTypes>]
 [[-CertificateUrl] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVmssWinRMListener** menambahkan pendengar Windows Remote Management (WinRM) pada Virtual Machine Scale Set (VMSS).

## EXAMPLES

### Contoh 1: Tambahkan pendengar WinRM ke VMSS
```
PS C:\> $VMSS = New-AzureRmVmssConfig
PS C:\> Add-AzureRmVmssWinRMListener -VirtualMachineScaleSet $VMSS -Protocol Https -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion"
```

Contoh ini menambahkan pendengar WinRM pada VMSS.

Perintah pertama menggunakan cmdlet **New-AzureRmVmssConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS.
Perintah kedua menambahkan pendengar WinRM protokol HTTP dengan sertifikat pada URL yang ditentukan ke VMSS.

## PARAMETERS

### -CertificateUrl
Menentukan link, sebagai URL, sertifikat yang menyediakan mesin virtual baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Menentukan protokol pendengar WinRM.
Nilai yang dapat diterima untuk parameter ini adalah:

- Http
- Https

```yaml
Type: ProtocolTypes
Parameter Sets: (All)
Aliases: 
Accepted values: Http, Https

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachinescaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet New-AzureRmVmssConfig untuk membuat objek.

```yaml
Type: VirtualMachineScaleSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN

## RELATED LINKS

[New-AzureRmVmssConfig](./New-AzureRmVmssConfig.md)


