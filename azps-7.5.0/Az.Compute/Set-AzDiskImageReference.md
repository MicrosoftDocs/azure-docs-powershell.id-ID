---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azdiskimagereference
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzDiskImageReference.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzDiskImageReference.md
ms.openlocfilehash: 6beb6677ae6cfe6494c34c88f11ccef0ac67643d
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145808142"
---
# Set-AzDiskImageReference

## SYNOPSIS
Mengatur properti referensi gambar pada objek disk.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azdiskimagereference) untuk informasi terbaru.

## SYNTAX

```
Set-AzDiskImageReference [-Disk] <PSDisk> [[-Id] <String>] [[-Lun] <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDiskImageReference** mengatur properti referensi gambar pada objek disk.

## EXAMPLES

### Contoh 1
```powershell
$diskconfig = New-AzDiskConfig -Location "East US" -DiskSizeGB 10 -AccountType Premium_LRS -OsType Windows -CreateOption FromImage
$image = '/Subscriptions/00000000-0000-0000-0000-000000000000/Providers/Microsoft.Compute/Locations/westeurope/Publishers/MicrosoftWindowsDesktop/ArtifactTypes/VMImage/Offers/Windows-10/Skus/win10-21h2-avd-g2/Versions/19044.1526.220204'
$diskconfig = Set-AzDiskImageReference -Disk $diskconfig -Id $image -Lun 0
New-AzDisk -ResourceGroupName 'ResourceGroup01' -DiskName 'Disk01' -Disk $diskconfig
```

Perintah pertama membuat objek disk lokal dengan ukuran 10GB dalam jenis akun penyimpanan Premium_LRS.  Ini juga menetapkan jenis OS Windows.
Perintah kedua mengatur id gambar dan unit logis nomor 0 untuk objek disk.
Perintah terakhir mengambil objek disk dan membuat disk dengan nama 'Disk01' di grup sumber daya 'ResourceGroup01'.

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

### -Disk
Menentukan objek disk lokal.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSDisk
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Id
Menentukan ID PIR atau gambar pengguna.

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

### -Lun
Menentukan nomor unit logis (LUN). Jika disk dibuat dari disk data gambar, ini adalah indeks yang menunjukkan disk data mana dalam gambar yang akan digunakan. Untuk disk OS, bidang ini null.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSDisk

### System.String

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSDisk

## NOTES

## RELATED LINKS
