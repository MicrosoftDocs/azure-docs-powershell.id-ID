---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultmanagedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedHsm.md
ms.openlocfilehash: 0ace1f51bc8bb5c8fe95d7abe079f89898707360
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143285309"
---
# Get-AzKeyVaultManagedHsm

## SYNOPSIS
Dapatkan HSM terkelola.

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
Cmdlet **Get-AzKeyVaultManagedHsm** mendapatkan informasi tentang HSM yang dikelola dalam langganan. Anda dapat menampilkan semua instans HSM terkelola dalam langganan, atau memfilter hasil menurut grup sumber daya atau HSM terkelola tertentu.
Perhatikan bahwa meskipun menentukan grup sumber daya opsional untuk cmdlet ini ketika Anda mendapatkan HSM terkelola tunggal, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Dapatkan semua HSM terkelola dalam langganan Anda saat ini
```powershell
Get-AzKeyVaultManagedHsm
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan semua HSM terkelola dalam langganan Anda saat ini.

### Contoh 2: Dapatkan HSM terkelola tertentu
```powershell
Get-AzKeyVaultManagedHsm -Name 'myhsm'
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

Perintah ini mendapatkan HSM terkelola bernama myhsm dalam langganan Anda saat ini.

### Contoh 3: Dapatkan HSM terkelola dalam grup sumber daya
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

### Contoh 5: Daftar HSM terkelola yang dihapus
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
Menentukan apakah akan memperlihatkan kumpulan HSM terkelola yang dihapus sebelumnya dalam output.

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
Lokasi kumpulan HSM yang dikelola yang dihapus.

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

### -Nama
Nama HSM. Cmdlet menyusun FQDN HSM berdasarkan nama dan lingkungan yang saat ini dipilih.

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
Menentukan nama grup sumber daya yang terkait dengan HSM yang dikelola yang sedang dikueri.

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
Mengesampingkan langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak mempengaruhi cmdlet berikutnya.

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
Menentukan kunci dan nilai opsional tag yang ditentukan untuk memfilter daftar HSM yang dikelola.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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