---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotCentral.dll-Help.xml
Module Name: Az.IotCentral
online version: https://docs.microsoft.com/powershell/module/az.iotcentral/new-aziotcentralapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/New-AzIotCentralApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/New-AzIotCentralApp.md
ms.openlocfilehash: 97fdb151b0d2e9b8af4c596e7df778fab4cdd6e9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143227169"
---
# New-AzIotCentralApp

## SYNOPSIS
Membuat Aplikasi Pusat IoT baru.

## SYNTAX

```
New-AzIotCentralApp [-Subdomain] <String> [-DisplayName <String>] [-Template <String>] [-Sku <String>] [-Identity <String>]
 [-Location <String>] [-Tag <Hashtable>] [-AsJob] [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Aplikasi Pusat IoT baru dengan properti dan metadata yang disediakan. Untuk pengenalan IoT Central, lihat https://docs.microsoft.com/azure/iot-central/.

## EXAMPLES

### Contoh 1 Buat Aplikasi Pusat IoT sederhana.
```powershell
New-AzIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Subdomain "MyAppSubdomain"
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
DisplayName       : MyAppResourceName
Subdomain         : MyAppSubdomain
Template          : iotc-default@1.0.0
SubscriptionId    : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
ResourceGroupName : MyResourceGroupName
Identity          : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity
```
Buat aplikasi IoT Central di st2 tingkat harga standar, di wilayah grup sumber daya.

### Contoh 2 Buat Aplikasi Pusat IoT sederhana.
```powershell
New-AzIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Subdomain "MyAppSubdomain" -Sku "ST2" -DisplayName "My Custom Display Name" -Template "iotc-default" -Location "westus"
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
DisplayName       : My Custom Display Name
Subdomain         : MyAppSubdomain
Template          : iotc-default@1.0.0
SubscriptionId    : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
ResourceGroupName : MyResourceGroupName
Identity          : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity
```
Buat aplikasi IoT Central dengan tingkat harga standar ST2 di wilayah 'westus', dengan nama tampilan kustom, berdasarkan templat default iotc.

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
Nama tampilan kustom untuk aplikasi Pusat IoT.
Defaultnya adalah nama sumber daya.

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

### -Lokasi
Lokasi aplikasi IoT Central Anda.
Default adalah lokasi grup sumber daya target.

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

### -Nama
Nama Sumber Daya Aplikasi Pusat Iot.

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

### -ResourceGroupName
Nama Grup Sumber Daya.

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
Subdomain untuk URL Pusat IoT.
Setiap aplikasi harus memiliki subdomain yang unik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Templat
Nama templat aplikasi IoT Central.
Defaultnya adalah aplikasi kustom.

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp

## NOTES

## RELATED LINKS
