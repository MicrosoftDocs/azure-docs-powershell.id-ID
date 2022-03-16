---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ManagementPartner.dll-Help.xml
Module Name: Az.ManagementPartner
online version: https://docs.microsoft.com/powershell/module/az.managementpartner/get-azmanagementpartner
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
ms.openlocfilehash: 551db58223e1fd2c5d37f89c60f0bf466cb2314a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140234377"
---
# Get-AzManagementPartner

## SYNOPSIS
Mendapatkan ID Jaringan Mitra Microsoft (MPN) dari prinsipal layanan atau pengguna yang diautentikasi saat ini.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.managementpartner/get-azmanagementpartner) untuk informasi terkini.

## SYNTAX

```
Get-AzManagementPartner [[-PartnerId] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan ID Jaringan Mitra Microsoft (MPN) dari prinsipal layanan atau pengguna yang diautentikasi saat ini.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzManagementPartner
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : 1b1121dd-6900-412a-af73-e8d44f81e1c1
ObjectId    : aa67f786-0552-423e-8849-244ed12bf581
State       : Active
```

Dapatkan id mitra manajemen saat ini

### Contoh 2
```powershell
PS C:\> Get-AzManagementPartner -PartnerId 4977985
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : 1b1121dd-6900-412a-af73-e8d44f81e1c1
ObjectId    : aa67f786-0552-423e-8849-244ed12bf581
State       : Active
```

Dapatkan id mitra manajemen saat ini menggunakan id mitra, jika tidak cocok, id akan gagal

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

### -PartnerId
Id mitra manajemen, merupakan angka 6 digit

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ManagementPartner.PSManagementPartner

## CATATAN

## RELATED LINKS

[Remove-AzManagementPartner](./Remove-AzManagementPartner.md)

[New-AzManagementPartner](./New-AzManagementPartner.md)

[Update-AzManagementPartner](./Update-AzManagementPartner.md)
