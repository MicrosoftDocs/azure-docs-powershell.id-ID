---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/update-azservicefabricvmimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Update-AzServiceFabricVmImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Update-AzServiceFabricVmImage.md
ms.openlocfilehash: 6743329d9f77c8f197c0c3448f899742d018dab1
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136374354"
---
# Update-AzServiceFabricVmImage

## SYNOPSIS

Perbarui pengaturan vmImage sumber daya kluster yang memetakan paket runtime yang sesuai untuk dikirimkan berdasarkan sistem operasi target.

## SYNTAX

```
Update-AzServiceFabricVmImage [-ResourceGroupName] <String> [-Name] <String> -VmImage <VmImageKind>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Gunakan **Update-AzServiceFabricVmImage** untuk memperbarui pengaturan vmImage kluster, yang bertanggung jawab atas pengiriman paket runtime.

Catatan Penting: VmImage 'Linux' serta peta 'Ubuntu' untuk pengiriman paket Ubuntu 16.04, jadi jika tujuannya adalah untuk menjalankan Ubuntu18+, gunakan Ubuntu18_04.

## EXAMPLES

### Contoh 1

```powershell
Update-AzServiceFabricVmImage -ResourceGroupName 'Group1' -ClusterName 'Contoso01SFCluster' -VmImage Ubuntu18_04
```

Perintah ini mengubah vmImage kluster 'Contoso01SFCluster' menjadi 'Ubuntu18_04', untuk tujuan melakukan migrasi pemutakhiran yang akan datang untuk menggunakan paket runtime deb Ubuntu 18 SF.

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

Tentukan nama kluster, jika tidak akan sama dengan nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName

Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmImage
Tentukan vmImage target umum yang akan digunakan untuk kluster.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.VmImageKind
Parameter Sets: (All)
Aliases:
Accepted values: Windows, Linux, Ubuntu, Ubuntu18_04

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

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.ServiceFabric.Models.VmImageKind

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSDeploymentResult

## CATATAN

## RELATED LINKS
