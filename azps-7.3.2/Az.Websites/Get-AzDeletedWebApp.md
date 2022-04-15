---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azdeletedwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzDeletedWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzDeletedWebApp.md
ms.openlocfilehash: 844ccd89ab306cb3b1ae846bfd1ca16f7260dd31
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142204597"
---
# Get-AzDeletedWebApp

## SYNOPSIS
Mendapatkan aplikasi web yang dihapus dalam langganan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/get-azdeletedwebapp) untuk informasi terbaru.

## SYNTAX

```
Get-AzDeletedWebApp [[-ResourceGroupName] <String>] [[-Name] <String>] [[-Slot] <String>] [-Location <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzDeletedWebApp** mengembalikan semua aplikasi web yang dihapus dalam langganan. Aplikasi yang dihapus secara opsional dapat difilter menurut grup sumber daya, nama, dan slot. Ada lebih dari satu aplikasi yang dihapus dengan nama dan grup sumber daya yang sama. Periksa DeletionTime untuk membedakan aplikasi yang dihapus yang memiliki nama yang sama.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzDeletedWebApp -ResourceGroupName "Default-Web-WestUS" -Name "ContosoSite"
```

Perintah ini mendapatkan aplikasi yang dihapus bernama ContosoSite milik grup sumber daya Default-Web-WestUS.

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

### -Lokasi
Lokasi aplikasi yang dihapus.

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
Nama aplikasi web.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -Slot
Nama slot aplikasi web.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.WebApps.Cmdlets.WebApps.PSAzureDeletedWebApp

## CATATAN

## RELATED LINKS

[Restore-AzDeletedWebApp](./Restore-AzDeletedWebApp.md)
