---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: BCCBB05B-A5D7-4796-BE55-6BE5E18E07FC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4c86282a0a03ff503d6bd736d4e8f3e4444ad8c70e2c3d35db90fa76ef028bbc
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417660"
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
Cmdlet **New-AzureStorageSASToken** membuat token tanda tangan akses bersama (SAS, Shared Access Signature) tingkat akun untuk akun Azure Storage anda.

Anda dapat menggunakan token SAS untuk mendelegasikan izin untuk beberapa layanan, atau untuk mendelegasikan izin untuk layanan yang tidak tersedia dengan token SAS tingkat objek.

## EXAMPLES

### Contoh 1: Membuat token SAS
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup"
```

Perintah ini membuat token SAS tingkat akun dengan izin penuh.

### Contoh 2: Buat token SAS untuk berbagai alamat IP
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -IPAddressOrRange 168.1.5.60-168.1.5.70
```

Perintah ini membuat token SAS untuk permintaan HTTPS-only dari rentang alamat IP yang ditentukan.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat menggunakan cmdlet New-AzureStorageContext untuk mendapatkan objek **AzureStorageContext.**

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
Menentukan waktu di mana tanda tangan akses bersama menjadi tidak valid.

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
Menentukan alamat IP atau rentang alamat IP untuk menerima permintaan, seperti 168.1.5.65 atau 168.1.5.60-168.1.5.70.
Rentang bersifat inklusif.

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

### -Permission
Menentukan izin untuk Storage Anda.
Izin hanya valid jika sesuai dengan tipe sumber daya yang ditentukan.
Untuk informasi selengkapnya tentang nilai izin yang dapat diterima, lihat Membangun SAS Akunhttps://go.microsoft.com/fwlink/?LinkId=799514

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

### -Protocol
Menentukan protokol yang diizinkan untuk permintaan yang dibuat dengan akun SAS.
Nilai yang dapat diterima untuk parameter ini adalah:

- HttpsOnly
- HttpsOrhttp

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

- Tidak ada
- Layanan
- Container
- Object

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

- Tidak ada
- Blob
- File
- Antrean
- Tabel

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
Menentukan waktu, sebagai objek **DateTime,** ketika SAS menjadi valid.
Untuk mendapatkan objek **DateTime,** gunakan cmdlet Get-Date.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-AzureStorageBlobSASToken](./New-AzureStorageBlobSASToken.md)

[New-AzureStorageContainerSASToken](./New-AzureStorageContainerSASToken.md)

[New-AzureStorageFileSASToken](./New-AzureStorageFileSASToken.md)

[New-AzureStorageQueueSASToken](./New-AzureStorageQueueSASToken.md)

[New-AzureStorageShareSASToken](./New-AzureStorageShareSASToken.md)

[New-AzureStorageTableSASToken](./New-AzureStorageTableSASToken.md)


