---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADUser.md
ms.openlocfilehash: 3a7656c142335ba318289d7926c00bbd093108ca
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144230405"
---
# Get-AzADUser

## SYNOPSIS
Mencantumkan entitas dari pengguna atau mendapatkan entitas dari pengguna menurut kunci

## SYNTAX

### Daftar (Default)
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected]
 [-Filter <String>] [-Orderby <String[]>] [-Search <String>] [-ConsistencyLevel <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### MailParameterSet
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected]
 [-DefaultProfile <PSObject>] -Mail <String> [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected]
 [-DefaultProfile <PSObject>] -DisplayName <String> [<CommonParameters>]
```

### StartsWithParameterSet
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected]
 [-DefaultProfile <PSObject>] -StartsWith <String> [<CommonParameters>]
```

### ObjectIdParameterSet
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-AppendSelected] [-DefaultProfile <PSObject>]
 -ObjectId <String> [<CommonParameters>]
```

### UPNParameterSet
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-AppendSelected] [-DefaultProfile <PSObject>]
 -UserPrincipalName <String> [<CommonParameters>]
```

### SignedInUser
```
Get-AzADUser [-Expand <String[]>] [-Select <String[]>] [-AppendSelected] [-DefaultProfile <PSObject>]
 [-SignedIn] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan entitas dari pengguna atau mendapatkan entitas dari pengguna menurut kunci

## EXAMPLES

### Contoh 1: Dapatkan pengguna masuk
```powershell
Get-AzADUser -SignedIn
```

Mendapatkan pengguna masuk

### Contoh 2: Mencantumkan pengguna
```powershell
Get-AzADUser -First 10 -Select 'City' -AppendSelected
```

Cantumkan 10 pengguna pertama dan tambahkan properti 'City' setelah properti default: 'DisplayName', 'Id', 'DeletedDateTime', 'UserPrincipalName', 'UsageLocation', 'GivenName', 'SurName', 'AccountEnabled', 'MailNickName', 'Mail'

### Contoh 3: Mendapatkan pengguna menurut nama tampilan
```powershell
Get-AzADUser -DisplayName $name
```

Mendapatkan pengguna menurut nama tampilan

## PARAMETERS

### -AppendSelected
Tambahkan properti yang dipilih dengan properti default saat sakelar ini aktif, hanya berfungsi dengan parameter '-Select'.

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

### -ConsistencyLevel
Menunjukkan tingkat konsistensi yang diminta.
URL Dokumentasi: https://developer.microsoft.com/en-us/office/blogs/microsoft-graph-advanced-queries-for-directory-objects-are-now-generally-available/

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
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
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
nama tampilan pengguna

```yaml
Type: System.String
Parameter Sets: DisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Perluas
Memperluas entitas terkait

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Memfilter item menurut nilai properti

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mail
alamat email pengguna

```yaml
Type: System.String
Parameter Sets: MailParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
kunci: id pengguna

```yaml
Type: System.String
Parameter Sets: ObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Orderby
Mengurutkan item menurut nilai properti

```yaml
Type: System.String[]
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cari
Cari item menurut frasa pencarian

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pilih
Pilih properti yang akan dikembalikan

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignedIn
alamat email pengguna

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SignedInUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartsWith
nama tampilan pengguna dimulai dengan

```yaml
Type: System.String
Parameter Sets: StartsWithParameterSet
Aliases: SearchString

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipalName
nama prinsipal pengguna

```yaml
Type: System.String
Parameter Sets: UPNParameterSet
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lewati
Mengabaikan objek 'n' pertama lalu mendapatkan objek yang tersisa.

```yaml
Type: System.UInt64
Parameter Sets: List, MailParameterSet, DisplayNameParameterSet, StartsWithParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First
Hanya mendapatkan objek 'n' pertama.

```yaml
Type: System.UInt64
Parameter Sets: List, MailParameterSet, DisplayNameParameterSet, StartsWithParameterSet
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser

## NOTES

ALIAS

## RELATED LINKS
