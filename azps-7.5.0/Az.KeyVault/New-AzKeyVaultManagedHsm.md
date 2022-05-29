---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/new-azkeyvaultmanagedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultManagedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultManagedHsm.md
ms.openlocfilehash: 2ca5e91ab3f33fa35622bb330092f6415297b4d7
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145815534"
---
# New-AzKeyVaultManagedHsm

## SYNOPSIS
Membuat HSM terkelola.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/new-azkeyvaultmanagedhsm) untuk informasi terbaru.

## SYNTAX

```
New-AzKeyVaultManagedHsm [-Name] <String> [-ResourceGroupName] <String> [-Location] <String>
 [-Administrator] <String[]> [-Sku <String>] [-SoftDeleteRetentionInDays <Int32>]
 [-PublicNetworkAccess <String>] [-EnablePurgeProtection] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzKeyVaultManagedHsm** membuat HSM terkelola dalam grup sumber daya yang ditentukan. Untuk menambahkan, menghapus, atau mencantumkan kunci di HSM terkelola, pengguna harus: 
1. memberikan izin dengan menambahkan ID pengguna ke Administrator;
2. tambahkan penetapan peran untuk pengguna seperti "Pengguna Kripto HSM Terkelola" dan sebagainya;
3. cadangkan data domain keamanan HSM terkelola menggunakan `Export-AzKeyVaultSecurityDomain`.

## EXAMPLES

### Contoh 1: Membuat HSM terkelola StandardB1
```powershell
New-AzKeyVaultManagedHsm -Name 'myhsm' -ResourceGroupName 'myrg1' -Location 'eastus2euap' -Administrator "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini membuat HSM terkelola bernama myhsm di lokasi eastus2euap. Perintah menambahkan HSM terkelola ke grup sumber daya bernama myrg1. Karena perintah tidak menentukan nilai untuk parameter *SKU* , perintah membuat HSM terkelola Standard_B1.

### Contoh 2: Membuat HSM terkelola CustomB32
```powershell
New-AzKeyVaultManagedHsm -Name 'myhsm' -ResourceGroupName 'myrg1' -Location 'eastus2euap' -Administrator "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Sku 'CustomB32'
```

```output
Name  Resource Group Name Location    SKU

----  ------------------- --------    ---
myhsm myrg1               eastus2euap CustomB32
```

Perintah ini membuat HSM terkelola, sama seperti contoh sebelumnya. Namun, ini menentukan nilai CustomB32 untuk parameter *SKU* untuk membuat HSM terkelola CustomB32.

## PARAMETERS

### -Administrator
Id objek administrator awal untuk kumpulan HSM terkelola ini.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePurgeProtection
menentukan apakah perlindungan terhadap penghapusan menyeluruh diaktifkan untuk kumpulan HSM terkelola ini. Pengaturan ini hanya efektif jika penghapusan sementara juga diaktifkan. Mengaktifkan fungsionalitas ini tidak dapat diubah.

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

### -Lokasi
Menentukan wilayah Azure untuk membuat brankas kunci.
Gunakan perintah Get-AzResourceProvider dengan parameter ProviderNamespace untuk melihat pilihan Anda.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama HSM terkelola yang akan dibuat.
Nama dapat berupa kombinasi huruf, digit, atau tanda hubung apa pun.
Nama harus dimulai dan diakhbungi dengan huruf atau digit.
Nama harus unik secara universal.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HsmName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Mengontrol izin untuk lalu lintas sarana data yang berasal dari jaringan publik saat titik akhir privat diaktifkan.

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang ada untuk membuat brankas kunci.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Menentukan SKU instans HSM terkelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SoftDeleteRetentionInDays
Menentukan berapa lama kumpulan hsm terkelola yang dihapus dipertahankan, dan berapa lama hingga kumpulan hsm terkelola dalam status dihapus dapat dihapus menyeluruh. Defaultnya 90 hari.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengambil alih langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak memengaruhi cmdlet berikutnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tabel hash yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm

## NOTES

## RELATED LINKS

[Get-AzKeyVaultManagedHsm](./Get-AzKeyVaultManagedHsm.md)

[Remove-AzKeyVaultManagedHsm](./Remove-AzKeyVaultManagedHsm.md)

[Update-AzKeyVaultManagedHsm](./Update-AzKeyVaultManagedHsm.md)
