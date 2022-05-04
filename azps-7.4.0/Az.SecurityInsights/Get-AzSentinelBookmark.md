---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelbookmark
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelBookmark.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelBookmark.md
ms.openlocfilehash: 81873d969d5ef399d19ab4029d3f178ed6592bf3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144597362"
---
# Get-AzSentinelBookmark

## SYNOPSIS
Mendapatkan Bookmark. <br/>
Bookmark digunakan untuk mempertahankan kueri, komentar, dan tag untuk insiden tertentu.<br/>
Anda membuat Bookmark terlebih dahulu lalu menambahkannya ke insiden.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/get-azsentinelbookmark) untuk informasi terbaru.

## SYNTAX

### WorkspaceScope (Default)
```
Get-AzSentinelBookmark -ResourceGroupName <String> -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BookmarkId.
```
Get-AzSentinelBookmark -ResourceGroupName <String> -WorkspaceName <String> -BookmarkId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzSentinelBookmark -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelBookmark** mendapatkan Bookmark dari ruang kerja yang ditentukan.
Jika Anda menentukan parameter *BookmarkId* , satu objek Bookmark dikembalikan.
Jika Anda tidak menentukan parameter *BookmarkId* , array yang berisi semua Bookmark di ruang kerja yang ditentukan akan dikembalikan.
Anda dapat menggunakan objek Bookmark untuk memperbarui Bookmark, misalnya Anda bisa menambahkan Tag dan Mencatat **Bookmark**.

## EXAMPLES

### Contoh 1
```powershell
$Bookmarks = Get-AzSentinelBookmark -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName"
```

Contoh ini mendapatkan semua Bookmark di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $Bookmarks.

### Contoh 2
```powershell
$Bookmark = Get-AzSentinelBookmark -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -BookmarkId "MyBookmarkId"
```

Contoh ini mendapatkan Bookmark di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $Bookmark.

## PARAMETERS

### -BookmarkId
Id Bookmark,

```yaml
Type: System.String
Parameter Sets: BookmarkId.
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, BookmarkId.
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, BookmarkId.
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark
## NOTES

## RELATED LINKS
