---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.servicelinker/new-azservicelinkerforcontainerapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerForContainerApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerForContainerApp.md
ms.openlocfilehash: 00857472ec60432da56bbb6a7613063e52f19f3f
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146636356"
---
# New-AzServiceLinkerForContainerApp

## SYNOPSIS
Membuat atau memperbarui sumber daya linker di aplikasi kontainer.

## SYNTAX

```
New-AzServiceLinkerForContainerApp -AuthInfo <IAuthInfoBase> -Scope <String>
 -TargetService <ITargetServiceBase> -ContainerApp <String> -ResourceGroupName <String> [-Name <String>]
 [-ResourceUri <String>] [-ClientType <ClientType>] [-SecretStoreKeyVaultId <String>]
 [-VNetSolutionType <VNetSolutionType>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-SubscriptionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sumber daya linker di aplikasi kontainer.

## EXAMPLES

### Contoh 1: Membuat tautan layanan antara aplikasi kontainer dan postgresql
```powershell
$target=New-AzServiceLinkerAzureResourceObject -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/servicelinker-test-group/providers/Microsoft.DBforPostgreSQL/servers/servicelinker-postgresql/databases/test

$authInfo=New-AzServiceLinkerSecretAuthInfoObject -Name testUser -SecretValue ***  

New-AzServiceLinkerForContainerApp -TargetService $target -AuthInfo $auth -ClientType dotnet -LinkerName testLinker -ContainerApp servicelinker-app -ResourceGroupName servicelinker-test-linux-group -Scope 'simple-hello-world-container'
```

```output
Name
----
testLinker
```

Membuat tautan layanan antara Container AppName dan postgresql

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

### -AuthInfo
Jenis Autentikasi.
Untuk membuat, lihat bagian NOTES untuk properti AUTHINFO dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.IAuthInfoBase
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientType
Jenis klien aplikasi

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Support.ClientType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "none"
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerApp
Nama aplikasi kontainer sumber daya yang akan disambungkan.

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

### -Name
Nama sumber daya Linker.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LinkerName

Required: False
Position: Named
Default value: "connect_"+(-join ((65..90) + (97..122) | Get-Random -Count 5 | % {[char]$_}))
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
[ResourceGroupCompleter] Grup sumber daya sumber daya yang akan disambungkan.

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

### -ResourceUri
Pengidentifikasi Azure Resource manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

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

### -Cakupan
cakupan koneksi dalam layanan sumber.

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

### -SecretStoreKeyVaultId
Id brankas kunci untuk menyimpan rahasia

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

### -TargetService
Properti layanan target Untuk membangun, lihat bagian CATATAN untuk properti TARGETSERVICE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ITargetServiceBase
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetSolutionType
Jenis solusi VNet.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Support.VNetSolutionType
Parameter Sets: (All)
Aliases:

Required: False
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ILinkerResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AUTHINFO `<IAuthInfoBase>`: Jenis autentikasi.
  - `AuthType <AuthType>`: Jenis autentikasi.

TARGETSERVICE `<ITargetServiceBase>`: Properti layanan target
  - `Type <TargetServiceType>`: Jenis layanan target.

## RELATED LINKS

