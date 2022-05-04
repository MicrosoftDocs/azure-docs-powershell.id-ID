---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 6FF04E82-4921-4F7B-83D0-6997316BC5FD
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstoragecontainersastoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainerSASToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainerSASToken.md
ms.openlocfilehash: ed39b8848800f22f777b8c246d5dbd7d8275ab56
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144708418"
---
# New-AzStorageContainerSASToken

## SYNOPSIS
Membuat token SAS untuk kontainer penyimpanan Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/new-azstoragecontainersastoken) untuk informasi terbaru.

## SYNTAX

### SasPolicy
```
New-AzStorageContainerSASToken [-Name] <String> -Policy <String> [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-EncryptionScope <String>] [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SasPermission
```
New-AzStorageContainerSASToken [-Name] <String> [-Permission <String>] [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-EncryptionScope <String>] [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageContainerSASToken** menghasilkan token Tanda Tangan Akses Bersama (SAS) untuk kontainer penyimpanan Azure.

## EXAMPLES

### Contoh 1: Membuat token SAS kontainer dengan izin kontainer penuh
```
PS C:\>New-AzStorageContainerSASToken -Name "Test" -Permission rwdl
```

Contoh ini menghasilkan token SAS kontainer dengan izin kontainer penuh.

### Contoh 2: Menghasilkan beberapa token SAS kontainer menurut alur
```
PS C:\>Get-AzStorageContainer -Container test* | New-AzStorageContainerSASToken -Permission rwdl
```

Contoh ini menghasilkan beberapa token SAS kontainer dengan menggunakan alur.

### Contoh 3: Menghasilkan token SAS kontainer dengan kebijakan akses bersama
```
PS C:\>New-AzStorageContainerSASToken -Name "Test" -Policy "PolicyName"
```

Contoh ini menghasilkan token SAS kontainer dengan kebijakan akses bersama.

### Contoh 3: Membuat token SAS kontainer Identitas Pengguna dengan konteks penyimpanan berdasarkan autentikasi OAuth
```
PS C:\> $ctx = New-AzStorageContext -StorageAccountName $accountName -UseConnectedAccount
PS C:\> $StartTime = Get-Date
PS C:\> $EndTime = $startTime.AddDays(6)
PS C:\> New-AzStorageContainerSASToken -Name "ContainerName" -Permission rwd -StartTime $StartTime -ExpiryTime $EndTime -context $ctx
```

Contoh ini menghasilkan token SAS kontainer Identitas Pengguna dengan konteks penyimpanan berdasarkan autentikasi OAuth

## PARAMETERS

### -Context
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya dengan menggunakan cmdlet New-AzStorageContext.
Ketika konteks penyimpanan didasarkan pada autentikasi OAuth, akan menghasilkan token SAS kontainer Identitas Pengguna.

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
Jika pengguna mengatur waktu mulai tetapi bukan waktu kedaluwarsa, waktu kedaluwarsa diatur ke waktu mulai ditambah satu jam.
Jika waktu mulai maupun waktu kedaluwarsa tidak ditentukan, waktu kedaluwarsa diatur ke waktu saat ini ditambah satu jam.
Ketika konteks penyimpanan didasarkan pada autentikasi OAuth, waktu kedaluwarsa harus dalam 7 hari dari waktu saat ini, dan tidak boleh lebih awal dari waktu saat ini.

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
Menunjukkan bahwa cmdlet ini mengembalikan URI blob lengkap dan token tanda tangan akses bersama.

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

### -Name
Menentukan nama kontainer penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Container

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Izin
Menentukan izin untuk kontainer penyimpanan.
Penting untuk dicatat bahwa ini adalah string, seperti `rwd` (untuk Baca, Tulis, dan Hapus).

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
Menentukan Kebijakan Akses Tersimpan Azure.

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
* HttpsOrHttp Nilai defaultnya adalah HttpsOrHttp.

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

### -StartTime
Menentukan waktu tanda tangan akses bersama menjadi valid.

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

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[New-AzStorageBlobSASToken](./New-AzStorageBlobSASToken.md)
