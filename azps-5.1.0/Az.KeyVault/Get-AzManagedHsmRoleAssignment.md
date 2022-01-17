---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/az.keyvault/get-azmanagedhsmroleassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/KeyVault/KeyVault/help/Get-AzManagedHsmRoleAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/KeyVault/KeyVault/help/Get-AzManagedHsmRoleAssignment.md
ms.openlocfilehash: 20e80617d47cd0a1f0ffb5cdb80d836656cd9abd
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136024963"
---
# Get-AzManagedHsmRoleAssignment

## SYNOPSIS
Mendapatkan atau mencantumkan penetapan peran HSM yang dikelola. Gunakan parameter terkait untuk mencantumkan penetapan ke pengguna tertentu atau definisi peran.

## SINTAKS

### Daftar (Default)
```
Get-AzManagedHsmRoleAssignment [-HsmName] <String> [-Scope <String>] [-RoleDefinitionName <String>]
 [-RoleDefinitionId <String>] [-ObjectId <String>] [-SignInName <String>] [-ApplicationId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByName
```
Get-AzManagedHsmRoleAssignment [-HsmName] <String> [-Scope <String>] -RoleAssignmentName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Gunakan `Get-AzManagedHsmRoleAssignment` perintah untuk mencantumkan semua penetapan peran yang efektif pada lingkup.
Tanpa parameter apa pun, perintah ini mengembalikan semua penetapan peran yang dibuat di bawah HSM yang dikelola.
Daftar ini bisa difilter menggunakan parameter pemfilteran untuk pokok, peran dan lingkup.
Subjek tugas harus ditentukan.
Untuk menentukan pengguna, gunakan parameter SignInName atau Azure AD ObjectId.
Untuk menentukan grup keamanan, gunakan parameter Azure AD ObjectId.
Dan untuk menentukan aplikasi Azure AD, gunakan parameter ApplicationId atau ObjectId.
Peran yang sedang ditetapkan harus ditentukan menggunakan parameter RoleDefinitionName atau RoleDefinitionId.
Lingkup di mana akses sedang diberikan mungkin ditentukan. Defaultnya adalah "/".

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzManagedHsmRoleAssignment -HsmName myHsm

RoleDefinitionName         DisplayName                      ObjectType Scope
------------------         -----------                      ---------- -----
Managed HSM Administrator  User 1 (user1@microsoft.com)     User       /
Managed HSM Crypto Auditor User 2 (user2@microsoft.com)     User       /keys
Managed HSM Backup         User 2 (user2@microsoft.com)     User       /
Managed HSM Administrator  User 2 (user2@microsoft.com)     User       /
```

Contoh ini mencantumkan semua penetapan peran "myHsm" pada semua lingkupnya.

### Contoh 2
```powershell
PS C:\> Get-AzManagedHsmRoleAssignment -HsmName myHsm -SignInName user1@microsoft.com -Scope "/keys"

RoleDefinitionName         DisplayName                      ObjectType Scope
------------------         -----------                      ---------- -----
Managed HSM Crypto Auditor User 1 (user1@microsoft.com)     User       /keys
Managed HSM Backup         User 1 (user1@microsoft.com)     User       /keys
```

This example lists all role assignments of "myHsm" on "/keys" scope and filters the result by user sign-in name.

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
ID objek pengguna atau grup.

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
Id Peran pokok ditugaskan kepada.

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
Nama peran RBAC untuk menetapkan pokoknya.

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

### -Lingkup
Lingkup di mana penetapan peran atau definisi berlaku, misalnya '/' atau '/keys' atau '/keys/{keyName}'.
'/' digunakan ketika dihilangkan.

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
Pengguna SignInName.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleAssignment

## CATATAN

## LINK TERKAIT
