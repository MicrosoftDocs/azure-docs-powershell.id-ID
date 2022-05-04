---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Support.dll-Help.xml
Module Name: Az.Support
online version: https://docs.microsoft.com/powershell/module/az.support/get-azsupportticketcommunication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicketCommunication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicketCommunication.md
ms.openlocfilehash: da1a7c04dffc90499fac61b421c7082dc568a0b7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144576614"
---
# Get-AzSupportTicketCommunication

## SYNOPSIS
Mendapatkan komunikasi tiket dukungan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.support/get-azsupportticketcommunication) untuk informasi terbaru.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzSupportTicketCommunication -SupportTicketName <String> [-Name <String>] [-Filter <String>]
 [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### GetByParentObjectParameterSet
```
Get-AzSupportTicketCommunication [-Name <String>] -SupportTicketObject <PSSupportTicket> [-Filter <String>]
 [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan komunikasi untuk tiket dukungan. Ini akan mengambil semua komunikasi untuk tiket jika Anda tidak menentukan parameter lain. Anda juga dapat memfilter komunikasi dengan CreatedDate atau CommunicationType menggunakan parameter Filter. Berikut adalah beberapa contoh nilai filter yang bisa Anda tentukan.


| Skenario                                                        | Filter                                                     |
|-----------------------------------------------------------------|------------------------------------------------------------|
| Mendapatkan komunikasi Web                                          | "CommunicationType eq 'Web'"                               |
| Mendapatkan komunikasi Telepon                                        | "CommunicationType eq 'Telepon'"                             |
| Mendapatkan komunikasi yang dibuat pada atau setelah 20 Des 2019 | "CreatedDate ge 2019-12-20"                                |
| Mendapatkan komunikasi yang dibuat setelah 20 Des 2019       | "CreatedDate gt 2019-12-20"                                |
| Mendapatkan komunikasi Web yang dibuat setelah 20 Des 2019            | "CreatedDate gt 2019-12-20 dan CommunicationType eq 'Web'" |


Cmdlet ini mendukung paging melalui parameter Pertama dan Lewati.

Anda juga dapat mengambil satu komunikasi tiket dukungan dengan menentukan nama komunikasi. 

## EXAMPLES

### Contoh 1: Mengambil semua komunikasi untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1"
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
testmessage1 user@contoso.com     test message   2/4/2020 9:35:42 PM
```

### Contoh 2: Mengambil satu komunikasi dengan nama untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -Name "testmessage1"
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage1 user@contoso.com     test message   2/4/2020 9:38:14 PM
```

### Contoh 3: Mengambil 2 komunikasi pertama untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -First 2
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 4: Ambil 2 komunikasi berikutnya setelah melewati 2 komunikasi pertama untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -Skip 2 -First 2
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage4 user@contoso.com     test message4  2/4/2020 9:38:14 PM
testmessage5 user@contoso.com     test message5  2/4/2020 9:36:36 PM
```

### Contoh 5: Mengambil semua komunikasi Web untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CommunicationType eq 'Web'"
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 6: Mengambil semua komunikasi yang dibuat pada atau setelah 20 Des 2019 untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CreatedDate ge 2019-12-20"
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 7: Mengambil semua komunikasi Web yang dibuat pada atau setelah 20 Des 2019 untuk tiket dukungan
```powershell
Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CommunicationType eq 'Web' and CreatedDate ge 2019-12-20"
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 8: Mengambil semua komunikasi untuk tiket dukungan dengan menyalurkan objek tiket dukungan
```powershell
Get-AzSupportTicket -Name "test1" | Get-AzSupportTicketCommunication
```
```output
Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
testmessage1 user@contoso.com     test message   2/4/2020 9:35:42 PM
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama komunikasi.

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

### -SupportTicketName
Nama tiket dukungan.

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

### -SupportTicketObject
Objek tiket dukungan.

```yaml
Type: Microsoft.Azure.Commands.Support.Models.PSSupportTicket
Parameter Sets: GetByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IncludeTotalCount
Melaporkan jumlah total objek dalam himpunan data (bilangan bulat) diikuti oleh objek yang dipilih.
Jika cmdlet tidak dapat menentukan jumlah total, cmdlet akan menampilkan "Jumlah total tidak diketahui." Bilangan bulat memiliki properti Akurasi yang menunjukkan keandalan nilai jumlah total.
Nilai Akurasi berkisar antara 0,0 hingga 1,0 di mana 0,0 berarti bahwa cmdlet tidak dapat menghitung objek, 1,0 berarti bahwa hitungannya tepat, dan nilai antara 0,0 dan 1,0 menunjukkan perkiraan yang semakin andal.

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

### -First
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportTicket

## OUTPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportTicketCommunication

## NOTES

## RELATED LINKS
