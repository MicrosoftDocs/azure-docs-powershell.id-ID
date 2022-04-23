---
external help file: ''
Module Name: Az.Blockchain
online version: https://docs.microsoft.com/powershell/module/az.blockchain/new-azblockchainmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Blockchain/help/New-AzBlockchainMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Blockchain/help/New-AzBlockchainMember.md
ms.openlocfilehash: ba0d280a7be09e9cde40c0069d42ae7d2d37b1fb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143302031"
---
# New-AzBlockchainMember

## SYNOPSIS
Buat anggota blockchain.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.blockchain/new-azblockchainmember) untuk informasi terbaru.

## SYNTAX

```
New-AzBlockchainMember -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Consortium <String>] [-ConsortiumManagementAccountPassword <SecureString>]
 [-ConsortiumMemberDisplayName <String>] [-ConsortiumRole <String>] [-FirewallRule <IFirewallRule[]>]
 [-Location <String>] [-Password <SecureString>] [-Protocol <BlockchainProtocol>] [-Sku <String>]
 [-SkuTier <String>] [-Tag <Hashtable>] [-ValidatorNodeSkuCapacity <Int32>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat anggota blockchain.

## EXAMPLES

### Contoh 1: Buat anggota blockchain baru
```powershell
PS C:\> $passwd = 'strongMemberAccountPassword@1' | ConvertTo-SecureString -AsPlainText -Force
PS C:\> $csPasswd = 'strongConsortiumManagementPassword@1' | ConvertTo-SecureString -AsPlainText -Force
PS C:\> New-AzBlockchainMember -Name dolauli002 -ResourceGroupName testgroup -Consortium consor002 -ConsortiumManagementAccountPassword $csPasswd -Location eastus -Password $passwd -Protocol Quorum -Sku S0

Location Name       Type
-------- ----       ----
eastus   dolauli002 Microsoft.Blockchain/blockchainMembers
```

Perintah ini menciptakan anggota blockchain baru.

## PARAMETERS

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

### -Consortium
Mendapatkan atau mengatur konsorsium untuk anggota blockchain.

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

### -ConsortiumManagementAccountPassword
Mengatur kata sandi akun manajemen konsorsium terkelola.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsortiumMemberDisplayName
Mendapatkan nama tampilan anggota dalam konsorsium.

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

### -ConsortiumRole
Mendapatkan peran anggota dalam konsorsium.

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

### -FirewallRule
Mendapatkan atau mengatur aturan firewall Untuk membangun, lihat bagian CATATAN untuk properti FIREWALLRULE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Blockchain.Models.Api20180601Preview.IFirewallRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi GEO dari layanan blockchain.

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

### -Nama
Nama anggota Blockchain.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BlockchainMemberName

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

### -Password
Mengatur kata sandi auth dasar anggota blockchain.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Mendapatkan atau mengatur protokol blockchain.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Blockchain.Support.BlockchainProtocol
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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

### -Sku
Mendapatkan atau mengatur nama Sku

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

### -SkuTier
Mendapatkan atau mengatur tingkat Sku

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
Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan adalah bagian dari URI untuk setiap panggilan layanan.

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

### -Tag
Tag layanan yang merupakan daftar pasangan nilai kunci yang menjelaskan sumber daya.

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

### -ValidatorNodeSkuCapacity
Mendapatkan atau mengatur kapasitas simpul.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Blockchain.Models.Api20180601Preview.IBlockchainMember

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


FIREWALLRULE <IFirewallRule[]>: Mendapatkan atau mengatur aturan firewall
  - `[EndIPAddress <String>]`: Mendapatkan atau mengatur alamat IP akhir rentang aturan firewall.
  - `[RuleName <String>]`: Mendapatkan atau mengatur nama aturan firewall.
  - `[StartIPAddress <String>]`: Mendapatkan atau mengatur alamat IP mulai rentang aturan firewall.

## RELATED LINKS

