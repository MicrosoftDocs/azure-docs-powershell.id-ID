---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotCentral.dll-Help.xml
Module Name: Az.IotCentral
online version: https://docs.microsoft.com/powershell/module/az.iotcentral/get-aziotcentralapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/Get-AzIotCentralApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotCentral/IotCentral/help/Get-AzIotCentralApp.md
ms.openlocfilehash: 95270dd71111b19943dd8706cfda81bfa913b268
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140394059"
---
# Get-AzIotCentralApp

## SYNOPSIS
Mendapatkan properti untuk satu atau beberapa Aplikasi Pusat IoT.

## SYNTAX

### ListIotCentralAppsParameterSet (Default)
```
Get-AzIotCentralApp [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InteractiveIotCentralParameterSet
```
Get-AzIotCentralApp [-ResourceGroupName] <String> [-Name] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzIotCentralApp -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan metadata untuk Aplikasi Pusat IoT tertentu, atau semua aplikasi dalam Grup Sumber Daya atau Langganan, bergantung pada Kumpulan Parameter. 

## EXAMPLES

### Contoh 1 Dapatkan Aplikasi Pusat Iot Tertentu.
```powershell
PS C:\> Get-AzIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName"
```

Mendapatkan metadata untuk Aplikasi Pusat IoT tertentu.

Output Contoh:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft . IoTCentral/IoTApps/MyAppResourceName Nama: Tipe MyAppResourceName : Microsoft.IoTCentral/IoTApps Lokasi : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : Subdomain Nama Tampilan Kustom Saya : Template MyAppSubdomain : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName Identity : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity

### Contoh 2 Dapatkan Aplikasi Pusat IoT dalam Langganan.
```powershell
PS C:\> Get-AzIotCentralApp
```

Mendapatkan metadata untuk semua Aplikasi Pusat IoT dalam Langganan saat ini.

Output Contoh:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft . IoTCentral/IoTApps/MyAppResourceName Nama: Tipe MyAppResourceName : Microsoft.IoTCentral/IoTApps Lokasi : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : Subdomain Nama Tampilan Kustom Saya : Template MyAppSubdomain : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName Identity : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName2/providers/Microsoft . Nama IoTCentral/IoTApps/MyAppResourceName2 : Tipe MyAppResourceName2 : Microsoft.IoTCentral/IoTApps Lokasi : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : My Custom Display Name 2 Subdomain : Templat MyAppSubdomain2 : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName2 Identity : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity

### Contoh 3 Dapatkan Aplikasi Pusat IoT dalam Grup Sumber Daya.
```powershell
PS C:\> Get-AzIotCentralApp -ResourceGroupName "MyResourceGroupName"
```

Mendapatkan metadata untuk semua Aplikasi Pusat IoT dalam Grup Sumber Daya yang disediakan.

Output Contoh:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft . IoTCentral/IoTApps/MyAppResourceName Nama: Tipe MyAppResourceName : Microsoft.IoTCentral/IoTApps Lokasi : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : Subdomain Nama Tampilan Kustom Saya : Template MyAppSubdomain : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName Identity : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft . Nama IoTCentral/IoTApps/MyAppResourceName2 : Tipe MyAppResourceName2 : Microsoft.IoTCentral/IoTApps Lokasi : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : My Custom Display Name 2 Subdomain : Templat MyAppSubdomain2 : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName Identity : Microsoft.Azure.Management.IotCentral.Models.SystemAssignedServiceIdentity

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
Parameter Sets: ListIotCentralAppsParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp

## CATATAN

## RELATED LINKS
