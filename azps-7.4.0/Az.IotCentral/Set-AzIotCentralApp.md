---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotCentral.dll-Help.xml
Module Name: Az.IotCentral
online version: https://docs.microsoft.com/powershell/module/az.iotcentral/set-aziotcentralapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/Set-AzIotCentralApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/Set-AzIotCentralApp.md
ms.openlocfilehash: 866cf0f8984b16a8e4849364f423d5eef90df840
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142422906"
---
# Set-AzIotCentralApp

## SYNOPSIS
Memperbarui metadata untuk Aplikasi Pusat IoT.

## SYNTAX

### ResourceIdParameterSet (Default)
```
Set-AzIotCentralApp [-DisplayName <String>] [-Subdomain <String>] [-Tag <Hashtable>] [-Sku <String>] [-Identity <String>]
 -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectParameterSet
```
Set-AzIotCentralApp [-DisplayName <String>] [-Subdomain <String>] [-Tag <Hashtable>] [-Sku <String>] [-Identity <String>]
 -InputObject <PSIotCentralApp> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InteractiveIotCentralParameterSet
```
Set-AzIotCentralApp [-DisplayName <String>] [-Subdomain <String>] [-Tag <Hashtable>] [-Sku <String>] [-Identity <String>] [-AsJob]
 [-ResourceGroupName] <String> [-Name] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Perbarui metadata untuk Aplikasi Pusat IoT. 

## EXAMPLES

### Contoh 1 Perbarui Nama Tampilan
```powershell
Set-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -DisplayName "My New Custom Display Name"
```

```output
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft
                    .IoTCentral/IoTApps/MyAppResourceName
Name              : MyAppResourceName
Type              : Microsoft.IoTCentral/IoTApps
Location          : westus
Tag               : 
Sku               : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo
ApplicationId     : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
DisplayName       : My New Custom Display Name
Subdomain         : MyAppSubdomain
Template          : iotc-default@1.0.0
SubscriptionId    : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
ResourceGroupName : MyResourceGroupName
Identity          : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity
```
Perbarui nama Tampilan pada Aplikasi Pusat IoT yang sudah ada.
### Contoh 2 Perbarui Subdomain
```powershell
Set-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Subdomain "new-subdomain"
```

```output
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft
                    .IoTCentral/IoTApps/MyAppResourceName
Name              : MyAppResourceName
Type              : Microsoft.IoTCentral/IoTApps
Location          : westus
Tag               : 
Sku               : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo
ApplicationId     : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
DisplayName       : Display Name
Subdomain         : new-subdomain
Template          : iotc-default@1.0.0
SubscriptionId    : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
ResourceGroupName : MyResourceGroupName
Identity          : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity
```
Perbarui nama Tampilan pada Aplikasi Pusat IoT yang sudah ada.
### Contoh 3 Perbarui Sku Info Aplikasi
```powershell
Set-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Sku "ST2"
```

```output
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft
                    .IoTCentral/IoTApps/MyAppResourceName
Name              : MyAppResourceName
Type              : Microsoft.IoTCentral/IoTApps
Location          : westus
Tag               : 
Sku               : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo
ApplicationId     : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
DisplayName       : Display Name
Subdomain         : MyAppSubdomain
Template          : iotc-default@1.0.0
SubscriptionId    : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
ResourceGroupName : MyResourceGroupName
Identity          : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity
```
Perbarui sku pada Aplikasi Pusat IoT yang sudah ada.
## PARAMETERS

### -AsJob
Jalankan cmdlet sebagai pekerjaan di latar belakang.

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

### -DisplayName
Nama Tampilan Kustom Aplikasi Pusat Iot.

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

### -InputObject
Objek Input Aplikasi Pusat Iot.

```yaml
Type: Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Sumber Daya Aplikasi Pusat Iot.

```yaml
Type: System.String
Parameter Sets: InteractiveIotCentralParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: InteractiveIotCentralParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya Aplikasi Pusat Iot.

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

### -Sku
Tingkat harga untuk aplikasi Pusat IoT.
Nilai defaultnya adalah ST2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subdomain
Subdomain dari Aplikasi Pusat IoT.

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

### -Tag
Iot Central Application Resource Tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitas
Tipe identitas terkelola untuk aplikasi IoT Central.
Nilai defaultnya tidak ada. Identitas terkelola yang ditetapkan sistem didukung.

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

### System.String

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp

## OUTPUTS

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp

## CATATAN

## RELATED LINKS
