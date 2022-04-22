---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 7EC166C7-151D-4DA0-9B10-165E735D4F12
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermvmssextension
schema: 2.0.0
ms.openlocfilehash: f69b8901b2bc2c07bdf158da4c92deba0330109d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142929323"
---
# Add-AzureRmVmssExtension

## SYNOPSIS
Menambahkan ekstensi ke VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVmssExtension [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-Name] <String>]
 [[-Publisher] <String>] [[-Type] <String>] [[-TypeHandlerVersion] <String>]
 [[-AutoUpgradeMinorVersion] <Boolean>] [[-Setting] <Object>] [[-ProtectedSetting] <Object>]
 [-ForceUpdateTag <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVmssExtension** menambahkan ekstensi ke Kumpulan Skala Mesin Virtual (VMSS).

## EXAMPLES

### Contoh 1: Menambahkan ekstensi ke VMSS
```
PS C:\> Add-AzureRmVmssExtension -VirtualMachineScaleSet $VMSS -Name $ExtName -Publisher $Publisher -Type $ExtType -TypeHandlerVersion $ExtVer -AutoUpgradeMinorVersion $True
```

Perintah ini menambahkan ekstensi ke VMMS.

## PARAMETERS

### -AutoUpgradeMinorVersion
Menunjukkan apakah versi ekstensi harus diperbarui secara otomatis ke versi minor yang lebih baru.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
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

### -ForceUpdateTag
Jika nilai disediakan dan berbeda dari nilai sebelumnya, penanganan ekstensi akan dipaksa untuk diperbarui meskipun konfigurasi ekstensi belum berubah.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama ekstensi yang ditambahkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtectedSetting
Menentukan konfigurasi privat untuk ekstensi, sebagai string.
Cmdlet ini mengenkripsi konfigurasi privat.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Menentukan nama penerbit ekstensi.
Penerbit menyediakan nama ketika penerbit mendaftarkan ekstensi.
Ini dapat menggunakan cmdlet [Get-AzureRmVMImagePublisher](./Get-AzureRmVMImagePublisher.md) untuk mendapatkan penerbit.

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

### -Pengaturan
Menentukan konfigurasi publik, sebagai string, untuk ekstensi.
Cmdlet ini tidak mengenkripsi konfigurasi publik.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe ekstensi.
Anda dapat menggunakan cmdlet [Get-AzureRmVMExtensionImageType](./Get-AzureRmVMExtensionImageType.md) untuk mendapatkan tipe ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi yang akan digunakan untuk mesin virtual ini.
Anda dapat menggunakan cmdlet [Get-AzureRmVMExtensionImage](./Get-AzureRmVMExtensionImage.md) untuk mendapatkan versi ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Tentukan objek VMSS.
Anda dapat menggunakan [New-AzureRmVmssConfig](./New-AzureRmVmssConfig.md) untuk membuat objek.

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

###  
Cmdlet ini tidak menghasilkan output apa pun.

## NOTES

## RELATED LINKS

[Hapus-AzureRmVmssExtension](./Remove-AzureRmVmssExtension.md)

[Get-AzureRmVMImagePublisher](./Get-AzureRmVMImagePublisher.md)

[Get-AzureRmVMExtensionImageType](./Get-AzureRmVMExtensionImageType.md)

[Get-AzureRmVMExtensionImage](./Get-AzureRmVMExtensionImage.md)

[New-AzureRmVmssConfig](./New-AzureRmVmssConfig.md)
