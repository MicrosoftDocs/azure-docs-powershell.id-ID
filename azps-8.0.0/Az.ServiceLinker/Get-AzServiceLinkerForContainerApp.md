---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.servicelinker/get-azservicelinkerforcontainerapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerForContainerApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerForContainerApp.md
ms.openlocfilehash: 2706fef76ab2f1d82b63b8879774fa63ac7b7d12
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145534977"
---
# Get-AzServiceLinkerForContainerApp

## SYNOPSIS
Mengembalikan sumber daya Linker untuk nama tertentu di aplikasi kontainer.

## SYNTAX

### Daftar (Default)
```
Get-AzServiceLinkerForContainerApp -ContainerApp <String> -ResourceGroupName <String> [-ResourceUri <String>]
 [-DefaultProfile <PSObject>] [-SubscriptionId <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzServiceLinkerForContainerApp -Name <String> -ContainerApp <String> -ResourceGroupName <String>
 [-ResourceUri <String>] [-DefaultProfile <PSObject>] [-SubscriptionId <String>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzServiceLinkerForContainerApp -InputObject <IServiceLinkerIdentity> [-DefaultProfile <PSObject>]
 [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan sumber daya Linker untuk nama tertentu di aplikasi kontainer.

## EXAMPLES

### Contoh 1: Mencantumkan semua linker dalam aplikasi kontainer
```powershell
Get-AzServiceLinkerForContainerApp -ContainerApp servicelinker-app -ResourceGroupName servicelinker-test-group -Scope 'simple-hello-world-container'
```

```output
Name
----
appconfig_08b18
postgresql_novnet
postgresql_203ca
eventhub_3ab5f
```

Mencantumkan semua linker di aplikasi kontainer

### Contoh 2: Dapatkan linker berdasarkan nama
```powershell
Get-AzServiceLinkerForContainerApp -ContainerApp servicelinker-app -ResourceGroupName servicelinker-test-group  -Name postgresql_connection | fl
```

```output
AuthInfo                     : Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Model
                               s.Api20220501.SecretAuthInfo
ClientType                   : dotnet
Id                           : /subscriptions/00000000-0000-0000-0000-000000000000/re 
                               sourceGroups/servicelinker-test-group/providers/ 
                               Microsoft.App/containerApps/servicelinker-app/providers 
                               /Microsoft.ServiceLinker/linkers/postgresql_connection     
Name                         : postgresql_connection
ProvisioningState            : Succeeded
Scope                        : 
SecretStoreKeyVaultId        :
SystemDataCreatedAt          :
SystemDataCreatedBy          :
SystemDataCreatedByType      :
SystemDataLastModifiedAt     :
SystemDataLastModifiedBy     :
SystemDataLastModifiedByType :
TargetService                : Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Model 
                               s.Api20220501.AzureResource
Type                         : microsoft.servicelinker/linkers
VNetSolutionType             : serviceEndpoint

```

Dapatkan linker berdasarkan nama

### Contoh 3: Dapatkan linker melalui objek identitas
```powershell
$identity = @{
ResourceUri = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/servicelinker-test-linux-group/providers/Microsoft.App/containerApps/servicelinker-app'
LinkerName = 'postgresql_connection'}

$identity | Get-AzServiceLinkerForContainerApp  |fl
```

```output
AuthInfo                     : Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Model
                               s.Api20220501.SecretAuthInfo
ClientType                   : dotnet
Id                           : /subscriptions/00000000-0000-0000-0000-000000000000/re 
                               sourceGroups/servicelinker-test-group/providers/ 
                               Microsoft.App/containerApps/servicelinker-app/providers 
                               /Microsoft.ServiceLinker/linkers/postgresql_connection     
Name                         : postgresql_connection
ProvisioningState            : Succeeded
Scope                        : 
SecretStoreKeyVaultId        :
SystemDataCreatedAt          :
SystemDataCreatedBy          :
SystemDataCreatedByType      :
SystemDataLastModifiedAt     :
SystemDataLastModifiedBy     :
SystemDataLastModifiedByType :
TargetService                : Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Model 
                               s.Api20220501.AzureResource
Type                         : microsoft.servicelinker/linkers
VNetSolutionType             : serviceEndpoint

```

Dapatkan linker berdasarkan nama

## PARAMETERS

### -ContainerApp
Nama aplikasi kontainer sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: Get, List
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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.IServiceLinkerIdentity
Parameter Sets: GetViaIdentity
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
Parameter Sets: Get
Aliases: LinkerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya sumber daya yang akan disambungkan.

```yaml
Type: System.String
Parameter Sets: Get, List
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
Parameter Sets: Get, List
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


INPUTOBJECT <IServiceLinkerIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LinkerName <String>]`: Nama sumber daya Linker.
  - `[ResourceUri <String>]`: Pengidentifikasi Azure Resource manager yang sepenuhnya memenuhi syarat dari sumber daya yang akan disambungkan.

## RELATED LINKS

