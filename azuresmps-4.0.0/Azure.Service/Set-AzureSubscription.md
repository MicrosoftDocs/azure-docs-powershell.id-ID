---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 6185C6BA-460E-4EEA-B1EF-CD67629AA75E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 589ff3496db0c6d589f94b86cdaf5669eba8f2b9
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414744"
---
# Set-AzureSubscription

## SYNOPSIS
Mengubah langganan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### UpdateSubscriptionByIdParameterSetName (Default)
```
Set-AzureSubscription -SubscriptionId <String> [-Certificate <X509Certificate2>] [-ServiceEndpoint <String>]
 [-ResourceManagerEndpoint <String>] [-CurrentStorageAccountName <String>] [-Context <AzureStorageContext>]
 [-Environment <String>] [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### UpdateSubscriptionByNameParameterSetName
```
Set-AzureSubscription -SubscriptionName <String> [-Certificate <X509Certificate2>] [-ServiceEndpoint <String>]
 [-ResourceManagerEndpoint <String>] [-CurrentStorageAccountName <String>] [-Context <AzureStorageContext>]
 [-Environment <String>] [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### AddSubscriptionParameterSetName
```
Set-AzureSubscription -SubscriptionName <String> -SubscriptionId <String> -Certificate <X509Certificate2>
 [-ServiceEndpoint <String>] [-ResourceManagerEndpoint <String>] [-CurrentStorageAccountName <String>]
 [-Context <AzureStorageContext>] [-Environment <String>] [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureSubscription** membuat dan mengubah properti objek langganan Azure.
Anda dapat menggunakan cmdlet ini untuk bekerja dalam langganan Azure yang bukan merupakan langganan default atau untuk mengubah akun penyimpanan saat ini.
Untuk informasi tentang langganan saat ini dan default, lihat cmdlet **Select-AzureSubscription** .

Cmdlet ini beroperasi pada objek langganan Azure, bukan langganan Azure aktual Anda.
Untuk membuat dan menyediakan langganan Azure, kunjungi [Portal Azure](https://azure.microsoft.com/) (https://azure.microsoft.com/).

Cmdlet ini mengubah data dalam file data langganan yang dibuat saat menggunakan cmdlet **Add-AzureAccount** atau **Import-AzurePublishSettingsFile** untuk menambahkan akun Azure Windows PowerShell.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

## EXAMPLES

### Contoh 1: Mengubah langganan yang sudah ada1
```
C:\PS> $thumbprint = <Thumbprint-2>
C:\PS> $differentCert = Get-Item cert:\\CurrentUser\My\$thumbprint
C:\PS> Set-AzureSubscription -SubscriptionName ContosoEngineering -Certificate $differentCert
```

Contoh ini mengubah sertifikat untuk langganan bernama ContosoEngineering.

### Contoh 2: Mengubah titik akhir layanan
```
C:\PS> Set-AzureSubscription -SubscriptionName ContosoEngineering -ServiceEndpoint "https://management.core.contoso.com"
```

Perintah ini akan menambahkan atau mengubah titik akhir layanan kustom untuk langganan ContosoEngineering.

### Contoh 3: Hapus nilai properti
```
C:\PS> Set-AzureSubscription -SubscriptionName ContosoEngineering -Certificate $null -ResourceManagerEndpoint $Null
```

Perintah ini mengatur nilai properti Certificate dan ResourceManagerEndpoint menjadi null ($Null).
Ini akan menghapus nilai properti tersebut tanpa mengubah pengaturan lainnya.

### Contoh 4: Gunakan file data langganan alternatif
```
C:\PS> Set-AzureSubscription -SubscriptionName ContosoFinance -SubscriptionDataFile C:\Azure\SubscriptionData.xml -CurrentStorageAccount ContosoStorage01
```

Perintah ini mengubah akun penyimpanan saat ini dari langganan Contoso Azure ke ContosoStorage01.
Perintah tersebut menggunakan parameter **SubscriptionDataFile** untuk mengubah data dalam file data C:\Azure\SubscriptionData.xml langganan.
Secara default, **Langganan Azure-Azure menggunakan** file data langganan default di profil pengguna roaming Anda.

## PARAMETERS

### -Certificate
```yaml
Type: X509Certificate2
Parameter Sets: UpdateSubscriptionByIdParameterSetName, UpdateSubscriptionByNameParameterSetName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: X509Certificate2
Parameter Sets: AddSubscriptionParameterSetName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konteks
```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CurrentStorageAccountName
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

### -Lingkungan
Menentukan lingkungan Azure.

Lingkungan Azure, penyebaran independen dari Microsoft Azure, seperti AzureCloud untuk global Azure dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga bisa membuat lingkungan Azure lokal dengan menggunakan Paket Azure dan cmdlet WAPack.
Untuk informasi selengkapnya, lihat [Paket Azure](/previous-versions/azure/windows-server-azure-pack/).

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

### -PassThru
Mengembalikan $True jika perintah berhasil $False jika gagal.
Secara default, cmdlet ini tidak mengembalikan output apa pun.
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -ResourceManagerEndpoint
Menentukan titik akhir untuk data Azure Resource Manager, termasuk data tentang grup sumber daya yang terkait dengan akun tersebut.
Untuk informasi selengkapnya tentang Azure Resource Manager, lihat [Cmdlet Azure Resource Manager](https://go.microsoft.com/fwlink/?LinkID=394765) (https://go.microsoft.com/fwlink/?LinkID=394765) dan [Menggunakan Windows PowerShell dengan Resource Manager](https://go.microsoft.com/fwlink/?LinkID=394767) (https://go.microsoft.com/fwlink/?LinkID=394767).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceEndpoint
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
```yaml
Type: String
Parameter Sets: UpdateSubscriptionByIdParameterSetName, AddSubscriptionParameterSetName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
```yaml
Type: String
Parameter Sets: UpdateSubscriptionByNameParameterSetName, AddSubscriptionParameterSetName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak Ada atau System.Boolean
Ketika Anda menggunakan parameter *PassThru* , cmdlet ini mengembalikan nilai Boolean.
Secara default, cmdlet ini tidak mengembalikan output apa pun.

## CATATAN

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzureSubscription](./Get-AzureSubscription.md)

[Import-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Remove-AzureSubscription](./Remove-AzureSubscription.md)

[Select-AzureSubscription](./Select-AzureSubscription.md)


