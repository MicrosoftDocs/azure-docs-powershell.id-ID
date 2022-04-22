---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: BDF42420-3616-4A64-9562-1A896F828728
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/new-azurestoragesharesastoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageShareSASToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageShareSASToken.md
ms.openlocfilehash: e6223e1ee46dc94e56a93a560473474930188965
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142989054"
---
# New-AzureStorageShareSASToken

## SYNOPSIS
Menghasilkan token Tanda Tangan Akses Bersama untuk berbagi Azure Storage.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SasPolicy
```
New-AzureStorageShareSASToken [-ShareName] <String> -Policy <String> [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SasPermission
```
New-AzureStorageShareSASToken [-ShareName] <String> [-Permission <String>] [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageShareSASToken** menghasilkan token tanda tangan akses bersama untuk berbagi Azure Storage.

## EXAMPLES

### Contoh 1: Membuat token tanda tangan akses bersama untuk berbagi
```
PS C:\>New-AzureStorageShareSASToken -ShareName "ContosoShare" -Permission "rwdl"
```

Perintah ini membuat token tanda tangan akses bersama untuk berbagi bernama ContosoShare.

### Contoh 2: Menghasilkan beberapa token tanda tangan akses bersama menggunakan pipeline
```
PS C:\>Get-AzureStorageShare -Prefix "test" | New-AzureStorageShareSASToken -Permission "rwdl"
```

Perintah ini mendapatkan semua Storage berbagi yang cocok dengan uji prefiks.
Perintah meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini membuat token akses bersama untuk setiap Storage berbagi yang memiliki izin yang ditentukan.

### Contoh 3: Membuat token tanda tangan akses bersama yang menggunakan kebijakan akses bersama
```
PS C:\>New-AzureStorageShareSASToken -ShareName "ContosoShare" -Policy "ContosoPolicy03"
```

Perintah ini membuat token tanda tangan akses bersama untuk Storage berbagi bernama ContosoShare yang memiliki kebijakan bernama ContosoPolicy03.

## PARAMETERS

### -Konteks
Menentukan konteks Azure Storage.
Untuk mendapatkan konteks, gunakan cmdlet New-AzureStorageContext.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Menentukan waktu ketika tanda tangan akses bersama menjadi tidak valid.

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

### -FullUri
Menunjukkan bahwa cmdlet ini mengembalikan URI blob penuh dan token tanda tangan akses bersama.

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

### -IPAddressOrRange
Menentukan alamat IP atau rentang alamat IP yang menerima permintaan, seperti 168.1.5.65 atau 168.1.5.60-168.1.5.70.
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
Menentukan izin dalam token untuk mengakses berbagi dan file di bawah berbagi.
Penting untuk diperhatikan bahwa ini adalah string, seperti `rwd` (untuk Baca, Tulis, dan Hapus).

```yaml
Type: System.String
Parameter Sets: SasPermission
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Menentukan kebijakan akses yang disimpan untuk berbagi.

```yaml
Type: System.String
Parameter Sets: SasPolicy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Menentukan protokol yang diizinkan untuk permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:
* HttpsOnly
* HttpsOrHttp The default value is HttpsOrHttp.

```yaml
Type: System.Nullable`1[Microsoft.WindowsAzure.Storage.SharedAccessProtocol]
Parameter Sets: (All)
Aliases:
Accepted values: HttpsOnly, HttpsOrHttp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareName
Menentukan nama berbagi Storage.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu ketika tanda tangan akses bersama menjadi valid.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.String

## NOTES
* Kata kunci: umum, azure, layanan, data, penyimpanan, blob, antrean, tabel

## RELATED LINKS

[Get-AzureStorageShare](./Get-AzureStorageShare.md)

[AzureStorageFileSASToken Baru](./New-AzureStorageFileSASToken.md)
