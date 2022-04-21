---
external help file: ''
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/start-azscontainerregistrysetup
schema: 2.0.0
ms.openlocfilehash: 8a06a707409c4c158aa22c4de288d42f72854246
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142721907"
---
# Start-AzsContainerRegistrySetup

## SYNOPSIS
Mencabut pengunggahan sertifikat registri kontainer dan penyebaran layanan.

## SYNTAX

### StartExpanded (Default)
```
Start-AzsContainerRegistrySetup [-Location <String>] [-SubscriptionId <String>] [-Password <SecureString>]
 [-SslCertInputFile <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Mulai
```
Start-AzsContainerRegistrySetup -STARTSETUPREQUEST \<IContainerRegistrySetupProperty> [-Location <String>]
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### StartViaIdentity
```
Start-AzsContainerRegistrySetup -INPUTOBJECT \<IContainerRegistryAdminIdentity>
 -STARTSETUPREQUEST \<IContainerRegistrySetupProperty> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### StartViaIdentityExpanded
```
Start-AzsContainerRegistrySetup -INPUTOBJECT \<IContainerRegistryAdminIdentity> [-Password <SecureString>]
 [-SslCertInputFile <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mencabut pengunggahan sertifikat registri kontainer dan penyebaran layanan.

## EXAMPLES

### Contoh 1: Mulai Penyiapan Azs ContainerRegistry
```powershell
PS C:\> Start-AzsContainerRegistrySetup -Password $password -SslCertInputFile $pfx_cert_path | ConvertTo-Json

{
    "Id":  "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Setup/locations/redmond/setup/value",
    "Name":  "redmond/value",
    "StatusUri":  "https://containerregistrysetup.ascu.azs:4335/providers/Microsoft.ContainerRegistry.Setup/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Setup/locations/redmond/setup?api-version=2019-11-01-preview",
    "Type":  "Microsoft.ContainerRegistry.Setup/locations/setup"
}
```

Mencabut pengunggahan sertifikat registri kontainer dan penyebaran layanan.

### Contoh 2: Mulai Penyiapan Azs ContainerRegistry saat contoh penyiapan lain sudah dimulai
```powershell
PS C:\> Start-AzsContainerRegistrySetup -Password $password -SslCertInputFile $pfx_cert_path | ConvertTo-Json

Start-AzsContainerRegistrySetup : Container registry deployment is still running. It is not allowed to repeat deployment at this stage.
At line:1 char:1
+ Start-AzsContainerRegistrySetup -Password $password -SslCertInputFile ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: ({ SubscriptionI...SetupProperty }:<>f__AnonymousType7`3) [Start-AzsContai...p_StartExpanded], Exception
    + FullyQualifiedErrorId : AcrDeploymentStillRunning,Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Cmdlets.StartAzsContainerRegistrySetup_StartExpanded
```

Mengembalikan kesalahan jika contoh Penyiapan lain sudah dimulai.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity
Parameter Sets: StartViaIdentity, StartViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama kawasan Azure.

```yaml
Type: System.String
Parameter Sets: Start, StartExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Kata sandi sertifikat Ssl.

```yaml
Type: System.Security.SecureString
Parameter Sets: StartExpanded, StartViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslCertInputFile
File Input untuk SslCert (sertifikat Ssl dalam format base64.)

```yaml
Type: System.String
Parameter Sets: StartExpanded, StartViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartSetupRequest
Properti penyetelan registri kontainer.
Untuk membangun, lihat bagian CATATAN untuk properti STARTSETUPREQUEST dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistrySetupProperty
Parameter Sets: Start, StartViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: Start, StartExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistrySetupProperty

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistrySetup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IContainerRegistryAdminIdentity>: Parameter Identitas
  - `[CapacityName <String>]`: Nama parameter kapasitas.
  - `[ConfigurationName <String>]`: Nama konfigurasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure.
  - `[QuotaName <String>]`: Nama kuota registri kontainer.
  - `[SubscriptionId <String>]`: ID langganan target.

STARTSETUPREQUEST \<IContainerRegistrySetupProperty>: Properti penyiapan registri kontainer.
  - `[Password <SecureString>]`: Kata sandi sertifikat Ssl.
  - `[SslCertBase64 <Byte[]>]`: Sertifikat SSL dalam format base64.

## RELATED LINKS

