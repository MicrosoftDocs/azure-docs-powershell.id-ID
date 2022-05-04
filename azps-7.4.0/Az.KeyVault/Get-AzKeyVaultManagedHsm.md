---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultmanagedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedHsm.md
ms.openlocfilehash: 1bbdb35928c03baad0f76a199ebf166d58f5def2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144580844"
---
# Get-AzKeyVaultManagedHsm

## SYNOPSIS
Dapatkan HSM terkelola.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/get-azkeyvaultmanagedhsm) untuk informasi terbaru.

## SYNTAX

### GetManagedHsm
```
Get-AzKeyVaultManagedHsm [[-Name] <String>] [[-ResourceGroupName] <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>] [<CommonParameters>]
```

### GetDeletedManagedHsm
```
Get-AzKeyVaultManagedHsm [-Name] <String> [-Location] <String> [-InRemovedState] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>] [<CommonParameters>]
```

### ListDeletedManagedHsms
```
Get-AzKeyVaultManagedHsm [-InRemovedState] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzKeyVaultManagedHsm** mendapatkan informasi tentang HSM terkelola dalam langganan. Anda dapat melihat semua instans HSM terkelola dalam langganan, atau memfilter hasil Anda menurut grup sumber daya atau HSM terkelola tertentu.
Perhatikan bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini ketika Anda mendapatkan satu HSM terkelola, Anda harus melakukannya untuk performa yang lebih baik.

## EXAMPLES

### Contoh 1: Dapatkan semua HSM terkelola di langganan Anda saat ini
```powershell
Get-AzKeyVaultManagedHsm
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan semua HSM terkelola di langganan Anda saat ini.

### Contoh 2: Mendapatkan HSM terkelola tertentu
```powershell
Get-AzKeyVaultManagedHsm -Name 'myhsm'
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan HSM terkelola bernama myhsm di langganan Anda saat ini.

### Contoh 3: Mendapatkan HSM terkelola dalam grup sumber daya
```powershell
Get-AzKeyVaultManagedHsm -ResourceGroupName 'myrg1'
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan semua HSM terkelola dalam grup sumber daya bernama myrg1.

### Contoh 4: Dapatkan HSM terkelola menggunakan pemfilteran
```powershell
Get-AzKeyVaultManagedHsm -Name 'myhsm*'
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan semua HSM terkelola dalam langganan yang dimulai dengan "myhsm".

### Contoh 5: Mencantumkan HSM terkelola yang dihapus
```powershell
PS C:\> Get-AzKeyVaultManagedHsm -InRemovedState
```
```output
Name                     Location      DeletionDate           ScheduledPurgeDate    Purge Protection Enabled?
----                     --------      ------------           ------------------    -------------------------
xxxxxxxx-mhsm-4op2n2g4xe eastus2       12/30/2021 2:29:00 AM  3/30/2022 2:29:00 AM  True
xxxxxxx-mhsm-ertopo7tnxa westus        12/29/2021 11:48:42 PM 3/29/2022 11:48:42 PM True
xxxxxxx-mhsm-gg66fgctz67 westus        12/29/2021 11:48:42 PM 3/29/2022 11:48:42 PM False
xxxxxxx-mhsm-2m5jiop6mfo westcentralus 12/30/2021 12:26:14 AM 3/30/2022 12:26:14 AM True
```

Perintah ini mendapatkan semua HSM terkelola yang dihapus dalam langganan saat ini.

## PARAMETERS

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

### -InRemovedState
Menentukan apakah akan menampilkan kumpulan HSM terkelola yang dihapus sebelumnya dalam output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetDeletedManagedHsm, ListDeletedManagedHsms
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi kumpulan HSM terkelola yang dihapus.

```yaml
Type: System.String
Parameter Sets: GetDeletedManagedHsm
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama HSM. Cmdlet membangun FQDN HSM berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: GetManagedHsm
Aliases: HsmName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

```yaml
Type: System.String
Parameter Sets: GetDeletedManagedHsm
Aliases: HsmName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang terkait dengan HSM terkelola yang sedang dikueri.

```yaml
Type: System.String
Parameter Sets: GetManagedHsm
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Menentukan kunci dan nilai opsional tag yang ditentukan untuk memfilter daftar HSM terkelola.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedManagedHsm

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultIdentityItem

## NOTES

## RELATED LINKS

[New-AzKeyVaultManagedHsm](./New-AzKeyVaultManagedHsm.md)

[Remove-AzKeyVaultManagedHsm](./Remove-AzKeyVaultManagedHsm.md)

[Update-AzKeyVaultManagedHsm](./Update-AzKeyVaultManagedHsm.md)
