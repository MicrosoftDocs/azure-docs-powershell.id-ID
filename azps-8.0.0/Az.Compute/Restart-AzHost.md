---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Restart-AzHost.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Restart-AzHost.md
ms.openlocfilehash: 6fbe77fea29d79be9067d9ad0700ec9bc97381a3
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145558497"
---
# Restart-AzHost

## SYNOPSIS
Mulai ulang host khusus.

## SYNTAX

### DefaultParameterSet (Default)
```
Restart-AzHost [-ResourceGroupName] <String> [-HostGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Restart-AzHost -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ObjectParameterSet
```
Restart-AzHost -InputObject <PSHost> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Mulai ulang host khusus. Operasi akan berhasil diselesaikan setelah host khusus dimulai ulang dan sedang berjalan. Untuk menentukan kesehatan VM yang disebarkan pada host khusus setelah mulai ulang, periksa Pusat Kesehatan Sumber Daya di Portal Microsoft Azure. Silakan merujuk untuk https://docs.microsoft.com/en-us/azure/service-health/resource-health-overview detail selengkapnya.

## EXAMPLES

### Contoh 1
```powershell
$Location = <Location>;
$ResourceGroupName = New-AzResourceGroup -Name $rgname -Location $Location -Force;

$hostGroupName = $ResourceGroupName + 'hostgroup'
New-AzHostGroup -ResourceGroupName $ResourceGroupName -Name $hostGroupName -Location $Location -PlatformFaultDomain 1  -Zone "2" -Tag @{key1 = "val1"};

$hostGroup = Get-AzHostGroup -ResourceGroupName $ResourceGroupName -Name $hostGroupName;
$hostName = $ResourceGroupName + 'host';
New-AzHost -ResourceGroupName $ResourceGroupName -HostGroupName $hostGroupName -Name $hostName -Location $Location -Sku "ESv3-Type1" -Tag @{key1 = "val2"};

$dedicatedHost = Get-AzHost -ResourceGroupName $ResourceGroupName -HostGroupName $hostGroupName -Name $hostName;
Restart-AzHost -ResourceGroupName $ResourceGroupName -HostGroupName $hostGroupName -Name $hostName;

# Check the status of the restart operation
$hostRestart = Get-AzHost -ResourceGroupName $rgname -HostGroupName $hostGroupName -Name $hostName -InstanceView;
$hostRestart.InstanceView.Statuses[1].DisplayStatus;
```

Contoh ini membuat grup host khusus dan host khusus. Kemudian mulai menghidupkan ulang host khusus, dan memeriksa status operasi hidupkan ulang ini.
Anda dapat mengkueri status operasi hidupkan ulang dengan `Get-AzHost` cmdlet menggunakan `-InstanceView` parameter .

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

### -HostGroupName
Nama grup host khusus.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Objek host khusus.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSHost
Parameter Sets: ObjectParameterSet
Aliases: Host

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama host khusus.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases: HostName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya ARM dari host khusus.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSHost

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSOperationStatusResponse

## NOTES

## RELATED LINKS
