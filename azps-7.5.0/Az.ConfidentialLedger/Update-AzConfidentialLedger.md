---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.confidentialledger/update-azconfidentialledger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Update-AzConfidentialLedger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Update-AzConfidentialLedger.md
ms.openlocfilehash: 135dc1d32353214306956aab3d7d2f70d112e4ce
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146610184"
---
# Update-AzConfidentialLedger

## SYNOPSIS
Updates properti Confidential Ledger

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.confidentialledger/update-azconfidentialledger) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzConfidentialLedger -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-AadBasedSecurityPrincipal <IAadBasedSecurityPrincipal[]>]
 [-CertBasedSecurityPrincipal <ICertBasedSecurityPrincipal[]>] [-LedgerType <LedgerType>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzConfidentialLedger -InputObject <IConfidentialLedgerIdentity> -Location <String>
 [-AadBasedSecurityPrincipal <IAadBasedSecurityPrincipal[]>]
 [-CertBasedSecurityPrincipal <ICertBasedSecurityPrincipal[]>] [-LedgerType <LedgerType>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Updates properti Confidential Ledger

## EXAMPLES

### Contoh 1: Memperbarui tag untuk Confidential Ledger
```powershell
PS C:\> Update-AzConfidentialLedger `
  -Name test-ledger `
  -ResourceGroupName rg-000 `
  -SubscriptionId 00000000-0000-0000-0000-000000000000 `
  -AadBasedSecurityPrincipal `
      @{
          LedgerRoleName="Administrator"; 
          PrincipalId="34621747-6fc8-4771-a2eb-72f31c461f2e"; 
          TenantId="bce123b9-2b7b-4975-8360-5ca0b9b1cd08"
      } `
  -CertBasedSecurityPrincipal `
      @{
          Cert="-----BEGIN CERTIFICATE-----********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************-----END CERTIFICATE-----"; 
          LedgerRoleName="Reader"
      } `
  -LedgerType Public `
  -Location eastus `
  -Tag `
      @{
          Location="additional properties 0"
          NewTag="New tag"
      }

Location Name
eastus   test-ledger
```

Updates metadata untuk Confidential Ledger yang ada.

## PARAMETERS

### -AadBasedSecurityPrincipal
Array dari semua Perwakilan Keamanan berbasis AAD.
Untuk membuat, lihat bagian CATATAN untuk properti AADBASEDSECURITYPRINCIPAL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.IAadBasedSecurityPrincipal[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -CertBasedSecurityPrincipal
Array semua Perwakilan Keamanan berbasis sertifikasi.
Untuk membuat, lihat bagian CATATAN untuk properti CERTBASEDSECURITYPRINCIPAL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.ICertBasedSecurityPrincipal[]
Parameter Sets: (All)
Aliases:

Required: False
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
Type: Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.IConfidentialLedgerIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LedgerType
Jenis Confidential Ledger

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Support.LedgerType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Azure tempat Confidential Ledger berjalan.

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

### -Name
Nama Confidential Ledger

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: LedgerName

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
Nama grup sumber daya.

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

### -SubscriptionId
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag tambahan untuk Confidential Ledger

```yaml
Type: System.Collections.Hashtable
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

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.IConfidentialLedgerIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.IConfidentialLedger

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AADBASEDSECURITYPRINCIPAL <IAadBasedSecurityPrincipal[]>: Array semua Perwakilan Keamanan berbasis AAD.
  - `[LedgerRoleName <LedgerRoleName?>]`: LedgerRole yang terkait dengan Perwakilan Keamanan Ledger
  - `[PrincipalId <String>]`: Id Utama berbasis UUID/GUID dari Perwakilan Keamanan
  - `[TenantId <String>]`: Id Penyewa berbasis UUID/GUID dari Perwakilan Keamanan

CERTBASEDSECURITYPRINCIPAL <ICertBasedSecurityPrincipal[]>: Array semua Perwakilan Keamanan berbasis sertifikasi.
  - `[Cert <String>]`: Kunci umum sertifikat pengguna (.pem atau .cer)
  - `[LedgerRoleName <LedgerRoleName?>]`: LedgerRole yang terkait dengan Perwakilan Keamanan Ledger

INPUTOBJECT `<IConfidentialLedgerIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LedgerName <String>]`: Nama Confidential Ledger
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

## RELATED LINKS

