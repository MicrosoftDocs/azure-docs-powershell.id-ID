---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 979E956B-4C74-426E-A617-E50C4EBC8A20
online version: https://docs.microsoft.com/powershell/module/az.compute/disable-azvmdiskencryption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Disable-AzVMDiskEncryption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Disable-AzVMDiskEncryption.md
ms.openlocfilehash: b30e3853a6f6b3ee3c4c9f16f6eb338ed3914b4a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144637424"
---
# Disable-AzVMDiskEncryption

## SYNOPSIS
Menonaktifkan enkripsi pada komputer virtual IaaS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/disable-azvmdiskencryption) untuk informasi terbaru.

## SYNTAX

```
Disable-AzVMDiskEncryption [-ResourceGroupName] <String> [-VMName] <String> [[-VolumeType] <String>]
 [[-Name] <String>] [[-TypeHandlerVersion] <String>] [-Force] [-DisableAutoUpgradeMinorVersion]
 [-ExtensionType <String>] [-ExtensionPublisherName <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzVMDiskEncryption** menonaktifkan enkripsi pada komputer virtual infrastruktur sebagai layanan (IaaS).
Cmdlet ini hanya didukung pada komputer virtual Windows dan bukan komputer virtual Linux.
Cmdlet ini menginstal ekstensi pada komputer virtual untuk menonaktifkan enkripsi.
Jika parameter *Nama* tidak ditentukan, ekstensi dengan nama default "AzureDiskEncryption for Windows VM" dibuat.
Perhatian: Cmdlet ini me-reboot komputer virtual.

## EXAMPLES

### Contoh 1: Menonaktifkan enkripsi untuk semua volume pada komputer virtual Windows
```powershell
Disable-AzVMDiskEncryption -ResourceGroupName "Group001" -VMName "VM002"
```

Perintah ini menonaktifkan enkripsi untuk volume jenis semua untuk komputer virtual bernama VM002 yang termasuk dalam grup sumber daya bernama Group001.
Karena parameter *VolumeType* tidak ditentukan, cmdlet mengatur nilai ke Semua.

### Contoh 2: Menonaktifkan enkripsi untuk volume data pada komputer virtual Windows
```powershell
$ResourceGroup = "Group002"
$VMName = "VM004"
$VolumeType = "Data"
Disable-AzVMDiskEncryption -ResourceGroupName $ResourceGroup -VMName $VMName -VolumeType $VolumeType
```

Perintah ini menonaktifkan enkripsi untuk volume data jenis untuk komputer virtual bernama VM004 yang termasuk dalam grup sumber daya bernama Group002.

## PARAMETERS

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

### -DisableAutoUpgradeMinorVersion
Menunjukkan bahwa cmdlet ini menonaktifkan peningkatan otomatis versi minor ekstensi.

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
Nama penerbit ekstensi. Tentukan parameter ini hanya untuk mengambil alih nilai default "Microsoft.Azure.Security".

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
Jenis ekstensi. Tentukan parameter ini untuk mengambil alih nilai default "AzureDiskEncryption" untuk VM Windows dan "AzureDiskEncryptionForLinux" untuk VM Linux.

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

### -Force
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

### -Name
Menentukan nama sumber daya Azure Resource Manager (ARM) yang mewakili ekstensi.
Jika parameter ini tidak ditentukan, cmdlet ini default ke "AzureDiskEncryption for Windows VM".

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
Menentukan nama grup sumber daya komputer virtual.

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
Jika Anda tidak menentukan nilai untuk parameter ini, versi terbaru ekstensi akan digunakan.

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
Menentukan nama komputer virtual tempat cmdlet ini menonaktifkan enkripsi.

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
Menentukan jenis volume komputer virtual untuk melakukan operasi enkripsi.
Untuk komputer virtual Windows, nilai yang valid adalah: 
- Semua
- OS
- Data.
Jika Anda tidak menentukan nilai untuk parameter ini, nilai defaultnya adalah Semua.
Nonaktifkan enkripsi saat ini tidak didukung untuk Linux.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzVMDiskEncryptionStatus](./Get-AzVMDiskEncryptionStatus.md)

[Remove-AzVMDiskEncryptionExtension](./Remove-AzVMDiskEncryptionExtension.md)

[Set-AzVMDiskEncryptionExtension](./Set-AzVMDiskEncryptionExtension.md)


