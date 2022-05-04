---
external help file: ''
Module Name: Az.Databricks
online version: https://docs.microsoft.com/powershell/module/az.databricks/update-azdatabricksworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Update-AzDatabricksWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Update-AzDatabricksWorkspace.md
ms.openlocfilehash: 390c7776df42e91ec5173000c89aea6d898004fe
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144693940"
---
# Update-AzDatabricksWorkspace

## SYNOPSIS
Memperbarui ruang kerja.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.databricks/update-azdatabricksworkspace) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzDatabricksWorkspace -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AmlWorkspaceId <String>] [-EncryptionKeyName <String>] [-EncryptionKeySource <KeySource>]
 [-EncryptionKeyVaultUri <String>] [-EncryptionKeyVersion <String>] [-KeyVaultKeyName <String>]
 [-KeyVaultKeyVersion <String>] [-KeyVaultUri <String>] [-PrepareEncryption] [-SkuTier <String>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzDatabricksWorkspace -InputObject <IDatabricksIdentity> [-AmlWorkspaceId <String>]
 [-EncryptionKeyName <String>] [-EncryptionKeySource <KeySource>] [-EncryptionKeyVaultUri <String>]
 [-EncryptionKeyVersion <String>] [-KeyVaultKeyName <String>] [-KeyVaultKeyVersion <String>]
 [-KeyVaultUri <String>] [-PrepareEncryption] [-SkuTier <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui ruang kerja.

## EXAMPLES

### Contoh 1: Memperbarui tag ruang kerja Databricks
```powershell
$dbr = Get-AzDatabricksWorkspace -ResourceGroupName databricks-rg-rqb2yo -Name workspaceopsc46
Update-AzDatabricksWorkspace -InputObject $dbr -Tag @{key="value"}
```

```output
Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Perintah ini memperbarui tag ruang kerja Databricks.

### Contoh 2: Mengaktifkan enkripsi di ruang kerja Databricks
```powershell
Update-AzDatabricksWorkspace -ResourceGroupName databricks-rg-rqb2yo -Name workspace3miaeb -PrepareEncryption
Update-AzDatabricksWorkspace -ResourceGroupName databricks-rg-rqb2yo -Name workspace3miaeb -EncryptionKeySource 'Microsoft.KeyVault' -EncryptionKeyVaultUri https://keyvalult-j3kube.vault.azure.net/ -EncryptionKeyName key-p3bjsf -EncryptionKeyVersion 853999da89714fb4a1408681945135fd
```

```output
Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Mengaktifkan enkripsi pada ruang kerja Databricks mengambil tiga langkah:
1.
Perbarui ruang kerja dengan `-PrepareEncryption` (jika tidak dibuat).
1.
Temukan `StorageAccountIdentityPrincipalId` dalam output dari langkah terakhir.
Berikan izin kunci kepada prinsipal.
1.
Perbarui ruang kerja lagi untuk mengisi informasi tentang kunci enkripsi:
    - `-EncryptionKeySource`
    - `-EncryptionKeyVaultUri`
    - `-EncryptionKeyName`
    - `-EncryptionKeyVersion`

### Contoh 3: Menonaktifkan enkripsi di ruang kerja Databricks
```powershell
Update-AzDatabricksWorkspace -ResourceGroupName databricks-rg-rqb2yo -Name workspace3miaeb -EncryptionKeySource 'Default'
```

Untuk menonaktifkan enkripsi, cukup atur `-EncryptionKeySource` ke `'Default'`.

## PARAMETERS

### -AmlWorkspaceId
Nilai yang harus digunakan untuk bidang ini.

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

### -EncryptionKeyName
Nama kunci Key Vault.

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

### -EncryptionKeySource
Sumber kunci enkripsi (penyedia).
Nilai yang mungkin (tidak peka huruf besar/kecil): Default, Microsoft.Keyvault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.KeySource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyVaultUri
URI (nama DNS) Key Vault.

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

### -EncryptionKeyVersion
Versi kunci KeyVault.

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

### -InputObject
Parameter identitas.
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyVaultKeyName
Nama kunci KeyVault.

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

### -KeyVaultKeyVersion
Versi kunci KeyVault.

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

### -KeyVaultUri
Uri Dari KeyVault.

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

### -Name
Nama ruang kerja.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: WorkspaceName

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

### -PrepareEncryption
Siapkan ruang kerja untuk enkripsi.
Mengaktifkan Identitas Terkelola untuk akun penyimpanan terkelola.

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
Nama tidak peka huruf besar/kecil.

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

### -SkuTier
Tingkat SKU.

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
ID langganan target.

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
Tag sumber daya.

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

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20210401Preview.IWorkspace

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDatabricksIdentity>: Parameter identitas.
  - `[GroupId <String>]`: Nama sumber daya tautan privat
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PeeringName <String>]`: Nama peering vNet ruang kerja.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja.

## RELATED LINKS

