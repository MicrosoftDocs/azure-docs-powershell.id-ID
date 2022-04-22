---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azroleassignmentschedulerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleAssignmentScheduleRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleAssignmentScheduleRequest.md
ms.openlocfilehash: 538e5f2ab8c8bdfa6b976687d20437641ee6dda6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142867420"
---
# New-AzRoleAssignmentScheduleRequest

## SYNOPSIS
Membuat permintaan jadwal penetapan peran.

## SYNTAX

```
New-AzRoleAssignmentScheduleRequest -Name <String> -Scope <String> [-Condition <String>]
 [-ConditionVersion <String>] [-ExpirationDuration <String>] [-ExpirationEndDateTime <DateTime>]
 [-ExpirationType <Type>] [-Justification <String>] [-LinkedRoleEligibilityScheduleId <String>]
 [-PrincipalId <String>] [-RequestType <RequestType>] [-RoleDefinitionId <String>]
 [-ScheduleInfoStartDateTime <DateTime>] [-TargetRoleAssignmentScheduleId <String>]
 [-TargetRoleAssignmentScheduleInstanceId <String>] [-TicketNumber <String>] [-TicketSystem <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat permintaan jadwal penetapan peran.

## EXAMPLES

### Contoh 1: Membuat permintaan jadwal penetapan peran baru sebagai Admin
```powershell
PS C:\> $guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
PS C:\> $startTime = Get-Date -Format o 
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId 5a4bdd72-ab3e-4d8e-ab0f-8dd8917481a2 -RequestType AdminAssign -RoleDefinitionId subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime

Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authori…
```

Membuat permintaan untuk menyediakan penetapan `roleDefinition` aktif untuk `scope``principal`

### Contoh 2: Menghapus permintaan jadwal penetapan peran sebagai Admin
```powershell
PS C:\> $guid = "13f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
PS C:\> $startTime = Get-Date -Format o 
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId 5a4bdd72-ab3e-4d8e-ab0f-8dd8917481a2 -RequestType AdminRemove -RoleDefinitionId subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime

Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
13f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authori…
```

Membuat permintaan untuk menghapus penetapan `roleDefinition` aktif untuk `scope` tugas yang ditentukan `principal`

### Contoh 3: Mengaktifkan permintaan jadwal penetapan peran baru sebagai pengguna
```powershell
PS C:\> $guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
PS C:\> $startTime = Get-Date -Format o 
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId 5a4bdd72-ab3e-4d8e-ab0f-8dd8917481a2 -RequestType SelfActivate -RoleDefinitionId subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime

Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authori…
```

Membuat permintaan untuk mengaktifkan penetapan `roleDefinition` `scope` yang memenuhi syarat untuk `principal`

### Contoh 4: Menonaktifkan permintaan jadwal penetapan peran sebagai pengguna
```powershell
PS C:\> $guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
PS C:\> $startTime = Get-Date -Format o 
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId 5a4bdd72-ab3e-4d8e-ab0f-8dd8917481a2 -RequestType SelfDeactivate -RoleDefinitionId subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime

Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authori…
```

Membuat permintaan untuk menonaktifkan penetapan `roleDefinition` yang memenuhi syarat untuk `scope` tugas yang ditentukan `principal`

## PARAMETERS

### -Kondisi
Kondisi pada penetapan peran.
Ini membatasi sumber daya tempat sumber daya dapat ditetapkan.
misalnya: @Resource[Microsoft.Storage /storageAccounts/blobServices/containers:ContainerName] StringEqualsIgnoreCase 'foo_storage_container'

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

### -ConditionVersion
Versi kondisi.
Nilai yang saat ini diterima adalah '2.0'

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

### -ExpirationDuration
Durasi jadwal penetapan peran di Rentang Waktu.

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

### -ExpirationEndDateTime
Tanggal Berakhir dari jadwal penetapan peran.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationType
Tipe jadwal penetapan peran kedaluwarsa

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Support.Type
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Justification
Justifikasi untuk penetapan peran

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

### -LinkedRoleEligibilityScheduleId
Id jadwal kelayakan peran tertaut - untuk mengaktifkan kelayakan.

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

### -Nama
Nama penetapan peran yang akan dibuat.
Ini bisa berupa GUID apa pun yang valid.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RoleAssignmentScheduleRequestName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalId
Id utama.

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

### -RequestType
Tipe permintaan jadwal penetapan peran.
Misalnya: SelfActivate, AdminAssign dll

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Support.RequestType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitionId
ID definisi peran.

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

### -ScheduleInfoStartDateTime
Mulai TanggalWaktu jadwal penetapan peran.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup permintaan jadwal penetapan peran untuk dibuat.
Lingkup dapat berupa instans sumber daya REST apa pun.
Misalnya, gunakan '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/' untuk langganan, '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}' untuk grup sumber daya, dan '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-provider}/{resource-type}/{resource-name}' untuk sumber daya.

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

### -TargetRoleAssignmentScheduleId
Id jadwal penetapan peran yang dihasilkan atau id jadwal penetapan peran sedang diperbarui

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

### -TargetRoleAssignmentScheduleInstanceId
Id instans jadwal penetapan peran sedang diperbarui

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

### -TicketNumber
Nomor tiket untuk penetapan peran

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

### -TicketSystem
Nama sistem tiket untuk penetapan peran

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleAssignmentScheduleRequest

## NOTES

ALIAS

## RELATED LINKS
