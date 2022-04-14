---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 979E956B-4C74-426E-A617-E50C4EBC8A20
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/disable-azurermvmdiskencryption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Disable-AzureRmVMDiskEncryption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Disable-AzureRmVMDiskEncryption.md
ms.openlocfilehash: b21dc9d2485d7f2473beec5b0953db2b699b1d6c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141844413"
---
# Disable-AzureRmVMDiskEncryption

## SYNOPSIS
Menonaktifkan enkripsi pada mesin virtual IaaS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Disable-AzureRmVMDiskEncryption [-ResourceGroupName] <String> [-VMName] <String> [[-VolumeType] <String>]
 [[-Name] <String>] [[-TypeHandlerVersion] <String>] [-Force] [-DisableAutoUpgradeMinorVersion]
 [-ExtensionType <String>] [-ExtensionPublisherName <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzureRmVMDiskEncryption** menonaktifkan enkripsi pada infrastruktur sebagai mesin virtual layanan (IaaS).
Cmdlet ini hanya didukung pada mesin virtual Windows dan bukan mesin virtual Linux.
Cmdlet ini menginstal ekstensi pada mesin virtual untuk menonaktifkan enkripsi.
Jika parameter *Nama* tidak ditentukan, ekstensi dengan nama default "AzureDiskEncryption untuk Windows VM" akan dibuat.
Perhatian: Cmdlet ini melakukan boot ulang mesin virtual.

## EXAMPLES

### Contoh 1: Menonaktifkan enkripsi untuk semua volume pada mesin virtual Windows
```
PS C:\> Disable-AzureRMVMDiskEncryption -ResourceGroupName "Group001" -VMName "VM002"
```

Perintah ini menonaktifkan enkripsi untuk volume tipe semua untuk mesin virtual bernama VM002 yang termasuk dalam grup sumber daya bernama Group001.
Karena parameter *VolumeType* tidak ditentukan, cmdlet mengatur nilai ke Semua.

### Contoh 2: Menonaktifkan enkripsi untuk volume data di mesin virtual Windows
```
PS C:\> $ResourceGroup = "Group002";
PS C:\> $VMName = "VM004";
PS C:\> Disable-AzureRMVMDiskEncryption -ResourceGroupName "Group002" -VMName "VM004" -VolumeType "Data"
```

Perintah ini menonaktifkan enkripsi untuk volume data tipe untuk mesin virtual bernama VM004 yang termasuk dalam grup sumber daya bernama Group002.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoUpgradeMinorVersion
Menunjukkan bahwa cmdlet ini menonaktifkan pemutakhiran otomatis dari versi minor ekstensi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExtensionPublisherName
Nama penerbit ekstensi. Tentukan parameter ini hanya untuk menimpa nilai default "Microsoft.Azure.Security".

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

### -ExtensionType
Tipe ekstensi. Tentukan parameter ini untuk menimpa nilai default "AzureDiskEncryption" untuk Windows VM dan "AzureDiskEncryptionForLinux" untuk VM Linux.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Nama
Menspekuifikasikan nama sumber daya Azure Resource Manager (ARM) yang mewakili ekstensi.
Jika parameter ini tidak ditentukan, cmdlet ini akan menjadi "AzureDiskEncryption untuk Windows VM".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi enkripsi.
Jika Anda tidak menentukan nilai untuk parameter ini, versi ekstensi terbaru akan digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual tempat cmdlet ini menonaktifkan enkripsi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumeType
Menentukan tipe volume mesin virtual untuk melakukan operasi enkripsi.
Untuk mesin virtual Windows, nilai yang valid adalah: 
- Semua
- OS
- Data.
Jika Anda tidak menentukan nilai untuk parameter ini, nilai defaultnya adalah Semua.
Enkripsi non-fungsikan saat ini tidak didukung untuk Linux.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: OS, Data, All

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureRmVMDiskEncryptionStatus](./Get-AzureRmVMDiskEncryptionStatus.md)

[Remove-AzureRmVMDiskEncryptionExtension](./Remove-AzureRmVMDiskEncryptionExtension.md)

[Set-AzureRmVMDiskEncryptionExtension](./Set-AzureRmVMDiskEncryptionExtension.md)


