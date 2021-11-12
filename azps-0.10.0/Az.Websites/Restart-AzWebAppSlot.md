---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.WebSites
ms.assetid: 645E74D2-640D-494F-9798-4375FE6A0AF2
online version: https://docs.microsoft.com/en-us/powershell/module/Az.websites/restart-Azwebappslot
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Websites/Websites/help/Restart-AzWebAppSlot.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Websites/Websites/help/Restart-AzWebAppSlot.md
ms.openlocfilehash: 9f0e48b20d19113290784d65b6bc78531dc7b2a1
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422816"
---
# Restart-AzWebAppSlot

## SYNOPSIS

## SYNTAX

### S1
```
Restart-AzWebAppSlot [-ResourceGroupName] <String> [-Name] <String> [-Slot] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
Restart-AzWebAppSlot [-WebApp] <Site> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restart-AzWebAppSlot** berhenti dan memulai Slot Azure Web App.
Jika Slot Web App berada dalam status berhenti, gunakan cmdlet Start-AzWebAppSlot.

## EXAMPLES

### Contoh 1
```
PS C:\> Restart-AzWebAppSlot -ResourceGroupName "Default-Web-WestUS" -Name "ContosoWebApp" -Slot "Slot001"
```

Perintah ini memulai ulang slot Slot001 untuk aplikasi web ContosoWebApp yang terkait dengan grup sumber daya Default-Web-WestUS

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama WebApp

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Nama Slot WebApp

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Objek WebApp

```yaml
Type: Site
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Situs
Parameter 'WebApp' menerima nilai tipe 'Situs' dari saluran

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzWebAppslot](./Get-AzWebAppSlot.md)

[New-AzWebAppslot](./New-AzWebAppSlot.md)

[Remove-AzWebAppslot](./Remove-AzWebAppSlot.md)

[Set-AzWebAppslot](./Set-AzWebAppSlot.md)

[Start-AzWebAppslot](./Start-AzWebAppSlot.md)

[Stop-AzWebAppslot](./Stop-AzWebAppSlot.md)

[Get-AzWebApp](./Get-AzWebApp.md)
