---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: C453485D-67A7-480E-83F6-527D4F5EBC93
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMDataDisk.md
ms.openlocfilehash: 156268571864f9ec2193b8560bd4bf2e08bd52d9
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145976071"
---
# Set-AzVMDataDisk

## SYNOPSIS
Memodifikasi properti disk data komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmdatadisk) untuk informasi terbaru.

## SYNTAX

### ChangeWithName
```
Set-AzVMDataDisk [-VM] <PSVirtualMachine> [-Name] <String> [[-Caching] <CachingTypes>]
 [[-DiskSizeInGB] <Int32>] [-StorageAccountType <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ChangeWithLun
```
Set-AzVMDataDisk [-VM] <PSVirtualMachine> [-Lun] <Int32> [[-Caching] <CachingTypes>] [[-DiskSizeInGB] <Int32>]
 [-StorageAccountType <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMDataDisk** memodifikasi properti disk data komputer virtual.

## EXAMPLES

### Contoh 1: Mengubah mode penembolokan disk data
```powershell
$VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07"
Set-AzVMDataDisk -VM $VM -Name "DataDisk01" -Caching ReadWrite | Update-AzVM
```

Perintah pertama mendapatkan komputer virtual bernama ContosoVM07 dengan menggunakan **Get-AzVM**.
Perintah menyimpannya dalam variabel $VM.
Perintah kedua memodifikasi mode penembolokan untuk disk data bernama DataDisk01 pada komputer virtual di $VM.
Perintah meneruskan hasil ke cmdlet Update-AzVM, yang mengimplementasikan perubahan Anda.
Perubahan pada mode kasir menyebabkan komputer virtual dimulai ulang.

### Contoh 2

Memodifikasi properti disk data komputer virtual. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzVMDataDisk -Caching None -Lun 1 -VM <PSVirtualMachine>
```

## PARAMETERS

### -Penembolokan
Menentukan mode penembolokan disk.
Nilai yang dapat diterima untuk parameter ini adalah:
- ReadOnly
- ReadWrite Nilai defaultnya adalah ReadWrite.
Mengubah nilai ini menyebabkan komputer virtual dimulai ulang.
Pengaturan ini memengaruhi konsistensi dan performa disk.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.CachingTypes]
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: 2
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

### -DiskEncryptionSetId
Menentukan ID sumber daya dari kumpulan enkripsi disk yang dikelola pelanggan.  Ini hanya dapat ditentukan untuk disk terkelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInGB
Menentukan ukuran, dalam gigabyte, untuk disk data.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lun
Menentukan nomor unit logis (LUN) dari disk data yang dimodifikasi cmdlet ini.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: ChangeWithLun
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama disk data yang diubah cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ChangeWithName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountType
Jenis akun disk yang dikelola komputer virtual.

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

### -VM
Menentukan komputer virtual yang cmdlet ini memodifikasi disk data.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet Get-AzVM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk data.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[Microsoft.Azure.Management.Compute.Models.CachingTypes, Microsoft.Azure.Management.Compute, Version=23.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Dapatkan-AzVM](./Get-AzVM.md)

[Update-AzVM](./Update-AzVM.md)


