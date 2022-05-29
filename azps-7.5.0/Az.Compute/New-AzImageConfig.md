---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azimageconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzImageConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzImageConfig.md
ms.openlocfilehash: dedb4bc029abba162d6d74f668c9e5f521dacb62
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145734508"
---
# New-AzImageConfig

## SYNOPSIS
Membuat objek gambar yang dapat dikonfigurasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azimageconfig) untuk informasi terbaru.

## SYNTAX

```
New-AzImageConfig [[-Location] <String>] [-EdgeZone <String>] [[-Tag] <Hashtable>] [[-SourceVirtualMachineId] <String>]
 [[-OsDisk] <ImageOSDisk>] [-HyperVGeneration <String>] [-DataDisk <ImageDataDisk[]>] [-ZoneResilient]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzImageConfig** membuat objek gambar yang dapat dikonfigurasi.

## EXAMPLES

### Contoh 1
```powershell
$imageConfig = New-AzImageConfig -Location 'West US';
$osDiskVhdUri = "https://contoso.blob.core.windows.net/test/os.vhd"
$dataDiskVhdUri1 = "https://contoso.blob.core.windows.net/test/data1.vhd"
$dataDiskVhdUri2 = "https://contoso.blob.core.windows.net/test/data2.vhd"
Set-AzImageOsDisk -Image $imageConfig -OsType 'Windows' -OsState 'Generalized' -BlobUri $osDiskVhdUri;
Add-AzImageDataDisk -Image $imageConfig -Lun 1 -BlobUri $dataDiskVhdUri1;
Add-AzImageDataDisk -Image $imageConfig -Lun 2 -BlobUri $dataDiskVhdUri2;
New-AzImage -Image $imageConfig -ImageName 'ImageName01' -ResourceGroupName 'ResourceGroup01';
```

Perintah pertama membuat objek gambar, lalu menyimpannya dalam variabel $imageConfig.
Tiga perintah berikutnya menetapkan jalur disk os dan dua disk data ke variabel $osDiskVhdUri, $dataDiskVhdUri 1, dan $dataDiskVhdUri 2. Pendekatan ini hanya untuk keterbacaan perintah berikut.
Tiga perintah berikutnya masing-masing menambahkan disk os dan dua disk data ke gambar yang disimpan dalam $imageConfig.
URI setiap disk disimpan dalam $osDiskVhdUri, $dataDiskVhdUri 1, dan $dataDiskVhdUri 2.
Perintah akhir membuat gambar bernama 'ImageName01' di grup sumber daya 'ResourceGroup01'.

## PARAMETERS

### -DataDisk
Menentukan objek disk data.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.ImageDataDisk[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -HyperVGeneration
Menentukan Jenis HyperVGeneration untuk komputer virtual yang dibuat dari gambar.  Nilai yang diizinkan adalah V1 dan V2.

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

### -Lokasi
Menentukan lokasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EdgeZone
Mengatur nama zona tepi. Jika diatur, kueri akan dirutekan ke zona tepi yang ditentukan alih-alih wilayah utama.

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

### -OsDisk
Menentukan Disk sistem operasi.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.ImageOSDisk
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceVirtualMachineId
Menentukan ID komputer virtual sumber.

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

### -Tag
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneResilient
Aktifkan zona tangguh

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

### System.String

### System.Collections.Hashtable

### Microsoft.Azure.Management.Compute.Models.ImageOSDisk

### Microsoft.Azure.Management.Compute.Models.ImageDataDisk[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSImage

## NOTES

## RELATED LINKS
