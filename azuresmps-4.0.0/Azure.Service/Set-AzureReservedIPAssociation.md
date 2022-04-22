---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 3249E908-B1D9-4707-844D-168274F1A466
online version: ''
schema: 2.0.0
ms.openlocfilehash: dc2f37125150ed56e7aba9a304bc36199e5af3de
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915787"
---
# Set-AzureReservedIPAssociation

## SYNOPSIS
Mengaitkan alamat IP khusus dengan mesin virtual atau layanan cloud yang sudah ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureReservedIPAssociation [-ReservedIPName] <String> [-ServiceName] <String> [[-VirtualIPName] <String>]
 [[-Slot] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureReservedIPAssociation** mengaitkan alamat IP khusus dengan alamat IP Virtual (VIP) mesin virtual yang berjalan atau layanan cloud.
Alamat IP khusus tidak boleh digunakan pada saat invokasi cmdlet ini, dan harus berada di wilayah yang sama dengan mesin virtual atau layanan awan.

Operasi ini membutuhkan waktu sekitar 30 detik untuk diselesaikan, setelah itu mesin virtual atau layanan dapat diakses menggunakan alamat IP khusus.

## EXAMPLES

### Contoh 1: Mengatur asosiasi IP khusus
```
PS C:\> Set-AzureReservedIPAssociation -ReservedIPName "ResIp14" -ServiceName "PipTestWestEurope"
```

Perintah ini menetapkan alamat IP khusus bernama ResIp14 ke layanan PipTestWestEurope.
ResIp14 adalah IP khusus di kawasan Eropa Barat.

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

### -ReservedIPName
Menentukan nama alamat IP khusus untuk dikaitkan dengan mesin atau layanan virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan yang memiliki penyebaran untuk mengaitkan alamat IP khusus.

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

### -Slot
Menentukan slot penyebaran.
Nilai yang dapat diterima untuk parameter ini adalah:

- Pementasan
- Produksi

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualIPName
Menentukan nama VIP yang sudah ada untuk dikaitkan dengan IP khusus.
Lihat Add-AzureVirtualIP untuk menambahkan VIP ke layanan awan Anda.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Common.ManagementOperationContext

## NOTES

## RELATED LINKS

[Hapus-AzureReservedIPAssociation](./Remove-AzureReservedIPAssociation.md)


