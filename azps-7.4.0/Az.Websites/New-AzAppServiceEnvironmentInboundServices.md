---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azappserviceenvironmentinboundservices
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzAppServiceEnvironmentInboundServices.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzAppServiceEnvironmentInboundServices.md
ms.openlocfilehash: c623542983f019e01a702cca64d957b255bbf838
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142736722"
---
# New-AzAppServiceEnvironmentInboundServices

## SYNOPSIS
Membuat layanan masuk untuk Lingkungan App Service. Untuk ASEv2 ILB, tindakan ini akan membuat Azure Private DNS Zone dan rekaman untuk dipetakan ke IP internal. Untuk ASEv3, subnet akan dinonaktifkan dan akan membuat titik akhir privat.

## SYNTAX

### SubnetNameParameterSet (Default)
```
New-AzAppServiceEnvironmentInboundServices [-ResourceGroupName] <String> [-Name] <String>
 -VirtualNetworkName <String> -SubnetName <String> [-SkipDns] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SubnetIdParameterSet
```
New-AzAppServiceEnvironmentInboundServices [-ResourceGroupName] <String> [-Name] <String> -SubnetId <String>
 [-SkipDns] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAppServiceEnvironmentInboundServices** menciptakan layanan masuk untuk Lingkungan App Service.

## EXAMPLES

### Contoh 1: Membuat Zona DNS Pribadi dan catatan untuk ASEv2
```powershell
New-AzAppServiceEnvironmentInboundServices -ResourceGroupName AseResourceGroup -Name AseV2Name -VirtualNetworkName MyVirtualNetwork -SubnetName InboundSubnet
```

Membuat Zona DNS Pribadi dan catatan untuk ASEv2

### Contoh 2: Membuat titik akhir privat, Zona DNS Pribadi dan catatan untuk ASEv3
```powershell
New-AzAppServiceEnvironmentInboundServices -ResourceGroupName AseResourceGroup -Name AseV2Name -VirtualNetworkName MyVirtualNetwork -SubnetName InboundSubnet
```

Membuat titik akhir pribadi, Zona DNS Pribadi, dan catatan untuk ASEv3

### Contoh 3: Membuat titik akhir privat untuk ASEv3
```powershell
New-AzAppServiceEnvironmentInboundServices -ResourceGroupName AseResourceGroup -Name AseV2Name -VirtualNetworkName MyVirtualNetwork -SubnetName InboundSubnet -SkipDns
```

Membuat titik akhir privat untuk ASEv3

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
Nama lingkungan layanan aplikasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan status.

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
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipDns
Jangan buat Azure Private DNS Zone dan rekaman.

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

### -SubnetId
Id subnet.

```yaml
Type: System.String
Parameter Sets: SubnetIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Nama subnet. Digunakan dalam kombinasi dengan -VirtualNetworkName dan harus berada dalam grup sumber daya yang sama dengan ASE. Jika tidak, gunakan -SubnetId

```yaml
Type: System.String
Parameter Sets: SubnetNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama vNet. Digunakan dalam kombinasi dengan -SubnetName dan harus berada dalam grup sumber daya yang sama dengan ASE. Jika tidak, gunakan -SubnetId

```yaml
Type: System.String
Parameter Sets: SubnetNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[New-AzAppServiceEnvironment](./New-AzAppServiceEnvironment.md)

[Get-AzAppServiceEnvironment](./Get-AzAppServiceEnvironment.md)

[Remove-AzAppServiceEnvironment](./Remove-AzAppServiceEnvironment.md)