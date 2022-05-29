---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudserviceroleinstanceremotedesktopfile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceRoleInstanceRemoteDesktopFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceRoleInstanceRemoteDesktopFile.md
ms.openlocfilehash: 7e022e8cdb8d78eebe60ce0f5b07e946b957f077
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145738252"
---
# Get-AzCloudServiceRoleInstanceRemoteDesktopFile

## SYNOPSIS
Mendapatkan file desktop jarak jauh untuk instans peran di layanan cloud.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/get-azcloudserviceroleinstanceremotedesktopfile) untuk informasi terbaru.

## SYNTAX

```
Get-AzCloudServiceRoleInstanceRemoteDesktopFile -CloudServiceName <String> -ResourceGroupName <String>
 -RoleInstanceName <String> -OutFile <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan file desktop jarak jauh untuk instans peran di layanan cloud.

## EXAMPLES

### Contoh 1: Mendapatkan file RDP
```powershell
Get-AzCloudServiceRoleInstanceRemoteDesktopFile -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS" -RoleInstanceName "ContosoFrontEnd_IN_0" -OutFile "C:\temp\ContosoFrontEnd_IN_0.rdp"
```

Perintah ini mendapatkan file RDP untuk instans peran bernama ContosoFrontEnd\_IN\_0 dari Layanan cloud bernama ContosoCS yang termasuk dalam grup sumber daya bernama ContosOrg.

## PARAMETERS

### -CloudServiceName
.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutFile
Jalur untuk menulis file output ke

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleInstanceName
Nama instans peran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS

