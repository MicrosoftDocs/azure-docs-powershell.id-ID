---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/update-azrolemanagementpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzRoleManagementPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzRoleManagementPolicy.md
ms.openlocfilehash: 371c0327aec5aad621fb537701cdf5ef71f2afc3
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146600808"
---
# Update-AzRoleManagementPolicy

## SYNOPSIS
Memutakhirkan kebijakan manajemen peran

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/update-azrolemanagementpolicy) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzRoleManagementPolicy -Name <String> -Scope <String> [-Description <String>] [-DisplayName <String>]
 [-IsOrganizationDefault] [-Rule <IRoleManagementPolicyRule[]>] [-DefaultProfile <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzRoleManagementPolicy -InputObject <IAuthorizationIdentity> [-Description <String>]
 [-DisplayName <String>] [-IsOrganizationDefault] [-Rule <IRoleManagementPolicyRule[]>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memutakhirkan kebijakan manajemen peran

## EXAMPLES

### Contoh 1: Memperbarui aturan kedaluwarsa kebijakan
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> $expirationRule = [RoleManagementPolicyExpirationRule]@{
            isExpirationRequired = "false";
            maximumDuration = "P180D";
            id = "Expiration_Admin_Eligibility";
            ruleType = [RoleManagementPolicyRuleType]("RoleManagementPolicyExpirationRule");
            targetCaller = "Admin";
            targetOperation = @('All');
            targetLevel = "Eligibility";
            targetObject = $null;
            targetInheritableSetting = $null;
            targetEnforcedSetting = $null;
        }
PS C:\> $rules = [IRoleManagementPolicyRule[]]@($expirationRule)
PS C:\> Update-AzRoleManagementPolicy -Scope $scope -Name "33b520ea-3544-4abc-8565-3588deb8e68e" -Rule $rules

Name                                 Type                                           Scope
----                                 ----                                           -----
33b520ea-3544-4abc-8565-3588deb8e68e Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

Setiap individu `Rule` pada kebijakan dapat diperbarui secara independen.

### Contoh 2: Memperbarui aturan kedaluwarsa dan aturan pemberitahuan kebijakan
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> $expirationRule = [RoleManagementPolicyExpirationRule]@{
            isExpirationRequired = "false";
            maximumDuration = "P180D";
            id = "Expiration_Admin_Eligibility";
            ruleType = [RoleManagementPolicyRuleType]("RoleManagementPolicyExpirationRule");
            targetCaller = "Admin";
            targetOperation = @('All');
            targetLevel = "Eligibility";
            targetObject = $null;
            targetInheritableSetting = $null;
            targetEnforcedSetting = $null;
        }
PS C:\> $notificationRule = [RoleManagementPolicyNotificationRule]@{
            notificationType = "Email";
            recipientType = "Approver";
            isDefaultRecipientsEnabled = "false";
            notificationLevel = "Critical";
            notificationRecipient = $null;                
            id = "Notification_Approver_Admin_Eligibility";
            ruleType = [RoleManagementPolicyRuleType]("RoleManagementPolicyNotificationRule");
            targetCaller = "Admin";
            targetOperation = @('All');
            targetLevel = "Eligibility";
            targetObject = $null;
            targetInheritableSetting = $null;
            targetEnforcedSetting = $null;
        }
PS C:\> $rules = [IRoleManagementPolicyRule[]]@($expirationRule, $notificationRule)
PS C:\> Update-AzRoleManagementPolicy -Scope $scope -Name "33b520ea-3544-4abc-8565-3588deb8e68e" -Rule $rules

Name                                 Type                                           Scope
----                                 ----                                           -----
33b520ea-3544-4abc-8565-3588deb8e68e Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

Beberapa `Rule` dapat diperbarui bersama-sama.

## PARAMETERS

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

### -Deskripsi
Deskripsi kebijakan manajemen peran.

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

### -DisplayName
Nama tampilan kebijakan manajemen peran.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsOrganizationDefault
Kebijakan manajemen peran adalah kebijakan default.

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

### -Name
Nama (guid) dari kebijakan manajemen peran ke upsert.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: RoleManagementPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aturan
Aturan yang diterapkan pada kebijakan.
Untuk membuat, lihat bagian CATATAN untuk properti ATURAN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleManagementPolicyRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan kebijakan manajemen peran untuk upsert.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleManagementPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IAuthorizationIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[RoleAssignmentScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleName <String>]`: Nama (guid) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleRequestName <String>]`: Nama penetapan peran yang akan dibuat. Ini bisa menjadi GUID yang valid.
  - `[RoleEligibilityScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleName <String>]`: Nama (guid) dari jadwal kelayakan peran yang akan didapatkan.
  - `[RoleEligibilityScheduleRequestName <String>]`: Nama kelayakan peran untuk dibuat. Ini bisa menjadi GUID yang valid.
  - `[RoleManagementPolicyAssignmentName <String>]`: Nama format {guid_guid} penetapan kebijakan manajemen peran yang akan didapatkan.
  - `[RoleManagementPolicyName <String>]`: Nama (guid) dari kebijakan manajemen peran yang akan didapatkan.
  - `[Scope <String>]`: Ruang lingkup kebijakan manajemen peran.

RULE <IRoleManagementPolicyRule[]>: Aturan yang diterapkan pada kebijakan.
  - `RuleType <RoleManagementPolicyRuleType>`: Jenis aturan
  - `[Id <String>]`: Id aturan.
  - `[TargetCaller <String>]`: Penelepon pengaturan.
  - `[TargetEnforcedSetting <String[]>]`: Daftar pengaturan yang diberlakukan.
  - `[TargetInheritableSetting <String[]>]`: Daftar pengaturan yang dapat diwariskan.
  - `[TargetLevel <String>]`: Tingkat penugasan yang diterapkannya.
  - `[TargetObject <String[]>]`: Daftar objek target.
  - `[TargetOperation <String[]>]`: Jenis operasi.

## RELATED LINKS
