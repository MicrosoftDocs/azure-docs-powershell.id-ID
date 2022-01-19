---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/add-azpurviewaccountrootcollectionadmin
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Add-AzPurviewAccountRootCollectionAdmin.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Add-AzPurviewAccountRootCollectionAdmin.md
ms.openlocfilehash: db10227e2b2a09a8c1a12c4f4a9aed375ff97944
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136162629"
---
# Add-AzPurviewAccountRootCollectionAdmin

## SYNOPSIS
Tambahkan administrator untuk kumpulan akar yang terkait dengan akun ini.

## SYNTAX

### AddExpanded (Default)
```
Add-AzPurviewAccountRootCollectionAdmin -AccountName <String> -ResourceGroupName <String> -ObjectId <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### AddViaIdentityExpanded
```
Add-AzPurviewAccountRootCollectionAdmin -InputObject <IPurviewIdentity> -ObjectId <String>
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Tambahkan administrator untuk kumpulan akar yang terkait dengan akun ini.

## EXAMPLES

### Contoh 1: Add the administrator for root collection
```powershell
PS C:\> Add-AzPurviewAccountRootCollectionAdmin -AccountName test-pa -ResourceGroupName test-rg -ObjectId xxxxxxxx-5be9-4f43-abd2-04561777c8b0

```

Tambahkan administrator untuk kumpulan akar yang terkait dengan akun bernama 'test-pa'.

### Contoh 2: Tambahkan administrator untuk koleksi akar dengan InputObject
```powershell
PS C:\>  $got = Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg
PS C:\>  Add-AzPurviewAccountRootCollectionAdmin -InputObject $got -ObjectId xxxxxxxx-5be9-4f43-abd2-04561777c8b0
```

Tambahkan administrator untuk kumpulan akar yang terkait dengan akun bernama 'test-pa' oleh InputObject.

## PARAMETERS

### -Nama Akun
Nama akun.

```yaml
Type: System.String
Parameter Sets: AddExpanded
Aliases:

Required: True
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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity
Parameter Sets: AddViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Mendapatkan atau mengatur pengidentifikasi objek admin.

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

### -PassThru
Mengembalikan true saat perintah berhasil

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
Parameter Sets: AddExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Pengidentifikasi langganan

```yaml
Type: System.String
Parameter Sets: AddExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IPurviewIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama akun.
  - `[GroupId <String>]`: Pengidentifikasi grup.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan

## RELATED LINKS

