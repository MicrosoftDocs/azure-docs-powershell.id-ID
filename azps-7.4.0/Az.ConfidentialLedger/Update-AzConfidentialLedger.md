---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.confidentialledger/update-azconfidentialledger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Update-AzConfidentialLedger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Update-AzConfidentialLedger.md
ms.openlocfilehash: c1bd50789c80a3100c80f90606c6854c2acd93b2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143230337"
---
# Update-AzConfidentialLedger

## SYNOPSIS
Memperbarui properti Buku Besar Rahasia

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
Memperbarui properti Buku Besar Rahasia

## EXAMPLES

### Contoh 1: Memperbarui tag untuk Buku Besar Rahasia
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

Memperbarui metadata untuk Buku Besar Rahasia yang sudah ada.

## PARAMETERS

### -AadBasedSecurityPrincipal
Array semua Prinsipal Keamanan berbasis AAD.
Untuk membangun, lihat bagian CATATAN untuk properti AADBASEDSECURITYPRINCIPAL dan membuat tabel hash.

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
Menjalankan perintah sebagai pekerjaan

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
Array semua Prinsipal Keamanan berbasis sert.
Untuk membangun, lihat bagian CATATAN untuk properti CERTBASEDSECURITYPRINCIPAL dan membuat tabel hash.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Tipe Buku Besar Rahasia

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
Lokasi Azure tempat Buku Besar Rahasia dijalankan.

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

### -Nama
Nama Buku Besar Rahasia

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
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000)

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
Tag tambahan untuk Buku Besar Rahasia

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

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.IConfidentialLedgerIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.IConfidentialLedger

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AADBASEDSECURITYPRINCIPAL <IAadBasedSecurityPrincipal[]>: Array semua Prinsipal Keamanan berbasis AAD.
  - `[LedgerRoleName <LedgerRoleName?>]`: LedgerRole yang terkait dengan Security Principal of Ledger
  - `[PrincipalId <String>]`: Id Prinsipal Prinsipal berbasis UUID/GUID dari Prinsipal Keamanan
  - `[TenantId <String>]`: Id Penyewa berbasis UUID/GUID dari Prinsipal Keamanan

CERTBASEDSECURITYPRINCIPAL <ICertBasedSecurityPrincipal[]>: Array semua Prinsipal Keamanan berbasis sert.
  - `[Cert <String>]`: Kunci publik sertifikat pengguna (.pem atau .cer)
  - `[LedgerRoleName <LedgerRoleName?>]`: LedgerRole yang terkait dengan Security Principal of Ledger

INPUTOBJECT <IConfidentialLedgerIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LedgerName <String>]`: Nama Buku Besar Rahasia
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000)

## RELATED LINKS

