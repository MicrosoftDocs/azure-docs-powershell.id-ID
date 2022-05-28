---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 8C1D738C-825D-4718-AD2A-9CFEAA7DBD3B
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azroleassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleAssignment.md
ms.openlocfilehash: d54c301183f45b16d3c4fd16350fd6172976a6b5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145639628"
---
# Remove-AzRoleAssignment

## SYNOPSIS
Menghapus penetapan peran ke prinsipal yang ditentukan yang ditetapkan ke peran tertentu pada cakupan tertentu.

Cmdlet dapat memanggil di bawah Microsoft Graph API sesuai dengan parameter input:

- GET /users/{id}
- GET /servicePrincipals/{id}
- GET /groups/{id}
- GET /directoryObjects/{id}
- POST /directoryObjects/getByIds

Harap perhatikan bahwa cmdlet ini akan menandai `ObjectType` sebagai `Unknown` dalam output jika objek penetapan peran tidak ditemukan atau akun saat ini tidak memiliki hak istimewa yang cukup untuk mendapatkan jenis objek.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-azroleassignment) untuk informasi terbaru.

## SYNTAX

### EmptyParameterSet (Default)
```
Remove-AzRoleAssignment -ObjectId <String> [-Scope <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceWithObjectIdParameterSet
```
Remove-AzRoleAssignment -ObjectId <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceGroupWithObjectIdParameterSet
```
Remove-AzRoleAssignment -ObjectId <String> -ResourceGroupName <String> -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ScopeWithObjectIdParameterSet
```
Remove-AzRoleAssignment -ObjectId <String> [-Scope <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleIdWithScopeAndObjectIdParameterSet
```
Remove-AzRoleAssignment -ObjectId <String> [-Scope <String>] -RoleDefinitionId <Guid> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceWithSignInNameParameterSet
```
Remove-AzRoleAssignment -SignInName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceGroupWithSignInNameParameterSet
```
Remove-AzRoleAssignment -SignInName <String> -ResourceGroupName <String> -RoleDefinitionName <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ScopeWithSignInNameParameterSet
```
Remove-AzRoleAssignment -SignInName <String> [-Scope <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceWithSPNParameterSet
```
Remove-AzRoleAssignment -ServicePrincipalName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] -RoleDefinitionName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceGroupWithSPNParameterSet
```
Remove-AzRoleAssignment -ServicePrincipalName <String> -ResourceGroupName <String> -RoleDefinitionName <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ScopeWithSPNParameterSet
```
Remove-AzRoleAssignment -ServicePrincipalName <String> [-Scope <String>] -RoleDefinitionName <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleAssignmentParameterSet
```
Remove-AzRoleAssignment [-PassThru] [-InputObject] <PSRoleAssignment>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Gunakan commandlet Remove-AzRoleAssignment untuk mencabut akses ke perwakilan mana pun pada cakupan tertentu dan peran yang diberikan.
Objek penugasan yaitu pokok HARUS ditentukan.
Prinsipal dapat menjadi pengguna (gunakan parameter SignInName atau ObjectId untuk mengidentifikasi pengguna), grup keamanan (gunakan parameter ObjectId untuk mengidentifikasi grup) atau perwakilan layanan (gunakan parameter ServicePrincipalName atau ObjectId untuk mengidentifikasi ServicePrincipal.
Peran yang ditetapkan prinsipal ke HARUS ditentukan menggunakan parameter RoleDefinitionName.
Cakupan penugasan DAPAT ditentukan dan jika tidak ditentukan, default ke cakupan langganan yaitu akan mencoba menghapus tugas ke prinsipal dan peran yang ditentukan pada cakupan langganan.
Cakupan penugasan dapat ditentukan menggunakan salah satu parameter berikut.
a.
Cakupan - Ini adalah cakupan yang sepenuhnya memenuhi syarat yang dimulai dengan /subscriptions/\<subscriptionId\> b.
ResourceGroupName - Nama grup sumber daya apa pun di bawah langganan.
c.
ResourceName, ResourceType, ResourceGroupName, dan (opsional) ParentResource - Mengidentifikasi sumber daya tertentu di bawah langganan.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzRoleAssignment -ResourceGroupName rg1 -SignInName john.doe@contoso.com -RoleDefinitionName Reader
```

Menghapus penetapan peran untuk john.doe@contoso.com siapa yang ditetapkan ke peran Pembaca di lingkup grup sumber daya rg1.

### Contoh 2
```powershell
Remove-AzRoleAssignment -ObjectId 36f81fc3-b00f-48cd-8218-3879f51ff39f -RoleDefinitionName Reader
```

Menghapus penetapan peran ke prinsipal grup yang diidentifikasi oleh ObjectId dan ditetapkan ke peran Pembaca.
Default menggunakan langganan saat ini sebagai cakupan untuk menemukan tugas yang akan dihapus.

### Contoh: 3
```powershell
$roleassignment = Get-AzRoleAssignment |Select-Object -First 1 -Wait
Remove-AzRoleAssignment -InputObject $roleassignment
```

Menghapus objek penetapan peran pertama yang diambil dari commandlet Get-AzRoleAssignment.

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

### -InputObject
Objek Penetapan Peran.

```yaml
Type: Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleAssignment
Parameter Sets: RoleAssignmentParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Azure AD ObjectId pengguna, grup, atau perwakilan layanan.

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet, ResourceWithObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ScopeWithObjectIdParameterSet, RoleIdWithScopeAndObjectIdParameterSet
Aliases: Id, PrincipalId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentResource
Sumber daya induk dalam hierarki (sumber daya yang ditentukan menggunakan parameter ResourceName), jika ada.
Harus digunakan bersama dengan parameter ResourceGroupName, ResourceType, dan ResourceName untuk membangun cakupan hierarkis dalam bentuk URI relatif yang mengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Jika ditentukan, menampilkan penetapan peran yang dihapus

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
Nama grup sumber daya tempat peran ditetapkan.
Mencoba menghapus penugasan pada cakupan grup sumber daya yang ditentukan.
Saat digunakan bersama dengan parameter ResourceName, ResourceType, dan (opsional)ParentResource, perintah membuat cakupan hierarkis dalam bentuk URI relatif yang mengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceGroupWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceGroupWithSPNParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceName
Nama sumber daya.
Misalnya storageaccountprod.
Harus digunakan bersama dengan parameter ResourceGroupName, ResourceType, dan (opsional) ParentResource, untuk membangun cakupan hierarkis dalam bentuk URI relatif yang mengidentifikasi sumber daya dan menghapus penugasan pada cakupan tersebut.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Jenis sumber daya.
Misalnya, Microsoft.Network/virtualNetworks.
Harus digunakan bersama dengan parameter ResourceGroupName, ResourceName, dan (opsional)ParentResource untuk membangun cakupan hierarkis dalam bentuk URI relatif yang mengidentifikasi sumber daya dan menghapus penugasan di cakupan sumber daya tersebut.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleDefinitionId
Id peran RBAC yang tugasnya perlu dihapus.

```yaml
Type: System.Guid
Parameter Sets: RoleIdWithScopeAndObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleDefinitionName
Nama peran RBAC yang tugasnya perlu dihapus yaitu Pembaca, Kontributor, Virtual Network Administrator, dll.

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet, ResourceWithObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ScopeWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceGroupWithSignInNameParameterSet, ScopeWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceGroupWithSPNParameterSet, ScopeWithSPNParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cakupan
Cakupan penetapan peran yang akan dihapus.
Dalam format URI relatif.
Misalnya "/subscriptions/9004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/TestRG".
Jika tidak ditentukan, akan mencoba menghapus peran di tingkat langganan.
Jika ditentukan, seharusnya dimulai dengan "/subscriptions/{id}".

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet, ScopeWithObjectIdParameterSet, RoleIdWithScopeAndObjectIdParameterSet, ScopeWithSignInNameParameterSet, ScopeWithSPNParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
ServicePrincipalName dari aplikasi Azure AD

```yaml
Type: System.String
Parameter Sets: ResourceWithSPNParameterSet, ResourceGroupWithSPNParameterSet, ScopeWithSPNParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SignInName
Alamat email atau nama utama pengguna pengguna.

```yaml
Type: System.String
Parameter Sets: ResourceWithSignInNameParameterSet, ResourceGroupWithSignInNameParameterSet, ScopeWithSignInNameParameterSet
Aliases: Email, UserPrincipalName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### System.Guid

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleAssignment

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleAssignment

## NOTES
Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, sumber daya, grup, templat, penyebaran

## RELATED LINKS

[New-AzRoleAssignment](./New-AzRoleAssignment.md)

[Get-AzRoleAssignment](./Get-AzRoleAssignment.md)

[Get-AzRoleDefinition](./Get-AzRoleDefinition.md)

