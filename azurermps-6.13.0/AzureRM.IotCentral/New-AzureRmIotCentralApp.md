---
external help file: Microsoft.Azure.Commands.IotCentral.dll-Help.xml
Module Name: AzureRM.IotCentral
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.iotcentral/new-azurermiotcentralapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/IotCentral/Commands.IotCentral/help/New-AzureRmIotCentralApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/IotCentral/Commands.IotCentral/help/New-AzureRmIotCentralApp.md
ms.openlocfilehash: d0bb10324c1a97b6228a26a7ab079edb4845d48a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141884724"
---
# New-AzureRmIotCentralApp

## SYNOPSIS
Membuat Aplikasi Pusat IoT baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmIotCentralApp [-Subdomain] <String> [-DisplayName <String>] [-Template <String>] [-Sku <String>]
 [-Location <String>] [-Tag <Hashtable>] [-AsJob] [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Aplikasi Pusat IoT baru dengan properti dan metadata yang disediakan. Untuk pengenalan IoT Central, lihat https://docs.microsoft.com/en-us/azure/iot-central/.

## EXAMPLES

### Contoh 1 Buat Aplikasi Pusat IoT sederhana.
```powershell
PS C:\> New-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Subdomain "MyAppSubdomain"
```

Contoh Output:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName Name : MyAppResourceName Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentRalAppSkuInfo ApplicationId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX DisplayName : MyAppResourceName Subdomain : MyAppSubdomain Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

Buat aplikasi IoT Central di tingkat harga standar S1, di kawasan grup sumber daya.

### Contoh 2 Buat Aplikasi Pusat IoT sederhana.
```powershell
PS C:\> New-AzureRmIotCentralApp -ResourceGroupName "MyResourceGroupName" -Name "MyAppResourceName" -Subdomain "MyAppSubdomain" -Sku "S1" -DisplayName "My Custom Display Name" -Template "iotc-default" -Location "westus"
```

Contoh Output:

ResourceId : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXX/resourceGroups/MyResourceGroupName/providers/Microsoft. IoTCentral/IoTApps/MyAppResourceName Name : MyAppResourceName Type : Lokasi Microsoft.IoTCentral/IoTApps : westus Tag : Sku : Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralAppskuInfo ApplicationId : XXXXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXX DisplayName : Subdomain Nama Tampilan Kustom Saya : MyAppsubdomain Template : iotc-default@1.0.0  SubscriptionId : XXXXXXXX-XXXX-XXXX-XXXXXXXXXXX ResourceGroupName : MyResourceGroupName

Buat aplikasi IoT Central dengan tingkat harga standar S1 di wilayah 'westus', dengan nama tampilan kustom, berdasarkan templat default iotc.

## PARAMETERS

### -AsJob
Jalankan cmdlet sebagai pekerjaan di latar belakang.

```yaml
Type: SwitchParameter
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Type: String
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
Type: String
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
Type: String
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
Type: String
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
Nilai defaultnya adalah S1.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: S1

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
Type: String
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
Type: Hashtable
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
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
### System.Collections.Hashtable
## OUTPUTS

### Microsoft.Azure.Commands.IotCentral.Models.PSIotCentralApp
## CATATAN

## RELATED LINKS
