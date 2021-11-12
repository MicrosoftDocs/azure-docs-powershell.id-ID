---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 8300B143-E322-419E-BC98-DBA56DD90A59
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmRoleDefinition.md
ms.openlocfilehash: 23bba16ea6e80d784a9de9bfb10a3a127f53b3f3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425618"
---
# New-AzureRmRoleDefinition

## SYNOPSIS
Membuat peran kustom di Azure RBAC.
Sediakan file definisi peran JSON atau objek PSRoleDefinition sebagai input.
Pertama, gunakan perintah Get-AzureRmRoleDefinition untuk menghasilkan objek definisi peran garis dasar.
Lalu, modifikasi propertinya sebagaimana diperlukan.
Terakhir, gunakan perintah ini untuk membuat peran kustom menggunakan definisi peran.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InputFileParameterSet
```
New-AzureRmRoleDefinition [-InputFile] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RoleDefinitionParameterSet
```
New-AzureRmRoleDefinition [-Role] <PSRoleDefinition> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzureRmRoleDefinition membuat peran kustom di Azure Role-Based Access Control.
Sediakan definisi peran sebagai input ke perintah sebagai file JSON atau objek PSRoleDefinition.

Definisi peran input HARUS berisi properti berikut ini:

1) DisplayName: nama peran kustom

2) Deskripsi: deskripsi singkat tentang peran yang meringkas akses yang diberikan oleh peran tersebut.

3) Tindakan: kumpulan operasi yang memberikan akses kepada peran kustom.
Gunakan Get-AzureRmProviderOperations untuk mendapatkan operasi bagi penyedia sumber daya Azure yang bisa diamankan menggunakan Azure RBAC.
Berikut ini adalah beberapa string operasi yang valid:
 - "*/read" memberikan akses ke operasi baca dari semua penyedia sumber daya Azure.
 - "Microsoft.Network/*/read" memberikan akses ke operasi baca untuk semua tipe sumber daya di Microsoft.Penyedia sumber daya jaringan Azure.
 - "Microsoft.Compute/virtualMachines/*" memberikan akses ke semua operasi mesin virtual dan tipe sumber daya anak Anda.

4) AssignableScopes: kumpulan lingkup (langganan atau grup sumber daya Azure) tempat peran kustom akan tersedia untuk ditetapkan.
Menggunakan AssignableScopes, Peran kustom dapat tersedia untuk ditetapkan hanya di langganan atau grup sumber daya yang diperlukan, dan tidak mengacaukan pengalaman pengguna untuk langganan atau grup sumber daya lainnya.
Berikut adalah beberapa lingkup valid yang dapat ditetapkan:
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e", "/subscriptions/e91d47c4-76f3-4271-a796-21b4ecfe3624": membuat peran tersedia untuk diberikan di dua langganan.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e": memungkinkan peran tersedia untuk diberikan dalam satu langganan.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e/resourceGroups/Network": membuat peran tersedia hanya untuk tugas di grup Sumber daya jaringan.

Definisi peran input MUNGKIN berisi properti berikut ini:

1) NotActions: kumpulan operasi yang harus dikecualikan dari Tindakan untuk menentukan tindakan efektif bagi peran kustom.
Jika ada operasi khusus yang tidak ingin Anda berikan akses dalam peran kustom, lebih mudah menggunakan NotActions untuk mengeluarkannya, daripada menentukan semua operasi selain operasi tertentu itu dalam Tindakan.

CATATAN: Jika pengguna diberi peran yang menentukan operasi dalam NotActions dan juga menetapkan peran lain memberikan akses ke operasi yang sama - pengguna akan dapat melakukan operasi itu.
NotActions bukanlah aturan tolak - ini hanya merupakan cara yang mudah untuk membuat kumpulan operasi yang diperbolehkan saat operasi tertentu perlu dikecualikan.

Berikut adalah contoh definisi peran json yang dapat disediakan sebagai input { "Nama": "Contoso On-call", "Deskripsi": "Bisa memantau perhitungan, jaringan dan penyimpanan, dan memulai ulang mesin virtual", "Tindakan": \[ "Microsoft.Compute/*/read", "Microsoft.Compute/virtualMachines/start/action", "Microsoft.Compute/virtualMachines/restart/action", "Microsoft.Compute/virtualMachines/downloadRemoteDesktopConnectionFile/action", "Microsoft.Network/*/read", "Microsoft. Storage/*/read", "Microsoft.Authorization/*/read", "Microsoft.Resources/subscriptions/resourceGroups/read", "Microsoft.Resources/subscriptions/resourceGroups/resources/read", "Microsoft. Insights/alertRules/*", "Microsoft.Support/*" \] , "AssignableScopes": \[ "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx","/subscriptions/yyyyyyy-yyyy-yyyy-yyyy-yyyyy" \] }

## EXAMPLES

### -------------------------- Membuat menggunakan PSRoleDefinitionObject --------------------------
```
PS C:\> $role = Get-AzureRmRoleDefinition -Name "Virtual Machine Contributor"
          PS C:\> $role.Id = $null
          PS C:\> $role.Name = "Virtual Machine Operator"
          PS C:\> $role.Description = "Can monitor, start, and restart virtual machines."
          PS C:\> $role.Actions.RemoveRange(0,$role.Actions.Count)
          PS C:\> $role.Actions.Add("Microsoft.Compute/*/read")
          PS C:\> $role.Actions.Add("Microsoft.Compute/virtualMachines/start/action")
          PS C:\> $role.Actions.Add("Microsoft.Compute/virtualMachines/restart/action")
          PS C:\> $role.Actions.Add("Microsoft.Compute/virtualMachines/downloadRemoteDesktopConnectionFile/action")
          PS C:\> $role.Actions.Add("Microsoft.Network/*/read")
          PS C:\> $role.Actions.Add("Microsoft.Storage/*/read")
          PS C:\> $role.Actions.Add("Microsoft.Authorization/*/read")
          PS C:\> $role.Actions.Add("Microsoft.Resources/subscriptions/resourceGroups/read")
          PS C:\> $role.Actions.Add("Microsoft.Resources/subscriptions/resourceGroups/resources/read")
          PS C:\> $role.Actions.Add("Microsoft.Insights/alertRules/*")
          PS C:\> $role.Actions.Add("Microsoft.Support/*")
          PS C:\> $role.AssignableScopes.Clear()
          PS C:\> $role.AssignableScopes.Add("/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e")

          PS C:\> New-AzureRmRoleDefinition -Role $role
```

### -------------------------- Buat menggunakan file JSON --------------------------
```
PS C:\> New-AzureRmRoleDefinition -InputFile C:\Temp\roleDefinition.json
```

## PARAMETERS

### -InputFile
Nama file berisi definisi peran json tunggal.

```yaml
Type: System.String
Parameter Sets: InputFileParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Peran
Objek definisi peran.

```yaml
Type: Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition
Parameter Sets: RoleDefinitionParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[Get-AzureRmProviderOperation](./Get-AzureRmProviderOperation.md)

[Get-AzureRmRoleDefinition](./Get-AzureRmRoleDefinition.md)

[Set-AzureRmRoleDefinition](./Set-AzureRmRoleDefinition.md)

[Remove-AzureRmRoleDefinition](./Remove-AzureRmRoleDefinition.md)

