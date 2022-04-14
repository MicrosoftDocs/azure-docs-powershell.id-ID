---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
Module Name: AzureRM.MachineLearning
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.machinelearning/new-azurermmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/New-AzureRmMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/New-AzureRmMlWebService.md
ms.openlocfilehash: 70704905063f120edd9f15bcda300707167c5d80
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141822353"
---
# New-AzureRmMlWebService

## SYNOPSIS
Membuat layanan web baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### BuatFromFile
```
New-AzureRmMlWebService -ResourceGroupName <String> -Location <String> -Name <String> -DefinitionFile <String>
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BuatFromInstance
```
New-AzureRmMlWebService -ResourceGroupName <String> -Location <String> -Name <String>
 -NewWebServiceDefinition <WebService> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat layanan web Azure Machine Learning dalam grup sumber daya yang sudah ada.
Jika layanan web dengan nama yang sama ada dalam grup sumber daya, panggilan bertindak sebagai operasi pembaruan dan layanan web yang sudah ada ditimpa.

## EXAMPLES

### Contoh 1: Membuat layanan baru dari definisi berbasis file Json
```
New-AzureRmMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -DefinitionFile "C:\mlservice.json"
```

Membuat layanan web Azure Machine Learning baru bernama "mywebservicename" dalam grup "myresourcegroup" dan kawasan South Central US, berdasarkan definisi yang ada dalam file json yang direferensikan.

### Contoh 2: Membuat layanan baru dari instans objek
```
New-AzureRmMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -NewWebServiceDefinition $serviceDefinitionObject
```

Anda bisa mendapatkan instans objek layanan web untuk dikustomisasi sebelum menerbitkan sebagai sumber daya dengan menggunakan cmdlet Import-AzureRmMlWebService.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionFile
Menspekuifikasikan jalur ke file yang berisi definisi format JSON dari layanan web.
Anda dapat menemukan spesifikasi terbaru untuk definisi layanan web dalam spesifikasi swagger di bawah https://github.com/Azure/azure-rest-api-specs/blob/master/specification/machinelearning/resource-manager/Microsoft.MachineLearning/.

```yaml
Type: System.String
Parameter Sets: CreateFromFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Jangan meminta konfirmasi.

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

### -Lokasi
Wilayah layanan web.
Masukkan kawasan pusat data Azure, seperti "AS Barat" atau "Asia Tenggara".
Anda bisa menempatkan layanan web di kawasan mana pun yang mendukung sumber daya tipe tersebut.
Layanan web tidak harus berada di kawasan yang sama dengan langganan Azure Anda atau kawasan yang sama dengan grup sumber dayanya.
Grup sumber daya bisa berisi layanan web dari kawasan yang berbeda.
Untuk menentukan wilayah mana yang mendukung setiap tipe sumber daya, gunakan Get-AzureRmResourceProvider dengan cmdlet parameter ProviderNamespace.

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

### -Nama
Nama untuk layanan web.
Nama harus unik dalam grup sumber daya.

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

### -NewWebServiceDefinition
Definisi untuk layanan web baru, berisi semua properti yang menyusun layanan.
Parameter ini diperlukan dan mewakili contoh kelas Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService.
Anda dapat menemukan spesifikasi terbaru untuk definisi layanan web dalam spesifikasi swagger di bawah https://github.com/Azure/azure-rest-api-specs/blob/master/specification/machinelearning/resource-manager/Microsoft.MachineLearning/stable/2017-01-01/webservices.json.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter Sets: CreateFromInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya tempat untuk menempatkan layanan web.
Masukkan kawasan pusat data Azure, seperti "AS Barat" atau "Asia Tenggara".
Anda bisa menempatkan layanan web di kawasan mana pun yang mendukung sumber daya tipe tersebut.
Layanan web tidak harus berada di kawasan yang sama dengan langganan Azure Anda atau kawasan yang sama dengan grup sumber dayanya.
Grup sumber daya bisa berisi layanan web dari kawasan yang berbeda.
Untuk menentukan wilayah mana yang mendukung setiap tipe sumber daya, gunakan Get-AzureRmResourceProvider dengan cmdlet parameter ProviderNamespace.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter: NewWebServiceDefinition (ByValue)

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## CATATAN
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
