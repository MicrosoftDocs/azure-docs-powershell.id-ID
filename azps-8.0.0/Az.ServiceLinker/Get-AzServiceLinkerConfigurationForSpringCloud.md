---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.servicelinker/get-azservicelinkerconfigurationforspringcloud
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerConfigurationForSpringCloud.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerConfigurationForSpringCloud.md
ms.openlocfilehash: 84466bb707e86f4db2f9e237e3121c30f1f72673
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145529962"
---
# Get-AzServiceLinkerConfigurationForSpringCloud

## SYNOPSIS
mencantumkan konfigurasi sumber untuk linker di spring cloud.

## SYNTAX

```
Get-AzServiceLinkerConfigurationForSpringCloud -LinkerName <String> -AppName <String>
 -ResourceGroupName <String> -ServiceName <String> [-ResourceUri <String>] [-DefaultProfile <PSObject>]
 [-DeploymentName <String>] [-SubscriptionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
mencantumkan konfigurasi sumber untuk linker di spring cloud.

## EXAMPLES

### Contoh 1: Mendapatkan daftar konfigurasi linker spring cloud
```powershell
Get-AzServiceLinkerConfigurationForSpringCloud -ServiceName servicelinker-springcloud -AppName appconfiguration -ResourceGroupName servicelinker-test-group -LinkerName postgresql_linker |fl
```

```output
Name  : AZURE_POSTGRESQL_POSTGRESQL_NOVNET_CONNECTIONSTRING
Value : Server=test.postgres.database.azure.com;Database=testdb;Port=543 
        2;Ssl Mode=Require;User Id=testuser@test;Password=password;   

```

Mendapatkan daftar konfigurasi Linker

## PARAMETERS

### -AppName
Nama aplikasi layanan spring cloud yang akan disambungkan.

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

### -DeploymentName
Nama penyebaran aplikasi spring cloud yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: "default"
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkerName
Nama sumber daya Linker.

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

### -ResourceGroupName
Grup sumber daya sumber daya yang akan disambungkan.

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

### -ResourceUri
Pengidentifikasi Azure Resource manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

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

### -ServiceName
Nama layanan spring cloud yang akan disambungkan.

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
Mendapatkan ID langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ISourceConfiguration

## NOTES

ALIAS

## RELATED LINKS

