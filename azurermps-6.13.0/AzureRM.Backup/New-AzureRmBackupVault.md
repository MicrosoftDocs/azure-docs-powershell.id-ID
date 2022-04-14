---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 015E3BC9-C535-4EA2-8A30-C728385DBFF8
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/new-azurermbackupvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupVault.md
ms.openlocfilehash: ad3619d2d0fcb9b60639a19b0c7d3fea45833857
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141844921"
---
# New-AzureRmBackupVault

## SYNOPSIS
Membuat kubah Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmBackupVault [-ResourceGroupName] <String> [-Name] <String> [-Region] <String>
 [[-Storage] <AzureBackupVaultStorageType>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmBackupVault** membuat kubah Azure Backup.
Cmdlet ini mengembalikan objek **AzureRmBackupVault** yang bertindak sebagai referensi ke entitas kubah.

## EXAMPLES

### Contoh 1: Membuat kubah cadangan
```
PS C:\>New-AzureRmBackupVault -ResourceGroupName "ResourceGroup01" -Name "Vault03" -Region "westus"
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup01/providers/Microsoft.Backup
                    /BackupVault/Vault03
Name              : Vault03
ResourceGroupName : ResourceGroup01
Region            : westus
Storage           : GeoRedundant
```

Perintah ini membuat kubah Azure Backup bernama Vault03.
Kubah berada dalam grup sumber daya bernama ResourceGroup01 di kawasan AS Barat.
Kubah menggunakan tipe penyimpanan GeoRedundant default.

### Contoh 2: Membuat kubah cadangan yang menggunakan penyimpanan lokal yang berlebihan
```
PS C:\>New-AzureRmBackupVault -ResourceGroupName "ResourceGroup02" -Name "Vault03" -Region "westus" -Storage LocallyRedundant
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup02/providers/Microsoft.Backup
                    /BackupVault/Vault03
Name              : Vault03
ResourceGroupName : ResourceGroup02
Region            : westus
Storage           : LocallyRedundant
```

Perintah ini membuat kubah Azure Backup bernama Vault03.
Kubah berada dalam grup sumber daya bernama ResourceGroup02 di kawasan AS Barat.
Kubah menggunakan tipe penyimpanan LocallyRedundant.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Nama
Menentukan nama untuk kubah Azure Backup.
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
Menentukan kawasan Azure tempat kubah cadangan ada.
Untuk skenario pencadangan hibrid, kami menyarankan agar Anda membuat kubah di kawasan yang dekat dengan server lokal untuk mengurangi latensi.
Untuk pencadangan mesin virtual Azure infrastructure as a service (IaaS), kubah menjadi titik penemuan untuk mesin virtual lokal.

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
Menentukan nama grup sumber daya Azure yang sudah ada di mana cmdlet ini membuat kubah Cadangan.
Untuk membuat grup sumber daya, gunakan cmdlet New-AzureRMResourceGroup.
Grup sumber daya dan kubah Azure Backup tidak harus berada di kawasan yang sama.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault

## CATATAN
* Tidak

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Hapus-AzureRmBackupVault](./Remove-AzureRmBackupVault.md)

[Set-AzureRmBackupVault](./Set-AzureRmBackupVault.md)


