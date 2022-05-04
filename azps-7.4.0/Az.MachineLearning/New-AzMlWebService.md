---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/new-azmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/New-AzMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/New-AzMlWebService.md
ms.openlocfilehash: eb90997060e52c2c65ac95df58f2c29faaea6afb
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144683490"
---
# New-AzMlWebService

## SYNOPSIS
Membuat layanan web baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.machinelearning/new-azmlwebservice) untuk informasi terbaru.

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
Membuat layanan web Azure Machine Learning di grup sumber daya yang sudah ada.
Jika layanan web dengan nama yang sama ada di grup sumber daya, panggilan bertindak sebagai operasi pembaruan dan layanan web yang ada ditimpa.

## EXAMPLES

### Contoh 1: Membuat layanan baru dari definisi berbasis file Json
```powershell
New-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -DefinitionFile "C:\mlservice.json"
```

Membuat layanan web Azure Machine Learning baru bernama "mywebservicename" di grup "myresourcegroup" dan wilayah US Tengah Selatan, berdasarkan definisi yang ada dalam file json yang direferensikan.

### Contoh 2: Membuat layanan baru dari instans objek
```powershell
New-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Location "South Central US" -NewWebServiceDefinition $serviceDefinitionObject
```

Anda dapat memperoleh instans objek layanan web untuk disesuaikan sebelum menerbitkan sebagai sumber daya dengan menggunakan cmdlet Import-AzMlWebService.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Force
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
Masukkan wilayah pusat data Azure, seperti "US Barat" atau "Asia Tenggara".
Anda dapat menempatkan layanan web di wilayah mana pun yang mendukung sumber daya jenis tersebut.
Layanan web tidak harus berada di wilayah yang sama dengan langganan Azure Anda atau wilayah yang sama dengan grup sumber dayanya.
Grup sumber daya dapat berisi layanan web dari berbagai wilayah.
Untuk menentukan wilayah mana yang mendukung setiap jenis sumber daya, gunakan Get-AzResourceProvider dengan cmdlet parameter ProviderNamespace.

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

### -Name
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
Definisi untuk layanan web baru, berisi semua properti yang membentuk layanan.
Parameter ini diperlukan dan mewakili instans kelas Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService.
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
Grup sumber daya untuk menempatkan layanan web.
Masukkan wilayah pusat data Azure, seperti "US Barat" atau "Asia Tenggara".
Anda dapat menempatkan layanan web di wilayah mana pun yang mendukung sumber daya jenis tersebut.
Layanan web tidak harus berada di wilayah yang sama dengan langganan Azure Anda atau wilayah yang sama dengan grup sumber dayanya.
Grup sumber daya dapat berisi layanan web dari berbagai wilayah.
Untuk menentukan wilayah mana yang mendukung setiap jenis sumber daya, gunakan Get-AzResourceProvider dengan cmdlet parameter ProviderNamespace.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## NOTES
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
