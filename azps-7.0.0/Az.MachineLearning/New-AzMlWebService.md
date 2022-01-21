---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/new-azmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/New-AzMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/New-AzMlWebService.md
ms.openlocfilehash: 86dd355441aeea1d272d10f2c5b89b44abd804d6
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136541384"
---
# New-AzMlWebService

## SYNOPSIS
Membuat layanan web baru.

## SYNTAX

### CreateFromFile
```
New-AzMlWebService -ResourceGroupName <String> -Location <String> -Name <String> -DefinitionFile <String>
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateFromInstance
```
New-AzMlWebService -ResourceGroupName <String> -Location <String> -Name <String>
 -NewWebServiceDefinition <WebService> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat layanan Azure Machine Learning web dalam grup sumber daya yang sudah ada.
Jika ada layanan web dengan nama yang sama dalam grup sumber daya, panggilan bertindak sebagai operasi pembaruan dan layanan web yang sudah ada ditimpa.

## EXAMPLES

### Contoh 1: Buat layanan baru dari definisi berbasis file Json
```
New-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -DefinitionFile "C:\mlservice.json"
```

Membuat layanan web Azure Machine Learning bernama "mywebservicename" dalam grup "myresourcegroup" dan kawasan AS Tengah Selatan, berdasarkan definisi yang ada dalam file json yang direferensikan.

### Contoh 2: Membuat layanan baru dari contoh objek
```
New-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -NewWebServiceDefinition $serviceDefinitionObject
```

Anda bisa mendapatkan contoh objek layanan web untuk dikustomisasi sebelum menerbitkan sebagai sumber daya dengan menggunakan cmdlet Import-AzMlWebService.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -DefinitionFile
Menentukan jalur ke file yang berisi definisi format JSON dari layanan web.
Anda dapat menemukan spesifikasi terbaru untuk definisi layanan web di spesifikasi di bawah https://github.com/Azure/azure-rest-api-specs/blob/master/specification/machinelearning/resource-manager/Microsoft.MachineLearning/ .

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

### -Force
Jangan minta konfirmasi.

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
Kawasan layanan web.
Masukkan kawasan pusat data Azure, seperti "AS Barat" atau "Asia Tenggara".
Anda bisa menempatkan layanan web di kawasan mana pun yang mendukung sumber daya tipe itu.
Layanan web tidak harus berada di kawasan yang sama dengan langganan Azure Anda atau kawasan yang sama dengan grup sumber dayanya.
Grup sumber daya bisa berisi layanan web dari wilayah yang berbeda.
Untuk menentukan kawasan yang mendukung setiap tipe sumber daya, Get-AzResourceProvider dengan cmdlet parameter ProviderNamespace.

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
Definisi untuk layanan web baru, berisi semua properti yang menjadi dasar layanan.
Parameter ini diperlukan dan mewakili instans kelas Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService.
Anda dapat menemukan spesifikasi terbaru untuk definisi layanan web di spesifikasi di bawah https://github.com/Azure/azure-rest-api-specs/blob/master/specification/machinelearning/resource-manager/Microsoft.MachineLearning/stable/2017-01-01/webservices.json .

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
Grup sumber daya di mana menempatkan layanan web.
Masukkan kawasan pusat data Azure, seperti "AS Barat" atau "Asia Tenggara".
Anda bisa menempatkan layanan web di kawasan mana pun yang mendukung sumber daya tipe itu.
Layanan web tidak harus berada di kawasan yang sama dengan langganan Azure Anda atau kawasan yang sama dengan grup sumber dayanya.
Grup sumber daya bisa berisi layanan web dari wilayah yang berbeda.
Untuk menentukan kawasan yang mendukung setiap tipe sumber daya, Get-AzResourceProvider dengan cmdlet parameter ProviderNamespace.

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

## INPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS
