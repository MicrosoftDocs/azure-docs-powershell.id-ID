---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebapptriggeredwebjobhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppTriggeredWebJobHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppTriggeredWebJobHistory.md
ms.openlocfilehash: 441768a2897c4ffd69511c6424fdcc90e4750c9d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142668952"
---
# Get-AzWebAppTriggeredWebJobHistory

## SYNOPSIS
Dapatkan atau cantumkan riwayat pekerjaan web yang dipicu untuk aplikasi.

## SYNTAX

### Daftar (Default)
```
Get-AzWebAppTriggeredWebJobHistory -AppName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzWebAppTriggeredWebJobHistory -AppName <String> -Id <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzWebAppTriggeredWebJobHistory -InputObject <IWebsitesIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan atau cantumkan riwayat pekerjaan web yang dipicu untuk aplikasi.

## EXAMPLES

### Contoh 1: Daftar riwayat pekerjaan web yang dipicu untuk aplikasi
```powershell
PS C:\> Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01

Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040249386155 webjob-rg-test
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

Daftar perintah ini memicu riwayat pekerjaan web untuk aplikasi.

### Contoh 2: Dapatkan riwayat pekerjaan web yang dipicu untuk aplikasi
```powershell
PS C:\> Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01 -Id 202201040236300466

Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

Perintah ini mendapatkan riwayat pekerjaan web yang dipicu untuk aplikasi.

### Contoh 3: Dapatkan riwayat pekerjaan web yang dipicu untuk aplikasi menurut saluran
```powershell
PS C:\> $logs =  Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01
PS C:\> $logs[0].Id | Get-AzWebAppTriggeredWebJobHistory

Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

Perintah ini mendapatkan riwayat pekerjaan web yang dipicu untuk aplikasi menurut saluran.

## PARAMETERS

### -AppName
Nama situs.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
ID Riwayat.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Web Job.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).

```yaml
Type: System.String[]
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20210201.ITriggeredJobHistory

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebsitesIdentity>: Parameter Identitas
  - `[Authprovider <String>]`: Penyedia auth untuk pengguna.
  - `[DomainName <String>]`: Nama domain kustom.
  - `[EnvironmentName <String>]`: Pengidentifikasi situs tahapan.
  - `[FunctionAppName <String>]`: Nama aplikasi fungsi yang terdaftar dengan build situs statis.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobHistoryId <String>]`: ID Riwayat.
  - `[Location <String>]`: Lokasi tempat Anda berencana untuk membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[Slot <String>]`: Nama slot penyebaran. Jika slot tidak ditentukan, API menghapus penyebaran untuk slot produksi.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.
  - `[WebJobName <String>]`: Nama Web Job.

## RELATED LINKS
