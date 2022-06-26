---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.servicelinker/update-azservicelinkerforcontainerapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Update-AzServiceLinkerForContainerApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Update-AzServiceLinkerForContainerApp.md
ms.openlocfilehash: 6d83d62b28f6f7f4f168f264cc1925b8fb08c0f7
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146634340"
---
# Update-AzServiceLinkerForContainerApp

## SYNOPSIS
Operasi untuk memperbarui tautan yang ada di aplikasi kontainer.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzServiceLinkerForContainerApp -Name <String> -AuthInfo <IAuthInfoBase> -ClientType <ClientType>
 -Scope <String> -TargetService <ITargetServiceBase> -ContainerApp <String> -ResourceGroupName <String>
 [-ResourceUri <String>] [-SecretStoreKeyVaultId <String>] [-VNetSolutionType <VNetSolutionType>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-SubscriptionId <String>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzServiceLinkerForContainerApp -InputObject <IServiceLinkerIdentity> -AuthInfo <IAuthInfoBase>
 -ClientType <ClientType> -Scope <String> -TargetService <ITargetServiceBase>
 [-SecretStoreKeyVaultId <String>] [-VNetSolutionType <VNetSolutionType>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-SubscriptionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk memperbarui tautan yang ada di aplikasi kontainer.

## EXAMPLES

### Contoh 1: Memperbarui linker
```powershell
$target=New-AzServiceLinkerAzureResourceObject -Id /subscriptions/937bc588-a144-4083-8612-5f9ffbbddb14/resourceGroups/servicelinker-test-linux-group/providers/Microsoft.DBforPostgreSQL/servers/servicelinker-postgresql/databases/test
$authInfo=New-AzServiceLinkerSecretAuthInfoObject -Name username -SecretValue password 
Update-AzServiceLinkerForContainerApp -ResourceGroupName servicelinker-test-linux-group -ContainerApp servicelinker-app -TargetService $target -AuthInfo $authInfo -ClientType 'none' -Name postgres_connection -Scope 'simple-hello-world-container'
```

```output
Name
----
postgres_connection
```

Perbarui linker

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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerApp
Nama aplikasi kontainer sumber daya yang akan disambungkan.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.IServiceLinkerIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya Linker.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: LinkerName

Required: True
Position: Named
Default value: None
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
Grup sumber daya sumber daya yang akan disambungkan.

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

### -ResourceUri
Pengidentifikasi Azure Resource manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.IServiceLinkerIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ILinkerResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AUTHINFO `<IAuthInfoBase>`: Jenis autentikasi.
  - `AuthType <AuthType>`: Jenis autentikasi.

INPUTOBJECT `<IServiceLinkerIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LinkerName <String>]`: Nama sumber daya Linker.
  - `[ResourceUri <String>]`: Pengidentifikasi Azure Resource Manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

TARGETSERVICE `<ITargetServiceBase>`: Properti layanan target
  - `Type <TargetServiceType>`: Jenis layanan target.

## RELATED LINKS

