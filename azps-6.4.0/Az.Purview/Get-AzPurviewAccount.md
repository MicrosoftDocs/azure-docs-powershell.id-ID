---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Get-AzPurviewAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Get-AzPurviewAccount.md
ms.openlocfilehash: ff749c8aa3854ef388ede3c44fa49b7569554de0
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136182585"
---
# Get-AzPurviewAccount

## SYNOPSIS
Mendapatkan akun

## SYNTAX

### Daftar1 (Default)
```
Get-AzPurviewAccount [-SubscriptionId <String[]>] [-SkipToken <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzPurviewAccount -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzPurviewAccount -InputObject <IPurviewIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzPurviewAccount -ResourceGroupName <String> [-SubscriptionId <String[]>] [-SkipToken <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan akun

## EXAMPLES

### Contoh 1: List All Purview Accounts
```powershell
PS C:\> Get-AzPurviewAccount

IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location Name          SystemDataCreatedAt  SystemDataCreatedBy      SystemDataCreatedByType 
-------------------                  ----------------                     ------------   -------- ----          -------------------  -------------------      -------- 
xxxxxxxx-a087-43aa-8a7f-c17a4bbd4d36 xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   pvac          8/4/2021 8:34:28 AM  xxx@microsoft.com        User     
xxxxxxxx-bbe7-4506-a9c4-4d602d8e4e1c xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   purview-test  8/9/2021 9:38:47 AM  xxxxxxxxx@microsoft.com  User     
xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7 xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   test-pa       8/17/2021 6:18:57 AM xxxxxxxxxx@microsoft.com User 
```

Membuat daftar semua akun tampilan.

### Contoh 2: Dapatkan Purview Account menurut Nama dan Nama Grup Sumber Daya
```powershell
PS C:\> Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg

IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location Name   SystemDataCreatedAt  SystemDataCreatedBy      SystemDataCreatedByType SystemDataLastModifiedAt
-------------------                  ----------------                     ------------   -------- ----   -------------------  -------------------      ----------------------- ----------------- 
xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7 xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   test-pa 8/17/2021 6:18:57 AM xxxxxxxxxx@microsoft.com User                    8/17/2021 6:18:5… 
```

Dapatkan uji-rg nama akun purview dalam uji-pa grup sumber daya

### Contoh 3: Purview Accounts in a Specified Resource Group 
```powershell
PS C:\> Get-AzPurviewAccount -ResourceGroupName test-rg

IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location Name   SystemDataCreatedAt  SystemDataCreatedBy      SystemDataCreatedByType SystemDataLastModifiedAt
-------------------                  ----------------                     ------------   -------- ----   -------------------  -------------------      ----------------------- ----------------- 
xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7 xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   test-pa 8/17/2021 6:18:57 AM xxxxxxxxxx@microsoft.com User                    8/17/2021 6:18:5… 
```

List the purview accounts in resource group test-pa

### Contoh 4: Dapatkan Purview Account by InputObject
```powershell
PS C:\>  $got = Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg
PS C:\>  Get-AzADDomainService -InputObject $got


IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location Name   SystemDataCreatedAt  SystemDataCreatedBy      SystemDataCreatedByType SystemDataLastModifiedAt
-------------------                  ----------------                     ------------   -------- ----   -------------------  -------------------      ----------------------- ----------------- 
xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7 xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a SystemAssigned eastus   test-pa 8/17/2021 6:18:57 AM xxxxxxxxxx@microsoft.com User                    8/17/2021 6:18:5… 
```

Mendapatkan akun tampilan dengan InputObject

## PARAMETERS

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama akun.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipToken
Token lewati.

```yaml
Type: System.String
Parameter Sets: List, List1
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Pengidentifikasi langganan

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.Api20210701.IAccount

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IPurviewIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama akun.
  - `[GroupId <String>]`: Pengidentifikasi grup.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan

## RELATED LINKS

