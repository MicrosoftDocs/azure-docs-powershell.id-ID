---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 015E3BC9-C535-4EA2-8A30-C728385DBFF8
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupVault.md
ms.openlocfilehash: a6415d941646f335ba7cae4fc2aab39d75000ab0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428607"
---
# New-AzureRmBackupVault

## SYNOPSIS
Membuat vault Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmBackupVault [-ResourceGroupName] <String> [-Name] <String> [-Region] <String>
 [[-Storage] <AzureBackupVaultStorageType>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmBackupVault** membuat vault Azure Backup.
Cmdlet ini mengembalikan **objek AzureRmBackupVault** yang bertindak sebagai referensi untuk entitas vault.

## EXAMPLES

### Contoh 1: Membuat vault cadangan
```
PS C:\>New-AzureRmBackupVault -ResourceGroupName "ResourceGroup01" -Name "Vault03" -Region "westus"
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup01/providers/Microsoft.Backup
                    /BackupVault/Vault03
Name              : Vault03
ResourceGroupName : ResourceGroup01
Region            : westus
Storage           : GeoRedundant
```

Perintah ini akan membuat vault Cadangan Azure bernama Vault03.
Vault berada di grup sumber daya bernama ResourceGroup01 di kawasan Barat AS.
Vault menggunakan tipe penyimpanan default GeoRedundant.

### Contoh 2: Buat vault cadangan yang menggunakan penyimpanan lokal yang berlebihan
```
PS C:\>New-AzureRmBackupVault -ResourceGroupName "ResourceGroup02" -Name "Vault03" -Region "westus" -Storage LocallyRedundant
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup02/providers/Microsoft.Backup
                    /BackupVault/Vault03
Name              : Vault03
ResourceGroupName : ResourceGroup02
Region            : westus
Storage           : LocallyRedundant
```

Perintah ini akan membuat vault Cadangan Azure bernama Vault03.
Vault berada di grup sumber daya bernama ResourceGroup02 di kawasan Barat AS.
Vault menggunakan tipe penyimpanan LocallyRedundant.

## PARAMETERS

### -Nama
Menentukan nama untuk vault Cadangan Azure.
Nama harus unik dalam grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kawasan
Menentukan kawasan Azure tempat vault cadangan tersebut ada.
Untuk skenario pencadangan hibrid, kami menyarankan agar Anda membuat vault di kawasan yang dekat dengan server lokal untuk mengurangi latensi.
Untuk cadangan infrastruktur Azure sebagai mesin virtual layanan (IaaS), vault menjadi titik penemuan untuk mesin virtual lokal.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure yang sudah ada di mana cmdlet ini membuat vault Cadangan.
Untuk membuat grup sumber daya, gunakan New-AzureRMResourceGroup cmdlet.
Grup sumber daya dan vault Cadangan Azure tidak harus berada di kawasan yang sama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage
Menentukan tipe penyimpanan untuk data cadangan.
Nilai yang dapat diterima untuk parameter ini adalah: LocallyRedundant dan GeoRedundant.
Nilai defaultnya adalah GeoRedundant.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureBackupVaultStorageType
Parameter Sets: (All)
Aliases: 
Accepted values: GeoRedundant, LocallyRedundant

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### AzureRmBackupVault

## CATATAN
* Tidak ada

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Remove-AzureRmBackupVault](./Remove-AzureRmBackupVault.md)

[Set-AzureRmBackupVault](./Set-AzureRmBackupVault.md)


