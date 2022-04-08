---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 25E3F297-1D91-4102-B4D3-1E7195A5D343
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/remove-aztrafficmanagercustomheaderfromprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerCustomHeaderFromProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerCustomHeaderFromProfile.md
ms.openlocfilehash: c143871ca48fadd0278dc9b9146805e77334152b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140498109"
---
# Remove-AzTrafficManagerCustomHeaderFromProfile

## SYNOPSIS
Menghapus informasi header kustom dari objek Traffic Manager profil kustom.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.trafficmanager/remove-aztrafficmanagercustomheaderfromprofile) untuk informasi terkini.

## SYNTAX

```
Remove-AzTrafficManagerCustomHeaderFromProfile -Name <String> -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzTrafficManagerCustomHeaderFromProfile** menghapus informasi header kustom dari objek Azure Traffic Manager profil lokal.
Anda dapat memperoleh profil menggunakan cmdlet New-AzTrafficManagerProfile Get-AzTrafficManagerProfile.

Cmdlet ini beroperasi pada objek profil lokal.
Lakukan perubahan ke profil untuk Traffic Manager dengan menggunakan cmdlet Set-AzTrafficManagerProfile cmdlet.

## EXAMPLES

### Contoh 1: Menghapus informasi header kustom dari profil
```
PS C:\> $TrafficManagerProfile = Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Remove-AzTrafficManagerCustomHeaderFromEndpoint -TrafficManagerProfile $TrafficManagerProfile -Name "host"
PS C:\> Set-AzTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet **Get-AzTrafficManagerProfile**.
Perintah kedua menghapus informasi header kustom dari profil yang disimpan di $TrafficManagerProfile.
Perintah terakhir memperbarui profil di Traffic Manager cocok dengan nilai lokal di $TrafficManagerProfile.

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

### -Nama
Menentukan nama informasi header kustom yang akan dihapus.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## CATATAN

## RELATED LINKS

[Add-AzTrafficManagerCustomHeaderToProfile](./Add-AzTrafficManagerCustomHeaderToProfile.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)
