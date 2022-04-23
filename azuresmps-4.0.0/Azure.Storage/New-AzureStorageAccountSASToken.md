---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: BCCBB05B-A5D7-4796-BE55-6BE5E18E07FC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5d0c7c3e589bf032856e50f41ee53f662ff4ce88
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143102547"
---
# New-AzureStorageAccountSASToken

## SYNOPSIS
Membuat token SAS.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorageAccountSASToken -Service <SharedAccessAccountServices>
 -ResourceType <SharedAccessAccountResourceTypes> [-Permission <String>] [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-Context <IStorageContext>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageSASToken** membuat token tanda tangan akses bersama (SAS) tingkat akun untuk akun Azure Storage.

Anda bisa menggunakan token SAS untuk mendelegasikan izin untuk beberapa layanan, atau untuk mendelegasikan izin untuk layanan yang tidak tersedia dengan token SAS tingkat objek.

## EXAMPLES

### Contoh 1: Membuat token SAS
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup"
```

Perintah ini membuat token SAS tingkat akun dengan izin penuh.

### Contoh 2: Membuat token SAS untuk rentang alamat IP
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -IPAddressOrRange 168.1.5.60-168.1.5.70
```

Perintah ini membuat token SAS untuk permintaan https saja dari rentang alamat IP tertentu.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat menggunakan cmdlet New-AzureStorageContext untuk mendapatkan objek **AzureStorageContext** .

```yaml
Type: IStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ExpiryTime
Menentukan waktu ketika tanda tangan akses bersama menjadi tidak valid.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressOrRange
Menentukan alamat IP atau rentang alamat IP yang menerima permintaan, seperti 168.1.5.65 atau 168.1.5.60-168.1.5.70.
Rentangnya inklusif.

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

### -Izin
Menentukan izin untuk akun Storage.
Izin hanya valid jika cocok dengan tipe sumber daya yang ditentukan.
Untuk informasi selengkapnya tentang nilai izin yang dapat diterima, lihat Menyusun Akun SAShttps://go.microsoft.com/fwlink/?LinkId=799514

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

### -Protokol
Menentukan protokol yang diizinkan untuk permintaan yang dibuat dengan AKUN SAS.
Nilai yang dapat diterima untuk parameter ini adalah:

- HttpsOnly
- HttpsOrHttp

Nilai defaultnya adalah HttpsOrHttp.

```yaml
Type: SharedAccessProtocol
Parameter Sets: (All)
Aliases: 
Accepted values: HttpsOnly, HttpsOrHttp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Menentukan tipe sumber daya yang tersedia dengan token SAS.
Nilai yang dapat diterima untuk parameter ini adalah:

- Tidak
- Layanan
- Wadah
- Objek

```yaml
Type: SharedAccessAccountResourceTypes
Parameter Sets: (All)
Aliases: 
Accepted values: None, Service, Container, Object

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Layanan
Menentukan layanan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Tidak
- Gumpalan
- File
- Antrian
- Meja

```yaml
Type: SharedAccessAccountServices
Parameter Sets: (All)
Aliases: 
Accepted values: None, Blob, File, Queue, Table

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu, sebagai objek **DateTime** , di mana SAS menjadi valid.
Untuk mendapatkan objek **DateTime** , gunakan cmdlet Get-Date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[AzureStorageBlobSASToken Baru](./New-AzureStorageBlobSASToken.md)

[AzureStorageContainerSASToken baru](./New-AzureStorageContainerSASToken.md)

[AzureStorageFileSASToken Baru](./New-AzureStorageFileSASToken.md)

[AzureStorage BaruQueueSASToken](./New-AzureStorageQueueSASToken.md)

[AzureStorageshareSASToken baru](./New-AzureStorageShareSASToken.md)

[AzureStorageTableSASToken baru](./New-AzureStorageTableSASToken.md)


