---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM.WebSites
ms.assetid: A87ED954-9C09-4329-A005-ABFF36C45E6E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/get-azurermwebapp
schema: 2.0.0
ms.openlocfilehash: eb1f96eaf85e6a5e7234e09c319b2e0c1117d456
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142391826"
---
# Get-AzureRmWebApp

## SYNOPSIS
Mendapatkan azure Web Apps dalam grup sumber daya tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
Get-AzureRmWebApp [[-ResourceGroupName] <String>] [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S2
```
Get-AzureRmWebApp [-AppServicePlan] <AppServicePlan> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S3
```
Get-AzureRmWebApp [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmWebApp** mendapatkan informasi tentang Azure Web App.

## EXAMPLES

### Contoh 1: Dapatkan Aplikasi Web dari grup sumber daya
```
PS C:\>Get-AzureRmWebApp -ResourceGroupName "Default-Web-WestUS" -Name "ContosoSite"
```

Perintah ini mendapatkan Web App bernama ContosoSite yang termasuk dalam grup sumber daya Default-Web-WestUS.

## PARAMETERS

### -AppServicePlan
objek Rencana App Service

```yaml
Type: AppServicePlan
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi

```yaml
Type: String
Parameter Sets: S3
Aliases: 

Required: True
Position: 0
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

Required: False
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

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.Site

## CATATAN

## RELATED LINKS

[Baru-AzureRmWebApp](./New-AzureRmWebApp.md)

[Hapus-AzureRmWebApp](./Remove-AzureRmWebApp.md)

[Mulai ulang-AzureRmWebApp](./Restart-AzureRmWebApp.md)

[Start-AzureRmWebApp](./Start-AzureRmWebApp.md)

[Stop-AzureRmWebApp](./Stop-AzureRmWebApp.md)


