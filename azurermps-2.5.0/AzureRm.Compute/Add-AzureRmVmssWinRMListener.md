---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 987BD670-20F3-4105-A5BE-03E712AB2B56
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermvmsswinrmlistener
schema: 2.0.0
ms.openlocfilehash: dd9c13298adac34a53ed2f97bbc1e3edc95892df
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143221902"
---
# Add-AzureRmVmssWinRMListener

## SYNOPSIS
Menambahkan pendengar WinRM ke VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVmssWinRMListener [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-Protocol] <ProtocolTypes>]
 [[-CertificateUrl] <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVmssWinRMListener** menambahkan pendengar Windows Remote Management (WinRM) di Kumpulan Skala Mesin Virtual (VMSS).

## EXAMPLES

### Contoh 1: Menambahkan pendengar WinRM ke VMSS
```
PS C:\> $VMSS = New-AzureRmVmssConfig
PS C:\> Add-AzureRmVmssWinRMListener -VirtualMachineScaleSet $VMSS -Protocol Https -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion"
```

Contoh ini menambahkan pendengar WinRM ke VMSS.

Perintah pertama menggunakan cmdlet **New-AzureRmVmsConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS.
Perintah kedua menambahkan protokol HTTP Pendengar WinRM dengan sertifikat di URL tertentu ke VMSS.

## PARAMETERS

### -CertificateUrl
Menentukan tautan, sebagai URL, sertifikat tempat mesin virtual baru ditetapkan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
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

### -VirtualMachineScaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet New-AzureRmVmssConfig untuk membuat objek.

```yaml
Type: PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### VirtualMachineScaleSet
Parameter 'VirtualMachineScaleSet' menerima nilai tipe 'VirtualMachineScaleSet' dari pipeline

## OUTPUTS

### Cmdlet ini tidak menghasilkan output apa pun.

## NOTES

## RELATED LINKS

[New-AzureRmVmssConfig](./New-AzureRmVmssConfig.md)


