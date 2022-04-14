---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxKeyEncryptionKeyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
ms.openlocfilehash: ab3bebb3232677ab5cb02784ff8fe3dd1df9c009
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141896157"
---
# New-AzDataBoxKeyEncryptionKeyObject

## SYNOPSIS
Buat objek dalam memori untuk KeyEncryptionKey.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databox/new-azdataboxkeyencryptionkeyobject) untuk informasi terbaru.

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
Properti identitas terkelola yang digunakan untuk enkripsi kunci.
Untuk membangun, lihat bagian CATATAN untuk properti IDENTITYPROPERTY dan membuat tabel hash.

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
Diperlukan jika Pelanggan mengelola KekType.

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
Id sumber daya kek vault. Diperlukan jika Pelanggan mengelola KekType.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.KeyEncryptionKey

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


IDENTITYPROPERTY <IIdentityProperties>: Properti identitas terkelola yang digunakan untuk enkripsi kunci.
  - `[Type <String>]`: Jenis identitas layanan terkelola.
  - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna yang akan digunakan untuk mengambil token MSI.

## RELATED LINKS

