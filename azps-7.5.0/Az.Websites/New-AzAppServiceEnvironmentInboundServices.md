---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azappserviceenvironmentinboundservices
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzAppServiceEnvironmentInboundServices.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzAppServiceEnvironmentInboundServices.md
ms.openlocfilehash: c623542983f019e01a702cca64d957b255bbf838
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144231836"
---
# New-AzAppServiceEnvironmentInboundServices

## SYNOPSIS
Membuat layanan masuk untuk lingkungan App Service. Untuk ASEv2 ILB, ini akan membuat Zona DNS Privat Azure dan rekaman untuk dipetakan ke IP internal. Untuk ASEv3, selain itu, pastikan subnet menonaktifkan Kebijakan Jaringan dan akan membuat titik akhir privat.

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
Cmdlet **New-AzAppServiceEnvironmentInboundServices** membuat layanan masuk untuk Lingkungan App Service.

## EXAMPLES

### Contoh 1: Membuat Zona DNS Privat dan rekaman untuk ASEv2
```powershell
New-AzAppServiceEnvironmentInboundServices -ResourceGroupName AseResourceGroup -Name AseV2Name -VirtualNetworkName MyVirtualNetwork -SubnetName InboundSubnet
```

Membuat Zona DNS Privat dan rekaman untuk ASEv2

### Contoh 2: Membuat titik akhir privat, Zona DNS Privat, dan rekaman untuk ASEv3
```powershell
New-AzAppServiceEnvironmentInboundServices -ResourceGroupName AseResourceGroup -Name AseV2Name -VirtualNetworkName MyVirtualNetwork -SubnetName InboundSubnet
```

Membuat titik akhir privat, Zona DNS Privat, dan rekaman untuk ASEv3

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

### -Name
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
Jangan membuat Zona dan rekaman DNS Privat Azure.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[New-AzAppServiceEnvironment](./New-AzAppServiceEnvironment.md)

[Get-AzAppServiceEnvironment](./Get-AzAppServiceEnvironment.md)

[Remove-AzAppServiceEnvironment](./Remove-AzAppServiceEnvironment.md)