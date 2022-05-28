---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultroleassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleAssignment.md
ms.openlocfilehash: 6e8930764ac261c5ebb24e6427566af852cb2bd5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145541420"
---
# Get-AzKeyVaultRoleAssignment

## SYNOPSIS
Mendapatkan atau mencantumkan penetapan peran dari HSM terkelola. Gunakan parameter masing-masing untuk mencantumkan penetapan ke pengguna tertentu atau definisi peran.

## SYNTAX

### Daftar (Default)
```
Get-AzKeyVaultRoleAssignment [-HsmName] <String> [-Scope <String>] [-RoleDefinitionName <String>]
 [-RoleDefinitionId <String>] [-ObjectId <String>] [-SignInName <String>] [-ApplicationId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByName
```
Get-AzKeyVaultRoleAssignment [-HsmName] <String> [-Scope <String>] -RoleAssignmentName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
`Get-AzKeyVaultRoleAssignment` Gunakan perintah untuk mencantumkan semua penetapan peran yang efektif pada cakupan.
Tanpa parameter apa pun, perintah ini mengembalikan semua penetapan peran yang dibuat di bawah HSM terkelola.
Daftar ini dapat difilter menggunakan parameter pemfilteran untuk prinsipal, peran, dan cakupan.
Subjek penugasan harus ditentukan.
Untuk menentukan pengguna, gunakan parameter SignInName atau Azure AD ObjectId.
Untuk menentukan grup keamanan, gunakan parameter objectId Azure AD.
Dan untuk menentukan aplikasi Azure AD, gunakan parameter ApplicationId atau ObjectId.
Peran yang sedang ditetapkan harus ditentukan menggunakan parameter RoleDefinitionName atau RoleDefinitionId.
Cakupan di mana akses diberikan dapat ditentukan. Ini default ke "/".

Cmdlet dapat memanggil di bawah Microsoft Graph API sesuai dengan parameter input:

- GET /directoryObjects/{id}
- GET /users/{id}
- GET /servicePrincipals/{id}
- GET /groups/{id}

## EXAMPLES

### Contoh 1
```powershell
Get-AzKeyVaultRoleAssignment -HsmName myHsm
```

```output
RoleDefinitionName         DisplayName                      ObjectType Scope
------------------         -----------                      ---------- -----
Managed HSM Administrator  User 1 (user1@microsoft.com)     User       /
Managed HSM Crypto Auditor User 2 (user2@microsoft.com)     User       /keys
Managed HSM Backup         User 2 (user2@microsoft.com)     User       /
Managed HSM Administrator  User 2 (user2@microsoft.com)     User       /
```

Contoh ini mencantumkan semua penetapan peran "myHsm" pada semua cakupan.

### Contoh 2
```powershell
Get-AzKeyVaultRoleAssignment -HsmName myHsm -SignInName user1@microsoft.com -Scope "/keys"
```

```output
RoleDefinitionName         DisplayName                      ObjectType Scope
------------------         -----------                      ---------- -----
Managed HSM Crypto Auditor User 1 (user1@microsoft.com)     User       /keys
Managed HSM Backup         User 1 (user1@microsoft.com)     User       /keys
```

Contoh ini mencantumkan semua penetapan peran "myHsm" pada cakupan "/keys" dan memfilter hasilnya berdasarkan nama masuk pengguna.

## PARAMETERS

### -ApplicationId
SPN aplikasi.

```yaml
Type: System.String
Parameter Sets: List
Aliases: SPN, ServicePrincipalName

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

### -HsmName
Nama HSM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Id objek pengguna atau grup.

```yaml
Type: System.String
Parameter Sets: List
Aliases: Id, PrincipalId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleAssignmentName
Nama penetapan peran.

```yaml
Type: System.String
Parameter Sets: GetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitionId
Id Peran tempat prinsipal ditetapkan.

```yaml
Type: System.String
Parameter Sets: List
Aliases: RoleId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitionName
Nama peran RBAC untuk menetapkan prinsipal dengan.

```yaml
Type: System.String
Parameter Sets: List
Aliases: RoleName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan tempat penetapan peran atau definisi berlaku, misalnya, '/' atau '/keys' atau '/keys/{keyName}'.
'/' digunakan saat dihilangkan.

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

### -SignInName
SignInName pengguna.

```yaml
Type: System.String
Parameter Sets: List
Aliases: Email, UserPrincipalName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleAssignment

## NOTES

## RELATED LINKS
