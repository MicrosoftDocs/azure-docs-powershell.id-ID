---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azadapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADApplication.md
ms.openlocfilehash: feaa3a343a67850fcc078cf9c19e13fb9091c900
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138166365"
---
# Get-AzADApplication

## SYNOPSIS
Mencantumkan entitas dari aplikasi atau mendapatkan entitas dari aplikasi dengan kunci

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzADApplication [-Select <String[]>] [-Filter <String>] [-Orderby <String[]>] [-Search <String>]
 [-ConsistencyLevel <String>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### ApplicationObjectIdParameterSet
```
Get-AzADApplication -ObjectId <String> [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>]
 [-AppendSelected] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### SearchStringParameterSet
```
Get-AzADApplication [-Select <String[]>] -DisplayNameStartWith <String> [-First <UInt64>] [-Skip <UInt64>]
 [-AppendSelected] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzADApplication [-Select <String[]>] -DisplayName <String> [-First <UInt64>] [-Skip <UInt64>]
 [-AppendSelected] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ApplicationIdParameterSet
```
Get-AzADApplication [-Select <String[]>] -ApplicationId <Guid> [-First <UInt64>] [-Skip <UInt64>]
 [-AppendSelected] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ApplicationIdentifierUriParameterSet
```
Get-AzADApplication [-Select <String[]>] -IdentifierUri <String> [-First <UInt64>] [-Skip <UInt64>]
 [-AppendSelected] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan entitas dari aplikasi atau mendapatkan entitas dari aplikasi dengan kunci

## EXAMPLES

### Contoh 1: Dapatkan aplikasi dengan nama tampilan
```powershell
PS C:\> Get-AzADApplication -DisplayName $appname
```

Dapatkan aplikasi dengan nama tampilan

### Contoh 2: Daftar aplikasi
```powershell
PS C:\> Get-AzADApplication -First 10
```

Membuat daftar 10 aplikasi pertama

### Contoh 3: Cari nama tampilan aplikasi dimulai dengan
```powershell
PS C:\> Get-AzADApplication -DisplayNameStartsWith $prefix
```

Cari nama tampilan aplikasi dimulai dengan

### Contoh 4: Get application by object Id
```powershell
PS C:\> Get-AzADapplication -ObjectId $id -Select Tags -AppendSelected
```

Dapatkan aplikasi dengan objek Id dan properti penambahan 'Tag' setelah properti default: 'DisplayName', 'Id', 'DeletedDateTime', 'IdentifierUris', 'Web', 'AppId', 'SignInAudience'

## PARAMETERS

### -AppendSelected
Tambahkan properti yang dipilih dengan properti default saat sakelar ini diaktifkan, hanya bekerja dengan parameter '-Pilih'.

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

### -ApplicationId
id aplikasi

```yaml
Type: System.Guid
Parameter Sets: ApplicationIdParameterSet
Aliases: AppId

Required: True
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
Parameter Sets: EmptyParameterSet
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
nama tampilan aplikasi

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

### -DisplayNameStartWith
nama tampilan aplikasi dimulai dengan

```yaml
Type: System.String
Parameter Sets: SearchStringParameterSet
Aliases: DisplayNameStartsWith

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Memfilter item menurut nilai properti

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentifierUri
uri pengidentifikasi aplikasi

```yaml
Type: System.String
Parameter Sets: ApplicationIdentifierUriParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
kunci: id aplikasi

```yaml
Type: System.String
Parameter Sets: ApplicationObjectIdParameterSet
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Orderby
Item pesanan menurut nilai properti

```yaml
Type: System.String[]
Parameter Sets: EmptyParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pencarian
Mencari item menurut frasa pencarian

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet
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

### -Lewati
Mengabaikan objek 'n' pertama, lalu mendapatkan objek yang tersisa.

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
Hanya mendapatkan objek 'n' pertama.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## CATATAN

ALIAS

## RELATED LINKS
