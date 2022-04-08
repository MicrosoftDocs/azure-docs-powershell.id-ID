---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxKeyEncryptionKeyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
ms.openlocfilehash: 3a5a70b32af2f1e0d73fb71bc4730e96ed9a0432
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140544802"
---
# New-AzDataBoxKeyEncryptionKeyObject

## SYNOPSIS
Buat objek dalam memori untuk KeyEncryptionKey.

## SYNTAX

```
New-AzDataBoxKeyEncryptionKeyObject -KekType <KekType> [-IdentityProperty <IIdentityProperties>]
 [-KekUrl <String>] [-KekVaultResourceId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk KeyEncryptionKey.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk KeyEncryptionKey 
```powershell
$keyEncryptionDetails = New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "UserAssigned"; UserAssignedResourceId = "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"
$keyEncryptionDetails
```

```output
KekType         KekUrl                                           KekVaultResourceId
-------         ------                                           ------------------
CustomerManaged keyIdentifier /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName
```

Membuat objek dalam memori untuk KeyEncryptionKey

## PARAMETERS

### -IdentityProperty
Properti identitas terkelola digunakan untuk enkripsi kunci.
Untuk membuat, lihat bagian CATATAN untuk properti IDENTITYPROPERTY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IIdentityProperties
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KekType
Tipe kunci enkripsi yang digunakan untuk enkripsi kunci.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.KekType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KekUrl
Kunci enkripsi kunci.
It is required in case of Customer managed KekType.

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

### -KekVaultResourceId
Id sumber daya penyimpanan kek. It is required in case of Customer managed KekType.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.KeyEncryptionKey

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


IDENTITYPROPERTY <IIdentityProperties>: Properti identitas terkelola digunakan untuk enkripsi kunci.
  - `[Type <String>]`: Tipe identitas layanan terkelola.
  - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna untuk digunakan untuk mengambil token MSI.

## RELATED LINKS

