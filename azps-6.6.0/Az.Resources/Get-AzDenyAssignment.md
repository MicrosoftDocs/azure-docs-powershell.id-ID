---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdenyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDenyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDenyAssignment.md
ms.openlocfilehash: 2ba3a917686ad7666c6b8729201cbcc50c4f5300
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143251991"
---
# Get-AzDenyAssignment

## SYNOPSIS
Mencantumkan Azure RBAC menolak penetapan pada lingkup yang ditentukan.
Secara default mencantumkan semua penolakan tugas dalam langganan Azure yang dipilih.
Gunakan parameter masing-masing untuk mencantumkan penolakan tugas kepada pengguna tertentu, atau untuk mencantumkan penolakan tugas pada grup sumber daya atau sumber daya tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azdenyassignment) untuk informasi terbaru.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzDenyAssignment [-Scope <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectIdParameterSet
```
Get-AzDenyAssignment -ObjectId <Guid> [-ExpandPrincipalGroups] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupWithObjectIdParameterSet
```
Get-AzDenyAssignment -ObjectId <Guid> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceWithObjectIdParameterSet
```
Get-AzDenyAssignment -ObjectId <Guid> -ResourceGroupName <String> -ResourceName <String> -ResourceType <String>
 [-ParentResource <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LingkupWithObjectIdParameterSet
```
Get-AzDenyAssignment -ObjectId <Guid> -Scope <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupWithSignInNameParameterSet
```
Get-AzDenyAssignment -SignInName <String> -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceWithSignInNameParameterSet
```
Get-AzDenyAssignment -SignInName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### LingkupWithSignInNameParameterSet
```
Get-AzDenyAssignment -SignInName <String> -Scope <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SignInNameParameterSet
```
Get-AzDenyAssignment -SignInName <String> [-ExpandPrincipalGroups] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupWithSPNParameterSet
```
Get-AzDenyAssignment -ServicePrincipalName <String> -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceWithSPNParameterSet
```
Get-AzDenyAssignment -ServicePrincipalName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### LingkupWithSPNParameterSet
```
Get-AzDenyAssignment -ServicePrincipalName <String> -Scope <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SPNParameterSet
```
Get-AzDenyAssignment -ServicePrincipalName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceGroupParameterSet
```
Get-AzDenyAssignment -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceParameterSet
```
Get-AzDenyAssignment -ResourceGroupName <String> -ResourceName <String> -ResourceType <String>
 [-ParentResource <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LingkupParameterSet
```
Get-AzDenyAssignment -Scope <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DenyAssignmentIdParameterSet
```
Get-AzDenyAssignment [-Scope <String>] -Id <Guid> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### DenyAssignmentNameParameterSet
```
Get-AzDenyAssignment [-Scope <String>] -DenyAssignmentName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Gunakan perintah Get-AzDenyAssignment untuk mencantumkan semua penolakan tugas yang efektif pada lingkup.
Tanpa parameter apa pun, perintah ini mengembalikan semua penolakan tugas yang dibuat di bawah langganan.
Daftar ini dapat difilter menggunakan parameter pemfilteran untuk lingkup dan nama penetapan pokok.
Untuk menentukan pengguna, gunakan SignInName atau parameter ObjectId Azure AD.
Untuk menentukan grup keamanan, gunakan parameter ObjectId Azure AD.
Dan untuk menentukan aplikasi Azure AD, gunakan parameter ServicePrincipalName atau ObjectId.
Lingkup di mana akses ditolak mungkin ditentukan.
Ini secara default ke langganan yang dipilih.
Lingkup penolakan penetapan dapat ditentukan menggunakan salah satu kombinasi parameter berikut ini a.
Lingkup - Ini adalah lingkup yang sepenuhnya memenuhi syarat yang dimulai dengan /subscriptions/\<subscriptionId\>.
Ini akan memfilter penolakan tugas yang efektif pada lingkup tersebut, yaitu semua menolak tugas pada lingkup tersebut ke atas.
B.
ResourceGroupName - Nama grup sumber daya apa pun di bawah langganan.
Tindakan ini akan memfilter penetapan yang efektif pada grup sumber daya yang ditentukan, misalnya semua menolak tugas pada lingkup tersebut ke atas.
C.
ResourceName, ResourceType, ResourceGroupName dan (opsional) ParentResource - Mengidentifikasi sumber daya tertentu dalam langganan dan akan memfilter penolakan tugas yang efektif pada lingkup sumber daya tersebut.
Untuk menentukan akses apa yang ditolak untuk pengguna tertentu dalam langganan, gunakan sakelar ExpandPrincipalGroups.
Ini akan mencantumkan semua penolakan tugas yang ditetapkan kepada pengguna, dan ke grup tempat pengguna menjadi anggotanya.

## EXAMPLES

### Contoh 1

Mencantumkan semua penolakan tugas dalam langganan

```
PS C:\> Get-AzDenyAssignment
Id                      : 22704996-fbd0-4ab1-8625-722d897825d2
DenyAssignmentName      : Test deny assignment 1
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  All Principals
                          ObjectType:   SystemDefined
                          ObjectId:     00000000-0000-0000-0000-000000000000
                          }
ExcludePrincipals       : {
                          DisplayName:  testuser
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          }
IsSystemProtected       : True

Id                      : 43af7d0c-0bf8-407f-96c0-96a29d076431
DenyAssignmentName      : Test deny assignment 2
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourcegroups/testRG
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  testuser
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          ,
                          DisplayName:  PowershellTestingApp
                          ObjectType:   ServicePrincipal
                          ObjectId:     f2dc21ac-702a-4bde-a4ce-146edf751d81
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True
```

### Contoh 2

Mendapatkan semua penolakan tugas yang dibuat untuk pengguna john.doe@contoso.com di testRG lingkup ke atas.

```
PS C:\> Get-AzDenyAssignment -ResourceGroupName testRG -SignInName john.doe@contoso.com

Id                      : 22704996-fbd0-4ab1-8625-722d897825d2
DenyAssignmentName      : Test deny assignment 1
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  john.doe
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True

Id                      : 43af7d0c-0bf8-407f-96c0-96a29d076431
DenyAssignmentName      : Test deny assignment
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourcegroups/testRG
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  john.doe
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          ,
                          DisplayName:  PowershellTestingApp
                          ObjectType:   ServicePrincipal
                          ObjectId:     f2dc21ac-702a-4bde-a4ce-146edf751d81
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True
```

### Contoh 3

Mendapatkan semua penugasan pokok layanan yang ditentukan

```
PS C:\> Get-AzDenyAssignment -ServicePrincipalName 'http://testapp1.com'

Id                      : 43af7d0c-0bf8-407f-96c0-96a29d076431
DenyAssignmentName      : Test deny assignment 1
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourcegroups/testRG
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  TestApp
                          ObjectType:   ServicePrincipal
                          ObjectId:     f2dc21ac-702a-4bde-a4ce-146edf751d81
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True

Id                      : 94e3d9da-3700-4113-aab4-15f6c173d794
DenyAssignmentName      : Test deny assignment 2
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/testRG/providers/Microsoft.Web/sites/site1
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  testuser
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          ,
                          DisplayName:  TestApp
                          ObjectType:   ServicePrincipal
                          ObjectId:     f2dc21ac-702a-4bde-a4ce-146edf751d81
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True
```

### Contoh 4

Mendapatkan penolakan tugas di lingkup situs web 'site1'.

```
PS C:\> Get-AzDenyAssignment -Scope '/subscriptions/96231a05-34ce-4eb4-aa6a-70759cbb5e83/resourcegroups/testRG/providers/Microsoft.Web/sites/site1'

Id                      : 43af7d0c-0bf8-407f-96c0-96a29d076431
DenyAssignmentName      : Test deny assignment 1
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourcegroups/testRG
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  testuser
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True

Id                      : 94e3d9da-3700-4113-aab4-15f6c173d794
DenyAssignmentName      : Test deny assignment 2
Description             : Test deny assignment for PS cmdlets
Actions                 : {foo/*}
NotActions              : {foo/*/read}
DataActions             : {foo/*}
NotDataActions          : {}
Scope                   : /subscriptions/4004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/testRG/providers/Microsoft.Web/sites/site1
DoNotApplyToChildScopes : False
Principals              : {
                          DisplayName:  testuser
                          ObjectType:   User
                          ObjectId:     f8d526a0-54eb-4941-ae69-ebf4a334d0f0
                          ,
                          DisplayName:  TestApp
                          ObjectType:   ServicePrincipal
                          ObjectId:     f2dc21ac-702a-4bde-a4ce-146edf751d81
                          }
ExcludePrincipals       : {}
IsSystemProtected       : True
```

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

### -DenyAssignmentName
Nama penolakan tugas.

```yaml
Type: System.String
Parameter Sets: DenyAssignmentNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExpandPrincipalGroups
Jika ditentukan, mengembalikan penolakan tugas yang ditetapkan secara langsung kepada pengguna dan ke grup di mana pengguna merupakan anggota (secara transitif).
Didukung hanya untuk prinsipal pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectIdParameterSet, SignInNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Tolak id penugasan.

```yaml
Type: System.Guid
Parameter Sets: DenyAssignmentIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
ObjectId Azure AD Dari Prinsipal Pengguna, Grup, atau Layanan.
Memfilter semua penolakan tugas yang dibuat untuk pokok yang ditentukan.

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: ObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ResourceWithObjectIdParameterSet, ScopeWithObjectIdParameterSet
Aliases: PrincipalId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentResource
Sumber daya induk dalam hierarki sumber daya yang ditentukan menggunakan parameter ResourceName.
Harus digunakan bersama dengan parameter ResourceGroupName, ResourceType, dan ResourceName.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Daftar menolak penetapan yang efektif pada grup sumber daya tertentu.
Ketika digunakan bersama dengan parameter ResourceName, ResourceType, dan ParentResource, daftar perintah menolak penetapan yang efektif pada sumber daya dalam grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceGroupWithObjectIdParameterSet, ResourceWithObjectIdParameterSet, ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ResourceGroupWithSPNParameterSet, ResourceWithSPNParameterSet, ResourceGroupParameterSet, ResourceParameterSet
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
Harus digunakan bersama dengan parameter ResourceGroupName, ResourceType, dan (opsional)ParentResource.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Tipe sumber daya.
Misalnya Microsoft.Network/virtualNetworks.
Harus digunakan bersamaan dengan parameter ResourceGroupName, ResourceName, dan (opsional)ParentResource.

```yaml
Type: System.String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lingkup
Lingkup penetapan peran.
Dalam format URI relatif.
Misalnya /subscriptions/9004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/TestRG.
Ini harus dimulai dengan "/subscriptions/{id}".
Perintah memfilter semua penolakan tugas yang efektif pada lingkup tersebut.

```yaml
Type: System.String
Parameter Sets: EmptyParameterSet, DenyAssignmentIdParameterSet, DenyAssignmentNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ScopeWithObjectIdParameterSet, ScopeWithSignInNameParameterSet, ScopeWithSPNParameterSet, ScopeParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
ServicePrincipalName dari prinsipal layanan.
Memfilter semua penolakan tugas yang dibuat pada aplikasi Azure AD yang ditentukan.

```yaml
Type: System.String
Parameter Sets: ResourceGroupWithSPNParameterSet, ResourceWithSPNParameterSet, ScopeWithSPNParameterSet, SPNParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SignInName
Alamat email atau nama utama pengguna pengguna.
Memfilter semua penolakan tugas yang dibuat untuk pengguna tertentu.

```yaml
Type: System.String
Parameter Sets: ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ScopeWithSignInNameParameterSet, SignInNameParameterSet
Aliases: Email, UserPrincipalName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSDenyAssignment

## NOTES
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, sumber daya, grup, Templat, penyebaran

## RELATED LINKS
