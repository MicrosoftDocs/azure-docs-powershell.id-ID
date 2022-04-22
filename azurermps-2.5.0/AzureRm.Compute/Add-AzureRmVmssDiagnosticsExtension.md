---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 7A1B92F5-C698-4D5E-ACD7-4013F1BC6247
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermvmssdiagnosticsextension
schema: 2.0.0
ms.openlocfilehash: 8e6a0ec7002f211e660c3ca71d190faf719bbd6c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142929359"
---
# Add-AzureRmVmssDiagnosticsExtension

## SYNOPSIS
Menambahkan ekstensi diagnostik ke VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVmssDiagnosticsExtension [-VirtualMachineScaleSet] <VirtualMachineScaleSet>
 [-SettingFilePath] <String> [[-ProtectedSettingFilePath] <String>] [[-Name] <String>]
 [[-TypeHandlerVersion] <String>] [[-AutoUpgradeMinorVersion] <Boolean>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVmssDiagnosticsExtension** menambahkan ekstensi diagnostik ke instans Kumpulan Skala Mesin Virtual (VMSS).

## EXAMPLES

### Contoh 1: Menambahkan ekstensi diagnostik ke VMSS
```
PS C:\> Add-AzureRmVmssDiagnosticsExtension -VirtualMachineScaleSet $VMSS -SettingFilePath $publicConfigPath -ProtectedSettingFilePath $privateConfigPath -Name $extName -TypeHandlerVersion $typeVersion -AutoUpgradeMinorVersion $True -Force
```

Perintah ini menambahkan ekstensi diagnostik ke VMSS.

## PARAMETERS

### -AutoUpgradeMinorVersion
Menunjukkan apakah cmdlet ini memungkinkan agen tamu Azure memperbarui ekstensi secara otomatis ke versi minor yang lebih baru.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtectedSettingFilePath
Menentukan jalur file konfigurasi privat.

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

### -SettingFilePath
Menentukan jalur file konfigurasi publik.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi yang akan digunakan untuk VMSS ini.
Untuk mendapatkan versi, jalankan cmdlet [Get-AzureRmVMExtensionImage](./Get-AzureRmVMExtensionImage.md) dengan nilai Microsoft.Azure.Diagnostics untuk parameter *PublisherName* dan IaaSDiagnostics untuk parameter *Tipe* .

```yaml
Type: String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Tentukan objek VMSS.
Anda dapat menggunakan cmdlet [New-AzureRmVmsConfig](./New-AzureRmVmssConfig.md) untuk membuat objek.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Add-AzureRmVmssExtension](./Add-AzureRmVmssExtension.md)

[Hapus-AzureRmVmssDiagnosticsExtension](./Remove-AzureRmVmssDiagnosticsExtension.md)

[Set-AzureRmVMDiagnosticsExtension](./Set-AzureRMVMDiagnosticsExtension.md)
