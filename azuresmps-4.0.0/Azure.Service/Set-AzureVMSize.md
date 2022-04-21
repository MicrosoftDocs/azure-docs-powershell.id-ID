---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 437889D1-F24F-4BBE-8C56-7C3E48CEA517
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22dce62d40bf06efebf3e407130e0f1f30ce3e73
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787145"
---
# Set-AzureVMSize

## SYNOPSIS
Mengatur ukuran mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVMSize [-InstanceSize] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVMSize memperbarui** ukuran mesin virtual.
Ini memiliki dua parameter: *InstanceSize*, yang merupakan ukuran baru mesin virtual, dan *VM*, yang merupakan objek mesin virtual yang diambil dengan menggunakan cmdlet **Get-AzureVM** .
Hasil **Dari Set-AzureVMSize dapat disalurkan** ke cmdlet **Update-AzureVM** atau disimpan dalam variabel untuk digunakan nanti.
Tidak ada perubahan aktual yang dilakukan hingga **Pembaruan-AzureVM** dijalankan.

Catatan: Cmdlet ini akan mengharuskan mesin virtual untuk disediakan ulang dan mungkin mendapatkan alamat IP baru.

## EXAMPLES

### Contoh 1: Mengatur ukuran mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "MySvc1" -Name "MyVM3" | Set-AzureVMSize "Small" | Update-AzureVM
```

Perintah ini memperbarui mesin virtual untuk ukuran "Kecil".

## PARAMETERS

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

### -Instancesize
Menentukan ukuran mesin virtual.

Nilai yang dapat diterima untuk parameter ini adalah:

--Extrasmall --small --medium --large --extralarge --A5 --A6 --A7

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
Menentukan objek mesin virtual persisten yang cmdlet ini atur ukurannya.

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

[Get-AzureVM](./Get-AzureVM.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


