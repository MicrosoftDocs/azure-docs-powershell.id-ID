---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Support.dll-Help.xml
Module Name: Az.Support
online version: https://docs.microsoft.com/powershell/module/az.support/get-azsupportticket
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicket.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicket.md
ms.openlocfilehash: 52e41eca379fda67d5adaf69cebdb2d7ef4dc143
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142000769"
---
# Get-AzSupportTicket

## SYNOPSIS
Dapatkan tiket dukungan.

## SYNTAX

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

## DESCRIPTION
Mendapatkan daftar tiket dukungan. Ini akan mengambil semua tiket dukungan jika Anda tidak menentukan parameter apa pun. Anda juga dapat memfilter tiket dukungan menurut Status atau TanggalDijadikan menggunakan parameter Filter. Berikut adalah beberapa contoh nilai filter yang bisa Anda tentukan.

| Skenario                                                         | Filter                                           |
|------------------------------------------------------------------|--------------------------------------------------|
| Dapatkan tiket yang dalam status terbuka                               | "Status eq 'Buka'"                               |
| Dapatkan tiket yang dalam keadaan tertutup                             | "Status eq 'Tertutup'"                             |
| Dapatkan tiket yang dibuat pada atau setelah 20 Des 2019         | "CreatedDate ge 2019-12-20"                      |
| Dapatkan tiket yang dibuat setelah 20 Des 2019               | "CreatedDate gt 2019-12-20"                      |
| Dapatkan tiket yang dibuat setelah 20 Des 2019 yang dalam status terbuka | "CreatedDate gt 2019-12-20 dan Status eq 'Buka'" |


Cmdlet ini mendukung paging melalui parameter Pertama dan Lewati.

Anda juga dapat mengambil tiket dukungan tunggal dengan menentukan nama tiket. 

## EXAMPLES

### Contoh 1: Dapatkan 2 tiket pertama
```powershell
Get-AzSupportTicket -First 2
```
```output
Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test2 test title2                  150010521000318 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 2: Dapatkan 2 tiket pertama setelah melewati 2 tiket pertama
```powershell
Get-AzSupportTicket -Skip 2 -First 2
```
```output
Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test3 test title3                  150010521000314 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test4 test title4                  150010521000315 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 3: Dapatkan tiket dukungan berdasarkan nama
```powershell
Get-AzSupportTicket -Name "test1"
```
```output
Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
```

### Contoh 4: Dapatkan 2 tiket dukungan pertama yang difilter menurut status
```powershell
Get-AzSupportTicket -Filter "Status eq 'Closed'" -First 2
```
```output
Name  Title                        SupportTicketId Severity ServiceDisplayName            Status CreatedDate
----  -----                        --------------- -------- ------------------            ------ -----------
test1 test title1                  150010521000317 Minimal  Virtual Machine running Linux Closed 2/5/2020 1:33:53 AM
test2 test title2                  150010521000318 Minimal  Billing                       Closed 2/5/2020 1:33:53 AM
```

### Contoh 5: Dapatkan semua tiket dukungan yang berada dalam Status terbuka dan dibuat setelah 20 Des 2019
```powershell
Get-AzSupportTicket -Filter "Status eq 'Open' and CreatedDate gt 2019-12-20"
```
```output
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
Filter untuk diterapkan ke hasil cmdlet ini.

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
Nama tiket dukungan yang didapat cmdlet ini.

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
Melaporkan jumlah total objek dalam kumpulan data (bilangan bulat) diikuti dengan objek yang dipilih.
Jika cmdlet tidak dapat menentukan jumlah total, cmdlet akan menampilkan "Jumlah total tidak diketahui." Bilangan bulat memiliki properti Akurasi yang menunjukkan keandalan nilai total hitungan.
Nilai Akurasi berkisar dari 0,0 hingga 1,0 di mana 0,0 berarti bahwa cmdlet tidak dapat menghitung objek, 1,0 berarti bahwa hitungan tepat, dan nilai antara 0,0 dan 1,0 menunjukkan perkiraan yang semakin andal.

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
Mengabaikan jumlah objek yang ditentukan lalu mendapatkan objek yang tersisa.
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

### -Pertama
Hanya mendapatkan jumlah objek yang ditentukan.
Masukkan jumlah objek yang akan didapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportTicket

## CATATAN

## RELATED LINKS
