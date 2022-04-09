---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Support.dll-Help.xml
Module Name: Az.Support
online version: https://docs.microsoft.com/powershell/module/az.support/get-azsupportservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Get-AzSupportService.md
ms.openlocfilehash: ec5ee2330db6bcaf0089aec510661826b207bcc1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140553672"
---
# Get-AzSupportService

## SYNOPSIS
Dapatkan layanan yang tersedia untuk dukungan. 

## SYNTAX

### ListParameterSet (Default)
```
Get-AzSupportService [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByNameParameterSet
```
Get-AzSupportService -Id <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar layanan Azure saat ini yang menyediakan dukungan. Setiap layanan mungkin berisi satu atau beberapa informasi tipe sumber daya manajer sumber daya Azure (ARM). Tipe sumber daya (contoh: 'microsoft.compute/virtualmachines') dapat berguna untuk memetakan produk yang tepat dan sumber daya ARM saat membuat tiket dukungan teknis. Setiap layanan Azure memiliki kumpulan kategorinya sendiri yang disebut klasifikasi masalah. Dapatkan daftar klasifikasi masalah saat ini untuk layanan menggunakan Get-AzSupportProblemClassification. Anda dapat menggunakan GUID klasifikasi masalah dan layanan untuk membuat tiket dukungan baru menggunakan New-AzSupportTicket.

Selalu gunakan layanan dan masalah klasifikasi GUID yang diperoleh secara terprogram. Praktik ini memastikan Anda memiliki kumpulan layanan terbaru dan klasifikasi masalah GUID untuk pembuatan tiket dukungan.

## EXAMPLES

### Contoh 1: Dapatkan semua layanan yang tersedia untuk dukungan
```powershell
PS C:\> Get-AzSupportService

Name                                 DisplayName
----                                 -----------
484e2236-bc6d-b1bb-76d2-7d09278cf9ea Activity Logs
809e8afe-489e-08b0-95f2-08f835a383e8 Advanced Threat Protection - Azure
6859f4e8-4a1d-13e4-f276-6d055007e83d Advanced Threat Protection - Microsoft Defender
94332e54-73b0-b8e3-306e-db3ad13d950b Advanced Threat Protection - O365
26d8424b-0a41-4443-cbc6-0309ea8708d0 Advisor
8f1ddc5f-0c5e-50c7-9810-e01a8d1da925 AKS Engine on Azure Stack
c1840ac9-309f-f235-c0ae-4782f283b698 Alerts and Action Groups
e8fe7c6f-d883-c57f-6576-cf801ca30653 Analysis Services
07651e65-958a-0877-36f3-61bbba85d783 API for FHIR
b4d0e877-0166-0474-9a76-b5be30ba40e4 API Management Service
e14f616b-42c5-4515-3d7c-67935eece51a App Configuration
445c0905-55e2-4f42-d853-ec9e17a5180e App Service Certificates
b7d2f8b7-7d20-cf2f-ddd5-5543ada54bd2 App Service Domains
101732bb-31af-ee61-7c16-d4ad77c86a50 Application Gateway
```

### Contoh 2: Dapatkan detail tentang satu layanan berdasarkan id yang tersedia untuk dukungan
```powershell
PS C:\> Get-AzSupportService -Id "484e2236-bc6d-b1bb-76d2-7d09278cf9ea"

Name                                 DisplayName
----                                 -----------
484e2236-bc6d-b1bb-76d2-7d09278cf9ea Activity Logs
```

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

### -Id
Id layanan.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Support.Models.PSSupportService

## CATATAN

## RELATED LINKS
