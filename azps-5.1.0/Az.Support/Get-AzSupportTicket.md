---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Support.dll-Help.xml
Module Name: Az.Support
online version: https://docs.microsoft.com/en-us/powershell/module/az.support/get-azsupportticket
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Support/Support/help/Get-AzSupportTicket.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Support/Support/help/Get-AzSupportTicket.md
ms.openlocfilehash: 368ae4ad814c9414ea211ea6e44c2d3fbda005f7
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136012093"
---
# Get-AzSupportTicket

## SYNOPSIS
Dapatkan tiket dukungan.

## SINTAKS

### ListParameterSet (Default)
```
Get-AzSupportTicket [-Filter <String>] [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount]
 [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

### GetByNameParameterSet
```
Get-AzSupportTicket -Name <String> [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount]
 [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

## DESKRIPSI
Mendapatkan daftar tiket dukungan. Ia akan mengambil semua tiket dukungan jika Anda tidak menentukan parameter apa pun. Anda juga bisa memfilter tiket dukungan menurut Status atau CreatedDate menggunakan parameter Filter. Berikut ini beberapa contoh nilai filter yang dapat Anda tentukan.

| Skenario                                                         | Filter                                           |
|------------------------------------------------------------------|--------------------------------------------------|
| Mendapatkan tiket yang dalam keadaan terbuka                               | "Status eq 'Buka'"                               |
| Dapatkan tiket yang dalam keadaan tertutup                             | "Status eq 'Ditutup'"                             |
| Dapatkan tiket yang dibuat pada atau setelah 20 Des 2019         | "CreatedDate ge 2019-12-20"                      |
| Dapatkan tiket yang dibuat setelah 20 Des 2019               | "CreatedDate gt 2019-12-20"                      |
| Mendapatkan tiket yang dibuat setelah 20 Des 2019 yang dibuka | "Tanggal Dibuat gt 2019-12-20 dan Status eq 'Buka'" |


Cmdlet ini mendukung membuat halaman melalui parameter Pertama dan Lewati.

Anda juga dapat mengambil satu tiket dukungan dengan menentukan nama tiket. 

## CONTOH

### Contoh 1: Get first 2 tickets
```powershell
PS C:\> Get-AzSupportTicket -First 2

Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test2 test title2                  150010521000318 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 2: Mendapatkan 2 tiket pertama setelah melewati 2 tiket pertama
```powershell
PS C:\> Get-AzSupportTicket -Skip 2 -First 2

Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test3 test title3                  150010521000314 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test4 test title4                  150010521000315 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 3: Dapatkan tiket dukungan berdasarkan nama
```powershell
PS C:\> Get-AzSupportTicket -Name "test1"

Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
```

### Contoh 4: Dapatkan 2 tiket dukungan pertama difilter menurut status
```powershell
PS C:\> Get-AzSupportTicket -Filter "Status eq 'Closed'" -First 2

Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test2 test title2                  150010521000318 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 5: Dapatkan semua tiket dukungan yang berada dalam Status terbuka dan dibuat setelah 20 Des 2019
```powershell
PS C:\> Get-AzSupportTicket -Filter "Status eq 'Open' and CreatedDate gt 2019-12-20"

Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test6 test title6                  150010521000311 Minimal  Virtual Machine running Linux Open   2/5/2020 1:33:53 AM
test7 test title7                  150010521000312 Minimal  Billing                       Open   2/5/2020 1:33:53 AM
```

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

### -Filter
Filter yang akan diterapkan ke hasil cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ListParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama tiket dukungan yang didaangkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTotalCount
Melaporkan jumlah total objek dalam rangkaian data (bilangan bulat) diikuti dengan objek yang dipilih.
Jika cmdlet tidak dapat menentukan hitungan total, cmdlet menampilkan "Penghitungan total tidak diketahui." Bilangan bulat memiliki properti Accuracy yang menunjukkan keandalan nilai perhitungan total.
Nilai Akurasi berkisar dari 0,0 hingga 1,0 di mana 0,0 berarti bahwa cmdlet tidak bisa menghitung objek, 1,0 berarti bahwa hitungan tepat, dan nilai antara 0,0 dan 1,0 menunjukkan perkiraan yang semakin andal.

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

### -Lewati
Mengabaikan jumlah objek tertentu lalu mendapatkan objek yang tersisa.
Masukkan jumlah objek yang akan dilewati.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First
Hanya mendapatkan jumlah objek yang ditentukan.
Masukkan jumlah objek yang akan dapatkan.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.Support.Models.PSSupportTicket

## CATATAN

## LINK TERKAIT
