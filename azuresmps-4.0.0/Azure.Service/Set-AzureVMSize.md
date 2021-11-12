---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 437889D1-F24F-4BBE-8C56-7C3E48CEA517
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22dce62d40bf06efebf3e407130e0f1f30ce3e73
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422445"
---
# Set-AzureVMSize

## SYNOPSIS
Mengatur ukuran komputer virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVMSize [-InstanceSize] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVMSize** memperbarui ukuran komputer virtual.
Alat ini memiliki dua parameter: *InstanceSize,* yang merupakan ukuran baru mesin virtual, dan *VM,* yaitu objek mesin virtual yang diambil menggunakan cmdlet **Get-AzureVM.**
Hasil **Set-AzureVMSize** dapat disambungkan ke cmdlet **Update-AzureVM** atau disimpan dalam variabel untuk penggunaan selanjutnya.
Tidak ada perubahan aktual yang **dilakukan hingga Update-AzureVM** dijalankan.

Catatan: Cmdlet ini akan meminta mesin virtual untuk penyediaan ulang dan mungkin akan mendapatkan alamat IP baru.

## EXAMPLES

### Contoh 1: Mengatur ukuran komputer virtual
```
PS C:\> Get-AzureVM -ServiceName "MySvc1" -Name "MyVM3" | Set-AzureVMSize "Small" | Update-AzureVM
```

Perintah ini memperbarui mesin virtual untuk ukuran "Kecil".

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceSize
Menentukan ukuran mesin virtual.

Nilai yang dapat diterima untuk parameter ini adalah:

--Extrasmall --Small --Medium --Large --ExtraLarge --A5 --A6 --A7

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual persisten yang telah ditetapkan cmdlet ini ukurannya.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVM](./Get-AzureVM.md)

[Update-AzureVM](./Update-AzureVM.md)


