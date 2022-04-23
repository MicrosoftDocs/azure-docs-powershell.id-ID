---
external help file: Microsoft.Azure.Commands.IotCentral.dll-Help.xml
Module Name: AzureRM.IotCentral
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.iotcentral/get-azurermiotcentralapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/IotCentral/Commands.IotCentral/help/Get-AzureRmIotCentralApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/IotCentral/Commands.IotCentral/help/Get-AzureRmIotCentralApp.md
ms.openlocfilehash: fdf674b5ec2dfcefe8fcada92cfaf0fd1073f7f3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143162480"
---
# Get-AzureRmIotCentralApp

## SYNOPSIS
Mendapatkan properti untuk satu atau beberapa Aplikasi Pusat IoT.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ListIotCentralAppsParameterSet (Default)
```
Get-AzureRmIotCentralApp [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InteractiveIotCentralParameterSet
```
Get-AzureRmIotCentralApp [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzureRmIotCentralApp -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan metadata untuk Aplikasi Pusat IoT tertentu, atau semua aplikasi dalam Grup Sumber Daya atau Langganan, bergantung pada Kumpulan Parameter. 

## EXAMPLES

### Contoh 1 Dapatkan Aplikasi Pusat IoT Tertentu.
```powershell
PS C:\> Get-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName"
```

Mendapatkan metadata untuk Aplikasi Pusat IoT yang ditentukan.

Contoh Output:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName Name : MyAppResourceName Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : My Custom Display Name Subdomain : MyAppSubdomain Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

### Contoh 2 Dapatkan Aplikasi Pusat IoT dalam Langganan.
```powershell
PS C:\> Get-AzureRmIotCentralApp
```

Mendapatkan metadata untuk semua Aplikasi Pusat IoT dalam Langganan saat ini.

Contoh Output:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName Name : MyAppResourceName Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : My Custom Display Name Subdomain : MyAppSubdomain Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName2/providers/Microsoft . IoTCentral/IoTApps/MyAppResourceName2 Nama : MyAppResourceName2 Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXX DisplayName : My Custom Display Name 2 Subdomain : MyAppSubdomain2 Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX ResourceGroupName : MyResourceGroupName2

### Contoh 3 Dapatkan Aplikasi Pusat IoT dalam Grup Sumber Daya.
```powershell
PS C:\> Get-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName"
```

Mendapatkan metadata untuk semua Aplikasi Pusat IoT dalam Grup Sumber Daya yang disediakan.

Contoh Output:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName Name : MyAppResourceName Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXX DisplayName : My Custom Display Name Subdomain : MyAppSubdomain Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName2 Nama : MyAppResourceName2 Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : {[key, val]} Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXX DisplayName : My Custom Display Name 2 Subdomain : MyAppSubdomain2 Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Sumber Daya Aplikasi Pusat Iot.

```yaml
Type: String
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
Type: String
Parameter Sets: ListIotCentralAppsParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
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
Type: String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp
## NOTES

## RELATED LINKS
