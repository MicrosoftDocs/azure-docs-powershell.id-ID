---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-aznetworkservicetag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzNetworkServiceTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzNetworkServiceTag.md
ms.openlocfilehash: 2531b18e39ce687651c730f2a96d6b993d5b1bb8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142176847"
---
# Get-AzNetworkServiceTag

## SYNOPSIS
Mendapatkan daftar sumber informasi tag layanan.

## SYNTAX

```
Get-AzNetworkServiceTag -Location <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetworkServiceTag** mendapatkan daftar sumber informasi tag layanan.

Harap diperhatikan bahwa informasi kawasan Azure yang Anda tentukan akan digunakan sebagai referensi untuk versi (bukan sebagai filter berdasarkan lokasi). Misalnya, bahkan jika Menentukan `-Location eastus2` , Anda akan mendapatkan daftar tag layanan dengan detail prefiks di seluruh kawasan namun terbatas pada cloud yang menjadi milik langganan Anda (misalnya Publik, pemerintah AS, Tiongkok, atau Jerman).

## EXAMPLES

### Contoh 1
```powershell
$serviceTags = Get-AzNetworkServiceTag -Location eastus2
$serviceTags

Name         : Public
Id           : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx/providers/Microsoft.Network/serviceTags/Public
Type         : Microsoft.Network/serviceTags
ChangeNumber : 63
Cloud        : Public
Values       : {ApiManagement, ApiManagement.AustraliaCentral, ApiManagement.AustraliaCentral2, ApiManagement.AustraliaEast...}

$serviceTags.Values

Name             : ApiManagement
System Service   : AzureApiManagement
Address Prefixes : {13.64.39.16/32, 13.66.138.92/31, 13.66.140.176/28, 13.67.8.108/31...}
Change Number    : 7

Name             : ApiManagement.AustraliaCentral
System Service   : AzureApiManagement
Region           : australiacentral
Address Prefixes : {20.36.106.68/31, 20.36.107.176/28}
Change Number    : 2

Name             : ApiManagement.AustraliaCentral2
System Service   : AzureApiManagement
Region           : australiacentral2
Address Prefixes : {20.36.114.20/31, 20.36.115.128/28}
Change Number    : 2

Name             : ApiManagement.AustraliaEast
System Service   : AzureApiManagement
Region           : australiaeast
Address Prefixes : {13.70.72.28/31, 13.70.72.240/28, 13.75.217.184/32, 13.75.221.78/32...}
Change Number    : 3

Name             : ApiManagement.AustraliaSoutheast
System Service   : AzureApiManagement
Region           : australiasoutheast
Address Prefixes : {13.77.50.68/31, 13.77.52.224/28}
Change Number    : 2

...
```

Perintah mendapatkan daftar sumber daya informasi tag layanan dan menyimpannya dalam variabel `serviceTags`.

### Contoh 2: Dapatkan semua prefiks alamat untuk AzureSQL
```powershell
$serviceTags = Get-AzNetworkServiceTag -Location eastus2
$sql = $serviceTags.Values | Where-Object { $_.Name -eq "Sql" }
$sql

Name             : Sql
System Service   : AzureSQL
Address Prefixes : {13.65.31.249/32, 13.65.39.207/32, 13.65.85.183/32, 13.65.200.105/32...}
Change Number    : 18

$sql.Properties.AddressPrefixes.Count
644
$sql.Properties.AddressPrefixes
13.65.31.249/32
13.65.39.207/32
13.65.85.183/32
13.65.200.105/32
13.65.209.243/32
...
```

Perintah pertama mendapatkan daftar sumber informasi tag layanan dan menyimpannya dalam variabel `serviceTags`.
Perintah kedua memfilter daftar untuk memilih sumber informasi untuk Sql.

### Contoh 3: Dapatkan sumber informasi tag layanan Storage untuk WEST US 2
```powershell
$serviceTags = Get-AzNetworkServiceTag -Location eastus2
$serviceTags.Values | Where-Object { $_.Name -eq "Storage.WestUS2" }

Name             : Storage.WestUS2
System Service   : AzureStorage
Region           : westus2
Address Prefixes : {13.66.176.16/28, 13.66.176.48/28, 13.66.232.64/28, 13.66.232.208/28...}
Change Number    : 5

$serviceTags.Values | Where-Object { $_.Name -like "Storage*" -and $_.Properties.Region -eq "westus2" }

Name             : Storage.WestUS2
System Service   : AzureStorage
Region           : westus2
Address Prefixes : {13.66.176.16/28, 13.66.176.48/28, 13.66.232.64/28, 13.66.232.208/28...}
Change Number    : 5

$serviceTags.Values | Where-Object { $_.Properties.SystemService -eq "AzureStorage" -and $_.Properties.Region -eq "westus2" }

Name             : Storage.WestUS2
System Service   : AzureStorage
Region           : westus2
Address Prefixes : {13.66.176.16/28, 13.66.176.48/28, 13.66.232.64/28, 13.66.232.208/28...}
Change Number    : 5
```

Perintah pertama mendapatkan daftar sumber informasi tag layanan dan menyimpannya dalam variabel `serviceTags`.
Perintah berikut ini memperlihatkan berbagai cara untuk memfilter daftar guna memilih informasi tag layanan untuk Storage di AS Barat 2.

### Contoh 4: Dapatkan semua sumber daya informasi tag layanan global
```powershell
$serviceTags = Get-AzNetworkServiceTag -Location eastus2
$serviceTags.Values | Where-Object { -not $_.Properties.Region }
```

```output
Name             : ApiManagement
System Service   : AzureApiManagement
Address Prefixes : {13.64.39.16/32, 13.66.138.92/31, 13.66.140.176/28, 13.67.8.108/31...}
Change Number    : 7

Name             : AppService
System Service   : AzureAppService
Address Prefixes : {13.64.73.110/32, 13.65.30.245/32, 13.65.37.122/32, 13.65.39.165/32...}
Change Number    : 13

Name             : AppServiceManagement
System Service   : AzureAppServiceManagement
Address Prefixes : {13.64.115.203/32, 13.66.140.0/26, 13.67.8.128/26, 13.69.64.128/26...}
Change Number    : 7

Name             : AzureActiveDirectory
System Service   : AzureAD
Address Prefixes : {13.64.151.161/32, 13.66.141.64/27, 13.67.9.224/27, 13.67.50.224/29...}
Change Number    : 3

Name             : AzureActiveDirectoryDomainServices
System Service   : AzureIdentity
Address Prefixes : {13.64.151.161/32, 13.66.141.64/27, 13.67.9.224/27, 13.69.66.160/27...}
Change Number    : 2

...
```

Perintah pertama mendapatkan daftar sumber informasi tag layanan dan menyimpannya dalam variabel `serviceTags`.
Perintah kedua memfilter daftar untuk memilih hanya yang tidak memiliki kawasan yang diatur.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi yang akan digunakan sebagai referensi untuk versi (bukan sebagai filter berdasarkan lokasi, Anda akan mendapatkan daftar tag layanan dengan detail prefiks di seluruh kawasan tetapi terbatas pada awan tempat langganan Anda berada).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkServiceTag

## CATATAN

## RELATED LINKS
