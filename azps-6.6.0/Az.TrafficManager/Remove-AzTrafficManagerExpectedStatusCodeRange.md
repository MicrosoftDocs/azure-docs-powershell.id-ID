---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 25E3F297-1D91-4102-B4D3-1E7195A5D344
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/remove-aztrafficmanagerexpectedstatuscoderange
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerExpectedStatusCodeRange.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerExpectedStatusCodeRange.md
ms.openlocfilehash: 734c10b2587449438702e477acf8f360b20b8f7f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142295917"
---
# Remove-AzTrafficManagerExpectedStatusCodeRange

## SYNOPSIS
Menghapus rentang kode status yang diharapkan dari objek profil Traffic Manager lokal.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.trafficmanager/remove-aztrafficmanagerexpectedstatuscoderange) untuk informasi terbaru.

## SYNTAX

```
Remove-AzTrafficManagerExpectedStatusCodeRange -Min <Int32> -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzTrafficManagerExpectedStatusCodeRange** menghapus rentang kode status yang diharapkan dari objek profil Azure Traffic Manager lokal.
Anda bisa mendapatkan profil dengan menggunakan cmdlet New-AzTrafficManagerProfile atau Get-AzTrafficManagerProfile.

Cmdlet ini beroperasi pada objek profil lokal.
Lakukan perubahan anda ke profil untuk Traffic Manager dengan menggunakan cmdlet Set-AzTrafficManagerProfile.

## EXAMPLES

### Contoh 1: Menghapus rentang kode status yang diharapkan dari profil
```
PS C:\> $TrafficManagerProfile = Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Remove-AzTrafficManagerExpectedStatusCodeRange -TrafficManagerProfile $TrafficManagerProfile -Min 200
PS C:\> Set-AzTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet **Get-AzTrafficManagerProfile**.
Perintah kedua menghapus rentang kode status yang diharapkan dari profil yang disimpan di $TrafficManagerProfile.
Perintah terakhir memperbarui profil di Traffic Manager agar sesuai dengan nilai lokal dalam $TrafficManagerProfile.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Min
Menentukan nilai terendah dalam rentang kode status yang akan dihapus.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Menentukan objek **TrafficManagerProfile** lokal.
Cmdlet ini mengubah objek lokal ini.
Untuk mendapatkan objek **TrafficManagerProfile** , gunakan cmdlet Get-AzTrafficManagerProfile.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## CATATAN

## RELATED LINKS

[Add-AzTrafficManagerExpectedStatusCodeRange](./Add-AzTrafficManagerExpectedStatusCodeRange.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)
