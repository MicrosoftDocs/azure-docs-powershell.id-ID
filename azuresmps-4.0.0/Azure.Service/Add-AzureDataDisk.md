---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: FDEDBF4F-7507-43FF-A983-7E431C0C1950
online version: ''
schema: 2.0.0
ms.openlocfilehash: 40ff4b075cb01e1478586d0e634feb859b3660a3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142788904"
---
# Add-AzureDataDisk

## SYNOPSIS
Menambahkan disk data ke mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### CreateNew (Default)
```
Add-AzureDataDisk [-CreateNew] [-DiskSizeInGB] <Int32> [-DiskLabel] <String> [-LUN] <Int32>
 [-MediaLocation <String>] [-HostCaching <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Impor
```
Add-AzureDataDisk [-Import] [-DiskName] <String> [-LUN] <Int32> [-HostCaching <String>] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ImporDari
```
Add-AzureDataDisk [-ImportFrom] [-DiskLabel] <String> [-LUN] <Int32> -MediaLocation <String>
 [-HostCaching <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureDataDisk** menambahkan disk data baru atau yang sudah ada ke objek mesin virtual Azure.
Gunakan parameter *CreateNew* untuk membuat disk data baru yang memiliki ukuran dan label tertentu.
Gunakan parameter *Impor* untuk melampirkan disk yang sudah ada dari penyimpanan gambar.
Gunakan parameter *ImportFrom* untuk melampirkan disk yang sudah ada dari blob dalam akun penyimpanan.
Anda bisa menentukan mode host-cache disk data yang terlampir.

## EXAMPLES

### Contoh 1: Mengimpor disk data dari repository
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Add-AzureDataDisk -Import -DiskName "Disk68" -LUN 0 | Update-AzureVM
```

Perintah ini mendapatkan objek mesin virtual untuk mesin virtual bernama VirtualMachine07 di layanan cloud ContosoService dengan menggunakan cmdlet **Get-AzureVM** .
Perintah meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Perintah tersebut melampirkan disk data yang sudah ada dari repository ke mesin virtual.
Disk data memiliki LUN 0.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda menggunakan cmdlet **Update-AzureVM** .

### Contoh 2: Menambahkan disk data baru
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine08" | Add-AzureDataDisk -CreateNew -DiskSizeInGB 128 -DiskLabel "main" -LUN 0 | Update-AzureVM
```

Perintah ini mendapatkan objek mesin virtual untuk mesin virtual bernama VirtualMachine08.
Perintah melewatinya ke cmdlet saat ini.
Perintah tersebut melampirkan disk data baru bernama MyNewDisk.vhd.
Cmdlet membuat disk dalam wadah vhds dalam akun penyimpanan default langganan saat ini.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda.

### Contoh 3: Menambahkan disk data dari lokasi tertentu
```
PS C:\> Get-AzureVM "ContosoService" -Name "Database" | Add-AzureDataDisk -ImportFrom -MediaLocation "https://contosostorage.blob.core.windows.net/container07/Disk14.vhd" -DiskLabel "main" -LUN 0 | Update-AzureVM
```

Perintah ini mendapatkan objek mesin virtual untuk mesin virtual bernama Database.
Perintah melewatinya ke cmdlet saat ini.
Perintah tersebut melampirkan disk data yang sudah ada bernama Disk14.vhd dari lokasi yang ditentukan.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda.

## PARAMETERS

### -CreateNew
Menunjukkan bahwa cmdlet ini membuat disk data.

```yaml
Type: SwitchParameter
Parameter Sets: CreateNew
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskLabel
Menentukan label disk untuk disk data baru.

```yaml
Type: String
Parameter Sets: CreateNew, ImportFrom
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskName
Menentukan nama disk data dalam penyimpanan disk.

```yaml
Type: String
Parameter Sets: Import
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskSizeInGB
Menentukan ukuran disk logika, dalam gigabyte, untuk disk data baru.

```yaml
Type: Int32
Parameter Sets: CreateNew
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostCaching
Menentukan setelan cache tingkat host disk.
Nilai yang valid adalah: 

- Tidak 
- ReadOnly 
- ReadWrite

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Impor
Menunjukkan bahwa cmdlet ini mengimpor disk data yang sudah ada dari penyimpanan gambar.

```yaml
Type: SwitchParameter
Parameter Sets: Import
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImporDari
Menunjukkan bahwa cmdlet ini mengimpor disk data yang sudah ada dari blob dalam akun penyimpanan.

```yaml
Type: SwitchParameter
Parameter Sets: ImportFrom
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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

### -LUN
Menentukan nomor unit logika (LUN) untuk drive data di mesin virtual.
Nilai yang valid adalah: 0 hingga 15.
Setiap disk data harus memiliki LUN yang unik.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaLokasi
Menentukan lokasi blob dalam akun penyimpanan Azure tempat cmdlet ini menyimpan disk data.
Jika Anda tidak menentukan lokasi, cmdlet menyimpan disk data dalam wadah vhds di akun penyimpanan default untuk langganan saat ini.
Jika wadah vhds tidak ada, cmdlet membuat wadah vhds.

```yaml
Type: String
Parameter Sets: CreateNew
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ImportFrom
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan objek mesin virtual tempat cmdlet ini melampirkan disk data.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM** .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Get-AzureVM](./Get-AzureVM.md)

[Hapus-AzureDataDisk](./Remove-AzureDataDisk.md)

[Set-AzureDataDisk](./Set-AzureDataDisk.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


