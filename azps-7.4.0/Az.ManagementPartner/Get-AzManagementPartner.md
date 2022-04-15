---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ManagementPartner.dll-Help.xml
Module Name: Az.ManagementPartner
online version: https://docs.microsoft.com/powershell/module/az.managementpartner/get-azmanagementpartner
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
ms.openlocfilehash: 150d5e4784ee43a83abf1bd231633002c5fa6ac4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142424836"
---
# Get-AzManagementPartner

## SYNOPSIS
Mendapatkan ID Jaringan Mitra Microsoft (MPN) dari pengguna atau prinsipal layanan yang diautentikasi saat ini.

## SYNTAX

```
Get-AzManagementPartner [[-PartnerId] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan ID Jaringan Mitra Microsoft (MPN) dari pengguna atau prinsipal layanan yang diautentikasi saat ini.

## EXAMPLES

### Contoh 1
```powershell
Get-AzManagementPartner
```

```output
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : 1b1121dd-6900-412a-af73-e8d44f81e1c1
ObjectId    : aa67f786-0552-423e-8849-244ed12bf581
State       : Active
```

Dapatkan id mitra manajemen saat ini

### Contoh 2
```powershell
Get-AzManagementPartner -PartnerId 4977985
```

```output
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : 1b1121dd-6900-412a-af73-e8d44f81e1c1
ObjectId    : aa67f786-0552-423e-8849-244ed12bf581
State       : Active
```

Dapatkan id mitra manajemen saat ini menggunakan id mitra, jika tidak cocok, id tersebut akan gagal

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
Id mitra manajemen, itu adalah angka 6 digit

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ManagementPartner.PSManagementPartner

## CATATAN

## RELATED LINKS

[Remove-AzManagementPartner](./Remove-AzManagementPartner.md)

[New-AzManagementPartner](./New-AzManagementPartner.md)

[Update-AzManagementPartner](./Update-AzManagementPartner.md)