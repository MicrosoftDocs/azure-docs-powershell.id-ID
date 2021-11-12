---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/en-us/powershell/module/az.servicebus/start-azservicebusmigration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/ServiceBus/ServiceBus/help/Start-AzServiceBusMigration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/ServiceBus/ServiceBus/help/Start-AzServiceBusMigration.md
ms.openlocfilehash: 0837532c6e708b4ff7d8cbee4f5ad231b4032347
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406424"
---
# Start-AzServiceBusMigration

## SYNOPSIS
Membuat konfigurasi Migrasi baru dan memulai migrasi entitas dari Standar ke Premium nama

## SINTAKS

```
Start-AzServiceBusMigration [-ResourceGroupName] <String> [-Name] <String> [-TargetNameSpace] <String>
 [-PostMigrationName] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Start-AzServiceBusMigration** membuat konfigurasi Migrasi baru dan mulai melakukan migrasi entitas dari Standar ke Premium namanya

## CONTOH

### Contoh 1
```powershell
PS C:\> Start-AzServiceBusMigration -ResourceGroupName ResourceGroup -Name TestingNamespaceStandardMigration -TargetNameSpace /subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/TestingNamespacePremiumMigration -PostMigrationName TestingNamespaceStandardMigrationPostMigration

Name              : TestingNamespaceStandardMigration
Id                : /subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/TestingNamespaceStandardMigration/migrationConfigurations/$default
Type              : Microsoft.ServiceBus/Namespaces/migrationconfigurations
ProvisioningState : Accepted
TargetNamespace   : /subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/TestingNamespacePremiumMigration
PostMigrationName : TestingNamespaceStandardMigrationPostMigration
```

Membuat konfigurasi migrasi baru untuk ruang nama 'TestingNamespaceStandardMigration' menjadi 'TestingNamespacePremiumMigration'

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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
Nama Ruang Nama Standar

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

### -PostMigrationName
Pasca Nama Migrasi untuk Ruang Nama Standar di Migrasi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

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

### -TargetNameSpace
Premium Nama Nama ID ARM

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes

## CATATAN

## LINK TERKAIT
