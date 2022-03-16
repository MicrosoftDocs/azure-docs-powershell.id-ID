---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azadgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroup.md
ms.openlocfilehash: 80925815613d878b557108169ee1d762d737f0a9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140264837"
---
# Get-AzADGroup

## SYNOPSIS
Lists entities from groups or get entity from groups by key

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/get-azadgroup) untuk informasi terkini.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzADGroup [-Expand <String[]>] [-Select <String[]>] [-Filter <String>] [-Orderby <String[]>]
 [-Search <String>] [-ConsistencyLevel <String>] [-First <UInt64>] [-Skip <UInt64>] [-AppendSelected]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzADGroup [-Expand <String[]>] [-Select <String[]>] [-ConsistencyLevel <String>] [-First <UInt64>]
 [-Skip <UInt64>] [-AppendSelected] -DisplayName <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### SearchStringParameterSet
```
Get-AzADGroup [-Expand <String[]>] [-Select <String[]>] [-ConsistencyLevel <String>] [-First <UInt64>]
 [-Skip <UInt64>] [-AppendSelected] -DisplayNameStartsWith <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### ObjectIdParameterSet
```
Get-AzADGroup [-Expand <String[]>] [-Select <String[]>] [-ConsistencyLevel <String>] [-AppendSelected]
 -ObjectId <Guid> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Lists entities from groups or get entity from groups by key

## EXAMPLES

### Contoh 1: Dapatkan grup berdasarkan nama tampilan
```powershell
PS C:\> Get-AzADGroup -DisplayName $gname
```

Dapatkan grup menurut nama tampilan

### Contoh 2: Grup daftar
```powershell
PS C:\> Get-AzADGroup -First 10
```

Membuat daftar 10 grup pertama

### Contoh 3: Get group by object id
```powershell
PS C:\> Get-AzADGroup -ObjectId $id -Select groupTypes -AppendSelected
```

Dapatkan grup dengan id objek dan properti tambahkan 'groupTypes' setelah properti default: 'DisplayName', 'Id', 'DeletedDateTime', 'SecurityEnabled', 'MailEnabled', 'MailNickname', 'Deskripsi'

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

### -ConsistencyLevel
Menunjukkan tingkat konsistensi yang diminta.
URL Dokumentasi: https://developer.microsoft.com/en-us/office/blogs/microsoft-graph-advanced-queries-for-directory-objects-are-now-generally-available/

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
Nama tampilan grup.

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

### -DisplayNameStartsWith
Digunakan untuk menemukan grup yang dimulai dengan string yang disediakan.

```yaml
Type: System.String
Parameter Sets: SearchStringParameterSet
Aliases: SearchString

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
Parameter Sets: EmptyParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
kunci: id grup

```yaml
Type: System.Guid
Parameter Sets: ObjectIdParameterSet
Aliases:

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
Parameter Sets: EmptyParameterSet, DisplayNameParameterSet, SearchStringParameterSet
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
Parameter Sets: EmptyParameterSet, DisplayNameParameterSet, SearchStringParameterSet
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup

## CATATAN

ALIAS

## RELATED LINKS
