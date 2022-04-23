---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 8300B143-E322-419E-BC98-DBA56DD90A59
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleDefinition.md
ms.openlocfilehash: 9d1da04f8a97011786b74e587f1eeaf6975cf73e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143251721"
---
# New-AzRoleDefinition

## SYNOPSIS
Membuat peran kustom di Azure RBAC.
Sediakan file definisi peran JSON atau objek PSRoleDefinition sebagai input.
Pertama, gunakan perintah Get-AzRoleDefinition untuk menghasilkan objek definisi peran garis dasar.
Lalu, ubah propertinya sesuai kebutuhan.
Terakhir, gunakan perintah ini untuk membuat peran kustom menggunakan definisi peran.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/new-azroledefinition) untuk informasi terbaru.

## SYNTAX

### InputFileParameterSet
```
New-AzRoleDefinition [-InputFile] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RoleDefinitionParameterSet
```
New-AzRoleDefinition [-Role] <PSRoleDefinition> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzRoleDefinition membuat peran kustom di Azure Role-Based Access Control.
Berikan definisi peran sebagai input ke perintah sebagai file JSON atau objek PSRoleDefinition.
Definisi peran input HARUS berisi properti berikut:
1) DisplayName: nama peran kustom
2) Deskripsi: deskripsi singkat tentang peran yang meringkas akses yang diberikan peran.
3) Tindakan: kumpulan operasi tempat peran kustom memberikan akses.
Gunakan Get-AzProviderOperation untuk mendapatkan operasi untuk penyedia sumber daya Azure yang dapat diamankan menggunakan Azure RBAC.
Berikut adalah beberapa string operasi yang valid:
 - "*/read" memberikan akses ke operasi baca semua penyedia sumber daya Azure.
 - "Microsoft.Network/*/read" memberikan akses ke operasi baca untuk semua tipe sumber daya di penyedia sumber daya Microsoft.Network Azure.
 - "Microsoft.Compute/virtualMachines/*" memberikan akses ke semua operasi mesin virtual dan tipe sumber daya anaknya.
4) AssignableScopes: kumpulan lingkup (langganan Azure atau grup sumber daya) di mana peran kustom akan tersedia untuk penetapan.
Menggunakan AssignableScopes, Anda dapat membuat peran kustom tersedia untuk tugas hanya dalam langganan atau grup sumber daya yang memerlukannya, dan tidak mengacaukan pengalaman pengguna untuk langganan atau grup sumber daya lainnya.
Berikut adalah beberapa lingkup valid yang dapat ditetapkan:
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e", "/subscriptions/e91d47c4-76f3-4271-a796-21b4ecfe3624": membuat peran tersedia untuk tugas dalam dua langganan.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e": membuat peran tersedia untuk tugas dalam satu langganan.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e/resourceGroups/Network": membuat peran tersedia untuk penetapan hanya dalam grup sumber daya Jaringan.
Definisi peran input MAY berisi properti berikut ini:
1) NotActions: kumpulan operasi yang harus dikecualikan dari Tindakan untuk menentukan tindakan efektif untuk peran kustom.
Jika ada operasi tertentu yang tidak ingin Anda berikan akses ke dalam peran kustom, lebih mudah menggunakan NotActions untuk mengecualikannya, daripada menentukan semua operasi selain operasi tertentu dalam Tindakan.
2) DataActions: kumpulan operasi data tempat peran kustom memberikan akses.
3) NotDataActions: kumpulan operasi yang harus dikecualikan dari DataActions untuk menentukan tindakan data yang efektif untuk peran kustom.
Jika ada operasi data tertentu yang tidak ingin Anda berikan aksesnya dalam peran kustom, lebih mudah menggunakan NotDataActions untuk mengecualikannya, daripada menentukan semua operasi selain operasi tertentu dalam Tindakan.
CATATAN: Jika pengguna diberi peran yang menentukan operasi dalam NotActions dan juga menetapkan peran lain memberikan akses ke operasi yang sama - pengguna akan dapat melakukan operasi tersebut.
NotActions bukan aturan penolakan - ini adalah cara yang mudah untuk membuat sekumpulan operasi yang diizinkan ketika operasi tertentu perlu dikecualikan.
Berikut ini adalah contoh definisi peran json yang dapat disediakan sebagai input { "Name": "Updated Role", "Deskripsi": "Dapat memantau semua sumber daya dan memulai dan memulai ulang mesin virtual", "Tindakan": \[ "*/read", "Microsoft.ClassicCompute/virtualmachines/restart/action", "Microsoft.ClassicCompute/virtualmachines/start/action" \], "NotActions": \[ "*/write" \], "DataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/read" \], "NotDataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/write" \], "AssignableScopes": \["/subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxx"\] }

## EXAMPLES

### Contoh 1: Membuat menggunakan PSRoleDefinitionObject
```powershell
PS C:\> $role = Get-AzRoleDefinition -Name "Virtual Machine Contributor"

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
PS C:\> $role.AssignableScopes.Add("/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx")

PS C:\> New-AzRoleDefinition -Role $role
```

### Contoh 2: Membuat menggunakan file JSON
```powershell
PS C:\> New-AzRoleDefinition -InputFile C:\Temp\roleDefinition.json
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

### -InputFile
Nama file yang berisi definisi peran json tunggal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition

## NOTES
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, sumber daya, grup, Templat, penyebaran

## RELATED LINKS

[Get-AzProviderOperation](./Get-AzProviderOperation.md)

[Get-AzRoleDefinition](./Get-AzRoleDefinition.md)

[Set-AzRoleDefinition](./Set-AzRoleDefinition.md)

[Remove-AzRoleDefinition](./Remove-AzRoleDefinition.md)

