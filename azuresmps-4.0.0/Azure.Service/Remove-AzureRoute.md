---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 5C8A79D1-32D4-4B30-AAC8-C6EF3B68017E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9d27f38a0aa19995db3f63f866927f4d46a8c851
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422067"
---
# Remove-AzureRoute

## SYNOPSIS
Menghapus rute dari tabel rute.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureRoute -RouteName <String> [-Force] -RouteTable <IRouteTable> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRoute** menghapus rute dari tabel rute.

## EXAMPLES

### Contoh 1: Menghapus rute
```
PS C:\> Get-AzureRouteTable -Name "ApplianceRouteTable" | Remove-AzureRoute -RouteName "InternetRoute"
Confirm
Are you sure you want to remove the Route "InternetRoute" from Route Table "ApplianceRouteTable"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute}                    AppRT                         Central US                    Appliance Route Table
```

Perintah ini mendapatkan tabel rute bernama TabelRoute.
Perintah melewati tabel rute itu ke cmdlet saat ini.
Cmdlet saat ini menghapus rute bernama InternetRoute.

## PARAMETERS

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteName
Menentukan nama untuk rute baru yang dihapus cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteTable
Menentukan tabel rute yang akan dihapus cmdlet ini.

```yaml
Type: IRouteTable
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Set-AzureRoute](./Set-AzureRoute.md)


