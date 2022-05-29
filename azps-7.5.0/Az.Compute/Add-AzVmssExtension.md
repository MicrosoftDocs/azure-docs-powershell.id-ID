---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 7EC166C7-151D-4DA0-9B10-165E735D4F12
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmssextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssExtension.md
ms.openlocfilehash: cb85b9ffbdbc3fde3223a97bd89a88a871e90f88
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145772747"
---
# Tambahkan-EkstensiAzVmss

## SYNOPSIS
Menambahkan ekstensi ke VMSS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmssextension) untuk informasi terbaru.

## SYNTAX

```
Add-AzVmssExtension [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-Name] <String>]
 [[-Publisher] <String>] [[-Type] <String>] [[-TypeHandlerVersion] <String>]
 [[-AutoUpgradeMinorVersion] <Boolean>] [[-Setting] <Object>] [[-ProtectedSetting] <Object>]
 [-EnableAutomaticUpgrade <Boolean>] [-ForceUpdateTag <String>] [-ProvisionAfterExtension <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVmssExtension** menambahkan ekstensi ke Virtual Machine Scale Set (VMSS).

## EXAMPLES

### Contoh 1: Menambahkan ekstensi ke VMSS
```powershell
Add-AzVmssExtension -VirtualMachineScaleSet $VMSS -Name $ExtName -Publisher $Publisher -Type $ExtType -TypeHandlerVersion $ExtVer -AutoUpgradeMinorVersion $True
```

Perintah ini menambahkan ekstensi ke VMSS.

### Contoh 2: Menambahkan ekstensi ke VMSS dengan pengaturan dan pengaturan yang dilindungi
```powershell
$Settings = @{"fileUris" = "[]"; "commandToExecute" = ""};
$ProtectedSettings = @{"storageAccountName" = $stoname; "storageAccountKey" = $stokey};

Add-AzVmssExtension -VirtualMachineScaleSet $vmss -Name $vmssExtensionName -Publisher $vmssPublisher  `
  -Type $vmssExtensionType -TypeHandlerVersion $ExtVer -AutoUpgradeMinorVersion $True  `
  -Setting $Settings -ProtectedSetting $ProtectedSettings
```

### Contoh 3: Menambahkan ekstensi ke VMSS dengan pengaturan dan pengaturan yang dilindungi
```powershell
$BatchFile = "runbook.sh"
$ResourceGroupName = "HelloRG"
$VMScaleSetName = "HelloVmSS"
$TypeHandlerVersion = 2.1

#Best Practice for securd paramaters.
$protectedSettings = @{
"managedIdentity" = @{ "clientId" = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"};
}

$publicSettings = @{ 
"fileUris"= (,"https://storage.blob.core.windows.net/itfiles/$($BatchFile)");
"commandToExecute"= "sh $($BatchFile)"
}

# Get information about the scale set
$vmss = Get-AzVmss `
            -ResourceGroupName $ResourceGroupName `
            -VMScaleSetName $VMScaleSetName

Add-AzVmssExtension -VirtualMachineScaleSet $vmss `
    -Name "CustomScript" `
    -Publisher "Microsoft.Azure.Extensions" `
    -Type "CustomScript" `
    -TypeHandlerVersion $TypeHandlerVersion `
    -AutoUpgradeMinorVersion $true `
    -Setting $publicSettings `
    -ProtectedSetting $protectedSettings

Update-AzVmss `
    -ResourceGroupName $ResourceGroupName `
    -Name $VMScaleSetName `
    -VirtualMachineScaleSet $vmss
```

Perintah ini menambahkan ekstensi ke VMSS dengan contoh skrip bash pada penyimpanan blob, menentukan url penyimpanan blob dan perintah yang dapat dieksekusi dalam pengaturan dan akses keamanan dalam pengaturan yang dilindungi. 

## PARAMETERS

### -AutoUpgradeMinorVersion
Menunjukkan apakah versi ekstensi harus diperbarui secara otomatis ke versi minor yang lebih baru.

```yaml
Type: System.Nullable`1[System.Boolean]
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutomaticUpgrade
Menunjukkan apakah ekstensi harus ditingkatkan secara otomatis oleh platform jika ada versi ekstensi yang lebih baru yang tersedia.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceUpdateTag
Jika nilai disediakan dan berbeda dari nilai sebelumnya, handler ekstensi akan dipaksa untuk memperbarui meskipun konfigurasi ekstensi tidak berubah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama ekstensi yang ditambahkan cmdlet ini.

```yaml
Type: System.String
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
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProvisionAfterExtension
Kumpulan nama ekstensi setelah ekstensi ini perlu disediakan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Menentukan nama penerbit ekstensi.
Penerbit memberikan nama saat penerbit mendaftarkan ekstensi.
Ini dapat menggunakan cmdlet [Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md) untuk mendapatkan penerbit.

```yaml
Type: System.String
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
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Menentukan jenis ekstensi.
Anda dapat menggunakan cmdlet [Get-AzVMExtensionImageType](./Get-AzVMExtensionImageType.md) untuk mendapatkan jenis ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi yang akan digunakan untuk komputer virtual ini.
Anda dapat menggunakan cmdlet [Get-AzVMExtensionImage](./Get-AzVMExtensionImage.md) untuk mendapatkan versi ekstensi.

```yaml
Type: System.String
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
Anda dapat menggunakan [New-AzVmssConfig](./New-AzVmssConfig.md) untuk membuat objek.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.String

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Object

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Remove-AzVmssExtension](./Remove-AzVmssExtension.md)

[Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md)

[Get-AzVMExtensionImageType](./Get-AzVMExtensionImageType.md)

[Get-AzVMExtensionImage](./Get-AzVMExtensionImage.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)
