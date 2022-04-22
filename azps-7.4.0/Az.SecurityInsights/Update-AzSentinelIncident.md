---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/update-azsentinelincident
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Update-AzSentinelIncident.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Update-AzSentinelIncident.md
ms.openlocfilehash: 14d46d9ef8bd2a0338c27616d041aded3217bd65
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142866520"
---
# Update-AzSentinelIncident

## SYNOPSIS
Memperbarui Insiden

## SYNTAX

### IncidentId (Default)
```
Update-AzSentinelIncident -ResourceGroupName <String> -WorkspaceName <String> -IncidentID <String>
 [-Classification <String>] [-ClassificationComment <String>] [-ClassificationReason <String>]
 [-Description <String>]
 [-Label <System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]>]
 [-Owner <PSSentinelIncidentOwner>] [-Severity <String>] [-Status <String>] [-Title <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Update-AzSentinelIncident -InputObject <PSSentinelIncident> [-Classification <String>]
 [-ClassificationComment <String>] [-ClassificationReason <String>] [-Description <String>]
 [-Label <System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]>]
 [-Owner <PSSentinelIncidentOwner>] [-Severity <String>] [-Status <String>] [-Title <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Update-AzSentinelIncident -ResourceId <String> [-Classification <String>] [-ClassificationComment <String>]
 [-ClassificationReason <String>] [-Description <String>]
 [-Label <System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]>]
 [-Owner <PSSentinelIncidentOwner>] [-Severity <String>] [-Status <String>] [-Title <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzSentinelIncident** memperbarui Insiden di ruang kerja yang ditentukan.
Anda dapat melewati objek **Insiden** sebagai parameter atau menggunakan operator pipeline, atau menentukan parameter yang diperlukan.
Anda dapat menggunakan variabel *Konfirmasi* parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

## EXAMPLES

### Contoh 1
```powershell
Update-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" -IncidentId "myIncidentId" -Severity High
```

Contoh ini mendapatkan Insiden menurut *IncidentId* dan mengatur properti *Tingkat Keparahan* ke *Tinggi*.  Semua properti lainnya tetap tidak berubah.

### Contoh 2
```powershell
$ownerObject = @{"AssignedTo" = "John Doe"; "Email" = "johndoe@contoso.com"; "ObjectId" = "f4e959b4-feda-4345-a1e7-16b4af2fc226";"UserPrincipalName" = "johndoe@contoso.com"}
Update-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"  -IncidentId a4b586c8-97d8-4cc5-9154-b723c62d26d8 -Owner $ownerObject
```

Contoh ini pertama-tama membuat "*objek pemilik*" yang berisi informasi pemilik, lalu cmdlet **Update-AzSentinelIncident** digunakan untuk melewati pemilikObject untuk memperbarui insiden. <br/><br/>

*Catatan: ObjectId pemilik dapat ditemukan di bawah tampilan detail pengguna di bawah Azure Active Directory. Jika ingin mengotomatisasi pengambilan ObjectId melalui scripting, Anda dapat memanfaatkan modul powerShell Azure Active Directory, seperti ini: Get-AzureADUser -ObjectId "johndoe@contoso.com".*

### Contoh 3
```powershell
Update-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"  -IncidentID "561c5184-f8da-4d8b-8544-c89e422bbf6f" -Classification FalsePositive -Status "Closed"
```

Contoh ini menutup insiden tertentu dengan **Klasifikasi** "False Positif" <br/>
*Catatan: menyediakan Klasifikasi saat penutupan adalah wajib*

### Contoh 4
```powershell
Update-AzSentinelIncident -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" 
-IncidentID "561c5184-f8da-4d8b-8544-c89e422bbf6f" -Classification FalsePositive  -ClassificationComment "my comment" -ClassificationReason InaccurateData -Status "Closed"
```

Contoh ini menutup insiden tertentu dan memberikan komentar klasifikasi dan alasan

## PARAMETERS

### -Klasifikasi
Insiden Classificaiton.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: BenignPositive, FalsePositive, TruePositive, Undetermined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassificationComment
Komentar Classificaiton Insiden.

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

### -KlasifikasiReason
Insiden Alasan Classificaiton.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: InaccurateData, IncorrectAlertLogic, SuspiciousActivity, SuspiciousButExpected

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

### -Deskripsi
Deskripsi.

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

### -IncidentID
Id Insiden.

```yaml
Type: System.String
Parameter Sets: IncidentId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
InputObject.

```yaml
Type: Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Label
Label Insiden.

```yaml
Type: System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Pemilik
Pemilik Insiden.

```yaml
Type: Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentOwner
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: IncidentId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Keparahan
Keparahan Insiden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: High, Informational, Low, Medium

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Status Insiden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Active, Closed, New

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Judul
Judul Insiden.

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

### -Nama Ruang Kerja
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: IncidentId
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident

### System.String

### System.Collections.Generic.IList'1[[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel, Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights, Version=0.1.0.0, Culture=netral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentOwner

## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident

## NOTES

## RELATED LINKS
