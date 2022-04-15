---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/enable-azdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzDataCollection.md
ms.openlocfilehash: dec05e96149fea4e405eb13af0ed48988b17b29b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142423986"
---
# Enable-AzDataCollection

## SYNOPSIS
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet Azure PowerShell. Menjalankan cmdlet ini memilih pengumpulan data untuk pengguna saat ini di komputer saat ini. Data dikumpulkan secara default kecuali Anda menolak secara eksplisit.

## SYNTAX

```
Enable-AzDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-AzDataCollection` Cmdlet digunakan untuk memilih pengumpulan data. Azure PowerShell secara otomatis mengumpulkan data telemetri secara default. Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum, dan untuk meningkatkan pengalaman Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi apa pun. Untuk menonaktifkan pengumpulan data, Anda harus menolak secara eksplisit dengan menjalankan `Disable-AzDataCollection`.

## EXAMPLES

### Contoh 1: Mengaktifkan pengumpulan data untuk pengguna saat ini

Contoh berikut ini memperlihatkan cara mengaktifkan pengumpulan data untuk pengguna saat ini.

```powershell
Enable-AzDataCollection
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

### -Konfirmasi

Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Disable-AzDataCollection](./Disable-AzDataCollection.md)
