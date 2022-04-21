---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Set-AzSecurityAssessment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Set-AzSecurityAssessment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Set-AzSecurityAssessment.md
ms.openlocfilehash: 0c984cce16b844f2ed693804bc16fd59c174d52a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142694818"
---
# Set-AzSecurityAssessment

## SYNOPSIS
Membuat atau memperbarui hasil penilaian keamanan pada sumber daya

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.security/set-azsecurityassessment) untuk informasi terbaru.

## SYNTAX

### SubscriptionLevelResource (Default)
```
Set-AzSecurityAssessment -Name <String> [-StatusCode <String>] [-StatusCause <String>]
 [-StatusDescription <String>]
 [-AdditionalData <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdLevelResource
```
Set-AzSecurityAssessment -Name <String> -AssessedResourceId <String> -StatusCode <String>
 [-StatusCause <String>] [-StatusDescription <String>]
 [-AdditionalData <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui hasil penilaian keamanan pada sumber daya, dapat digunakan untuk mengubah status hasil yang sudah ada atau menambahkan data tambahan.
hanya dapat digunakan untuk jenis penilaian "CustomerManaged" dan hanya setelah metadata penilaian yang cocok dibuat.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSecurityAssessment -Name 4FB6C0A0-1137-42C7-A1C7-4BD37C91DE8D -StatusCode "Unhealthy"
```

Menandai hasil langganan sebagai "Tidak Sehat" untuk penilaian tipe "4FB6C0A0-1137-42C7-A1C7-4BD37C91DE8D" - detail selengkapnya tentang tipe penilaian akan ditemukan di bawah penilaianTipemetadata

## PARAMETERS

### -AdditionalData
Data yang dilampirkan ke hasil penilaian untuk penyelidikan atau kejelasan status yang lebih baik.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssessedResourceId
ID sumber daya lengkap sumber daya yang dihitung penilaiannya.

```yaml
Type: String
Parameter Sets: ResourceIdLevelResource
Aliases:

Required: True
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
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusCause
Kode progremmatik untuk penyebab hasil penilaian.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusCode
Kode progremmatik untuk hasil penilaian.
dapat berupa "Sehat", "Tidak Sehat" atau "Tidak Dapat Diterapkan"

```yaml
Type: String
Parameter Sets: SubscriptionLevelResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ResourceIdLevelResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusDescription
Deskripsi yang dapat dibaca manusia tentang penyebab hasil penilaian.

```yaml
Type: String
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Assessments.PSSecurityAssessment

## NOTES

## RELATED LINKS
