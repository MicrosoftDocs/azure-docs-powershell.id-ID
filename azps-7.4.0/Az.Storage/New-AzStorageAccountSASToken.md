---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: BCCBB05B-A5D7-4796-BE55-6BE5E18E07FC
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageaccountsastoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccountSASToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccountSASToken.md
ms.openlocfilehash: 5f11b66d05daca0002dfc92b07ff99342df7a6f3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144700880"
---
# New-AzStorageAccountSASToken

## SYNOPSIS
Membuat token SAS tingkat akun.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/new-azstorageaccountsastoken) untuk informasi terbaru.

## SYNTAX

```
New-AzStorageAccountSASToken -Service <SharedAccessAccountServices>
 -ResourceType <SharedAccessAccountResourceTypes> [-Permission <String>] [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-EncryptionScope <String>]
 [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageAccountSASToken** membuat token tanda tangan akses bersama (SAS) tingkat akun untuk akun Azure Storage.
Anda dapat menggunakan token SAS untuk mendelegasikan izin untuk beberapa layanan, atau untuk mendelegasikan izin untuk layanan yang tidak tersedia dengan token SAS tingkat objek.

## EXAMPLES

### Contoh 1: Membuat token SAS tingkat akun dengan izin penuh
```
PS C:\> New-AzStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup"
```

Perintah ini membuat token SAS tingkat akun dengan izin penuh.

### Contoh 2: Membuat token SAS tingkat akun untuk berbagai alamat IP dan EncryptionScope
```
PS C:\> New-AzStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -IPAddressOrRange 168.1.5.60-168.1.5.70 -EncryptionScope scopename
```

Perintah ini membuat token SAS tingkat akun untuk permintaan khusus HTTPS dari rentang alamat IP yang ditentukan, dengan EncryptionScope tertentu.

### Contoh 3: Membuat token SAS tingkat akun yang berlaku selama 24 jam
```
PS C:\> New-AzStorageAccountSASToken -Service Blob -ResourceType Service,Container,Object -Permission "rl" -ExpiryTime (Get-Date).AddDays(1)
```

Perintah ini membuat token SAS tingkat akun baca-saja yang berlaku selama 24 jam. 

## PARAMETERS

### -Context
Menentukan konteks penyimpanan Azure.
Anda dapat menggunakan cmdlet New-AzStorageContext untuk mendapatkan objek **AzureStorageContext** .

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionScope
Cakupan enkripsi untuk digunakan saat mengirim permintaan yang diotorisasi dengan URI SAS ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Menentukan waktu tanda tangan akses bersama menjadi tidak valid.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressOrRange
Menentukan alamat IP atau rentang alamat IP tempat menerima permintaan, seperti 168.1.5.65 atau 168.1.5.60-168.1.5.70.
Rentangnya inklusif.

```yaml
Type: System.String
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
Izin hanya valid jika cocok dengan jenis sumber daya yang ditentukan.
Penting untuk dicatat bahwa ini adalah string, seperti `rwd` (untuk Baca, Tulis, dan Hapus).
Untuk informasi selengkapnya tentang nilai izin yang dapat diterima, lihat Membuat SAS Akun http://go.microsoft.com/fwlink/?LinkId=799514

```yaml
Type: System.String
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
- HttpsOrHttp Nilai defaultnya adalah HttpsOrHttp.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Storage.SharedAccessProtocol]
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
Menentukan jenis sumber daya yang tersedia dengan token SAS.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- Layanan
- Kontainer
- Objek

```yaml
Type: Microsoft.Azure.Storage.SharedAccessAccountResourceTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, Service, Container, Object

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Menentukan layanan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- Blob
- File
- Antrean
- Tabel

```yaml
Type: Microsoft.Azure.Storage.SharedAccessAccountServices
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
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[New-AzStorageBlobSASToken](./New-AzStorageBlobSASToken.md)

[New-AzStorageContainerSASToken](./New-AzStorageContainerSASToken.md)

[New-AzStorageFileSASToken](./New-AzStorageFileSASToken.md)

[New-AzStorageQueueSASToken](./New-AzStorageQueueSASToken.md)

[New-AzStorageShareSASToken](./New-AzStorageShareSASToken.md)

[New-AzStorageTableSASToken](./New-AzStorageTableSASToken.md)


