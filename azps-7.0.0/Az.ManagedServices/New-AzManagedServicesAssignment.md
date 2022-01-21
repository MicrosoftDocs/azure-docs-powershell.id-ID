---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/new-azmanagedservicesassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAssignment.md
ms.openlocfilehash: 01059c396285642e45239c9da15f9772d7803866
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136548161"
---
# New-AzManagedServicesAssignment

## SYNOPSIS
Membuat atau memperbarui penetapan pendaftaran.

## SYNTAX

```
New-AzManagedServicesAssignment -Name <String> [-Scope <String>] [-RegistrationDefinitionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui penetapan pendaftaran.

## EXAMPLES

### Contoh 1: Membuat penetapan pendaftaran Mercusuar Azure baru di lingkup langganan
```powershell
PS C:\> New-AzManagedServicesAssignment -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RegistrationDefinitionId  "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
```

Membuat penetapan pendaftaran Azure Lighthouse baru pada lingkup langganan dengan definisi pendaftaran.

### Contoh 2: Membuat penetapan pendaftaran Azure Lighthouse baru di lingkup grup sumber daya
```powershell
PS C:\> New-AzManagedServicesAssignment -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/testgroup" -RegistrationDefinitionId  "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
```

Membuat penetapan pendaftaran Azure Lighthouse baru pada lingkup grup sumber daya dengan definisi registrasi.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -Nama
GUID penetapan pendaftaran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RegistrationAssignmentId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -RegistrationDefinitionId
Jalur definisi registrasi yang sepenuhnya memenuhi syarat.

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

### -Lingkup
Lingkup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "subscriptions/" + (Get-AzContext).Subscription.Id
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationAssignment

## CATATAN

ALIAS

## RELATED LINKS

