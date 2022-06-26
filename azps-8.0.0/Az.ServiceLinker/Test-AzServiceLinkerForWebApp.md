---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.servicelinker/test-azservicelinkerforwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Test-AzServiceLinkerForWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Test-AzServiceLinkerForWebApp.md
ms.openlocfilehash: 4c37aaad13fb075525ccd480deac5d2e9a24e907
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146594958"
---
# Test-AzServiceLinkerForWebApp

## SYNOPSIS
Memvalidasi tautan di webapp.

## SYNTAX

### Validasi (Default)
```
Test-AzServiceLinkerForWebApp -Name <String> -ResourceGroupName <String> -WebApp <String>
 [-ResourceUri <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-SubscriptionId <String>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### ValidateViaIdentity
```
Test-AzServiceLinkerForWebApp -InputObject <IServiceLinkerIdentity> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-SubscriptionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memvalidasi tautan di webapp.

## EXAMPLES

### Contoh 1: Test Linker
```powershell
Test-AzServiceLinkerForWebApp -WebApp servicelinker-webapp -ResourceGroupName servicelinker-test-group -Name postgresql_connection | fl
```

```output
AuthType              : 
IsConnectionAvailable : True
LinkerName            : postgresql_connection
ReportEndTimeUtc      : 5/6/2022 8:32:26 AM
ReportStartTimeUtc    : 5/6/2022 8:32:24 AM
ResourceId            : /subscriptions/d82d7763-8e12-4f39-a7b6-496a983ec2f4/resourceGroups/servicelinke 
                        r-test-group/providers/Microsoft.Web/sites/servicelinker-webapp/providers/Mi 
                        crosoft.ServiceLinker/linkers/postgresql_connection
SourceId              :
Status                : Succeeded
TargetId              : /subscriptions/937bc588-a144-4083-8612-5f9ffbbddb14/resourceGroups/servicelinke 
                        r-test-group/providers/Microsoft.Storage/storageAccounts/servicelinkersto 
                        rage/tableServices/default
ValidationDetail      : {The target existence is validated, The target service firewall is validated,   
                        The configured values is validated}
```

Uji Linker

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.IServiceLinkerIdentity
Parameter Sets: ValidateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya Linker.

```yaml
Type: System.String
Parameter Sets: Validate
Aliases: LinkerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -ResourceGroupName
Grup sumber daya sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: Validate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceUri
Pengidentifikasi Azure Resource manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: Validate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan ID langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Nama webapp sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: Validate
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.IServiceLinkerIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.IValidateResult

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IServiceLinkerIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LinkerName <String>]`: Nama sumber daya Linker.
  - `[ResourceUri <String>]`: Pengidentifikasi Azure Resource Manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

## RELATED LINKS

