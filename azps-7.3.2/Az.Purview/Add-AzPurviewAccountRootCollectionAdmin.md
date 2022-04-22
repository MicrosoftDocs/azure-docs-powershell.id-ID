---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/add-azpurviewaccountrootcollectionadmin
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Add-AzPurviewAccountRootCollectionAdmin.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Add-AzPurviewAccountRootCollectionAdmin.md
ms.openlocfilehash: 4af179ae907ee170336bae9f660f17f973e74998
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143011583"
---
# Add-AzPurviewAccountRootCollectionAdmin

## SYNOPSIS
Tambahkan administrator untuk kumpulan akar yang terkait dengan akun ini.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.purview/add-azpurviewaccountrootcollectionadmin) untuk informasi terbaru.

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

### Contoh 1: Tambahkan administrator untuk kumpulan akar
```powershell
PS C:\> Add-AzPurviewAccountRootCollectionAdmin -AccountName test-pa -ResourceGroupName test-rg -ObjectId xxxxxxxx-5be9-4f43-abd2-04561777c8b0

```

Tambahkan administrator untuk kumpulan akar yang terkait dengan akun bernama 'test-pa'.

### Contoh 2: Tambahkan administrator untuk kumpulan akar oleh InputObject
```powershell
PS C:\>  $got = Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg
PS C:\>  Add-AzPurviewAccountRootCollectionAdmin -InputObject $got -ObjectId xxxxxxxx-5be9-4f43-abd2-04561777c8b0
```

Tambahkan administrator untuk kumpulan akar yang terkait dengan akun bernama 'test-pa' oleh InputObject.

## PARAMETERS

### -AccountName
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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Mengembalikan true ketika perintah berhasil

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

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IPurviewIdentity>: Parameter Identitas
  - `[AccountName <String>]`: Nama akun.
  - `[GroupId <String>]`: Pengidentifikasi grup.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan

## RELATED LINKS

