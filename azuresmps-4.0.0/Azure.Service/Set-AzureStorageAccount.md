---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: EB4A7F84-99E4-49B1-856D-EC0736058D23
online version: ''
schema: 2.0.0
ms.openlocfilehash: 89776bd919e9b8867983f5d00ede9de9901c985e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142722808"
---
# Set-AzureStorageAccount

## SYNOPSIS
Memperbarui properti akun penyimpanan dalam langganan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### AccountType (Default)
```
Set-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 [-Type <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### GeoReplicationEnabled
```
Set-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 [-GeoReplicationEnabled <Boolean>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorageAccount** memperbarui properti akun penyimpanan Azure dalam langganan saat ini.
Properti yang dapat diatur adalah: **Label**, **Deskripsi**, **Tipe** , dan **GeoReplicationEnabled**.

## EXAMPLES

### Contoh 1: Memperbarui label untuk akun penyimpanan
```
PS C:\> Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -Label "ContosoAccnt" -Description "Contoso storage account"
```

Perintah ini memperbarui properti **Label** dan **Deskripsi** untuk akun penyimpanan bernama ContosoStorage01.

### Contoh 2: Mengaktifkan geo-replikasi untuk akun penyimpanan
```
PS C:\> Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -GeoReplicationEnabled $False
```

Perintah ini mengatur properti **GeoReplicationEnabled** ke $False untuk akun penyimpanan bernama ContosoStorage01.

### Contoh 3: Menonaktifkan geo-replikasi untuk akun penyimpanan
```
PS C:\> Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -GeoReplicationEnabled $True
```

Perintah ini mengatur properti **GeoReplicationEnabled** ke $True untuk akun penyimpanan bernama ContosoStorage01.

## PARAMETERS

### -Deskripsi
Menentukan deskripsi untuk akun penyimpanan.
Deskripsi mungkin panjangnya hingga 1024 karakter.

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

### -GeoReplicationEnabled
Menentukan apakah akun penyimpanan dibuat dengan geo-replikasi diaktifkan.

```yaml
Type: Boolean
Parameter Sets: GeoReplicationEnabled
Aliases: 

Required: False
Position: Named
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

### -Label
Menentukan label untuk akun penyimpanan.
Label mungkin panjangnya hingga 100 karakter.

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

### -StorageAccountName
Menentukan nama akun penyimpanan yang diubah cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe akun penyimpanan.
Nilai yang valid adalah: 

- Standard_LRS
- Standard_ZRS
- Standard_GRS
- Standard_RAGRS
- Premium_LRS

Jika parameter ini tidak ditentukan, nilai defaultnya Standard_GRS.

Efek menentukan parameter *GeoReplicationEnabled* sama dengan menentukan Standard_GRS dalam parameter *Type* .

Standard_ZRS atau akun Premium_LRS tidak dapat diubah ke tipe akun lain, dan sebaliknya.

```yaml
Type: String
Parameter Sets: AccountType
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

[Get-AzureStorageAccount](./Get-AzureStorageAccount.md)

[AzureStorageAccount baru](./New-AzureStorageAccount.md)

[Hapus-AzureStorageAccount](./Remove-AzureStorageAccount.md)


