---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Support.dll-Help.xml
Module Name: Az.Support
online version: https://docs.microsoft.com/powershell/module/az.support/get-azsupportticketcommunication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicketCommunication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportTicketCommunication.md
ms.openlocfilehash: 563bf48f3df0a74e1f5c8580246363cec87586b4
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140499225"
---
# Get-AzSupportTicketCommunication

## SYNOPSIS
Dapatkan komunikasi tiket dukungan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.support/get-azsupportticketcommunication) untuk informasi terkini.

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
Mendapatkan komunikasi untuk tiket dukungan. It will retrieve all the communications for a ticket if you not specify any other parameters. Anda juga dapat memfilter komunikasi menurut CreatedDate atau CommunicationType menggunakan parameter Filter. Berikut ini beberapa contoh nilai filter yang dapat Anda tentukan.


| Skenario                                                        | Filter                                                     |
|-----------------------------------------------------------------|------------------------------------------------------------|
| Dapatkan komunikasi Web                                          | "CommunicationType eq 'Web'"                               |
| Dapatkan Telepon komunikasi                                        | "CommunicationType eq 'Telepon'"                             |
| Dapatkan komunikasi yang dibuat pada atau setelah 20 Des 2019 | "CreatedDate ge 2019-12-20"                                |
| Dapatkan komunikasi yang dibuat setelah 20 Des 2019       | "CreatedDate gt 2019-12-20"                                |
| Mendapatkan komunikasi Web dibuat setelah 20 Des 2019            | "CreatedDate gt 2019-12-20 dan CommunicationType eq 'Web'" |


Cmdlet ini mendukung membuat halaman melalui parameter Pertama dan Lewati.

Anda juga dapat mengambil satu komunikasi tiket dukungan dengan menentukan nama komunikasi. 

## EXAMPLES

### Contoh 1: Ambil semua komunikasi untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1"

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
testmessage1 user@contoso.com     test message   2/4/2020 9:35:42 PM
```

### Contoh 2: Ambil komunikasi tunggal dengan namanya untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -Name "testmessage1"

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage1 user@contoso.com     test message   2/4/2020 9:38:14 PM
```

### Contoh 3: Ambil 2 komunikasi pertama untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -First 2

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 4: Ambil 2 komunikasi berikutnya setelah melewati 2 komunikasi pertama untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -Skip 2 -First 2

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage4 user@contoso.com     test message4  2/4/2020 9:38:14 PM
testmessage5 user@contoso.com     test message5  2/4/2020 9:36:36 PM
```

### Contoh 5: Ambil semua komunikasi Web untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CommunicationType eq 'Web'"

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 6: Ambil semua komunikasi yang dibuat pada atau setelah 20 Des 2019 untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CreatedDate ge 2019-12-20"

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 7: Ambil semua komunikasi Web yang dibuat pada atau setelah 20 Des 2019 untuk tiket dukungan
```powershell
PS C:\> Get-AzSupportTicketCommunication -SupportTicketName "test1" -Filter "CommunicationType eq 'Web' and CreatedDate ge 2019-12-20"

Name         Sender               Subject        CreatedDate
----         ------               -------        -----------
testmessage3 user@contoso.com     test message3  2/4/2020 9:38:14 PM
testmessage2 user@contoso.com     test message2  2/4/2020 9:36:36 PM
```

### Contoh 8: Ambil semua komunikasi untuk tiket dukungan dengan pemipaan objek tiket dukungan
```powershell
PS C:\> Get-AzSupportTicket -Name "test1" | Get-AzSupportTicketCommunication

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

### -Nama
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportTicket

## OUTPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportTicketCommunication

## CATATAN

## RELATED LINKS
