---
external help file: ''
Module Name: Az.ResourceMover
online version: https://docs.microsoft.com/powershell/module/az.resourcemover/invoke-azresourcemoverbulkremove
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Invoke-AzResourceMoverBulkRemove.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Invoke-AzResourceMoverBulkRemove.md
ms.openlocfilehash: 3aab231a9739c97af5a1eb49f00d6d93c25bad75
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142224757"
---
# Invoke-AzResourceMoverBulkRemove

## SYNOPSIS
Menghapus kumpulan sumber daya pemindahan yang disertakan dalam isi permintaan dari pemindahan koleksi.
Orkestrasi dilakukan melalui layanan.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resourcemover/invoke-azresourcemoverbulkremove) untuk informasi terbaru.

## SYNTAX

```
Invoke-AzResourceMoverBulkRemove -MoveCollectionName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-MoveResource <String[]>] [-MoveResourceInputType <MoveResourceInputType>]
 [-ValidateOnly] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus kumpulan sumber daya pemindahan yang disertakan dalam isi permintaan dari pemindahan koleksi.
Orkestrasi dilakukan melalui layanan.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

## EXAMPLES

### Contoh 1: Memvalidasi depende sebelum menghapus Pindahkan Sumber Daya dari Pindahkan Koleksi
```powershell
PS C:\> Invoke-AzResourceMoverBulkRemove -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS"  -MoveResource $('PSDemoVM') -MoveResourceInputType "MoveResourceId" -ValidateOnly

AdditionalInfo : 
Code           : 
Detail         : 
EndTime        : 2/10/2021 12:52:28 PM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RG-MoveCollection-demoRMS/providers/Microsoft.Migrate/moveCollections/PS-centralus-westcentralu
                 s-demoRMS/operations/b4e3f140-b36b-4fd5-a507-b1e663ecf7a3
Message        : 
Name           : b4e3f140-b36b-4fd5-a507-b1e663ecf7a3
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/10/2021 12:52:28 PM
Status         : Succeeded

```

Validasikan dependeies sebelum menghapus pemindahan sumber daya dari Pindahkan Koleksi.

### Contoh 2: Hapus Pindahkan Sumber Daya dari Pindahkan Koleksi menggunakan "Nama MoveResource" sebagai input
```powershell
Invoke-AzResourceMoverBulkRemove -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS"  -MoveResource $('PSDemoVM') -MoveResourceInputType "MoveResourceId"

AdditionalInfo : 
Code           : 
Detail         : 
EndTime        : 2/10/2021 12:58:10 PM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RG-MoveCollection-demoRMS/providers/Microsoft.Migrate/moveCollections/PS-centralus-westcentralu
                 s-demoRMS/operations/d4827071-b797-45c5-b88c-00ddd7818d42
Message        : 
Name           : d4827071-b797-45c5-b88c-00ddd7818d42
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/10/2021 12:57:08 PM
Status         : Succeeded
```

Hapus Pindahkan Sumber Daya dari Pindahkan Koleksi menggunakan "Nama MoveResource" sebagai input

### Contoh 3: Hapus Pindahkan Sumber Daya dari Pindahkan Koleksi menggunakan "SourceARMID" sebagai input
```powershell
Invoke-AzResourceMoverBulkRemove -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS"  -MoveResource $('/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/PSDemoRM/providers/Microsoft.Network/networkSecurityGroups/PSDemoVM-nsg') -MoveResourceInputType "MoveResourceSourceId"

AdditionalInfo : 
Code           : 
Detail         : 
EndTime        : 2/10/2021 1:05:13 PM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RG-MoveCollection-demoRMS/providers/Microsoft.Migrate/moveCollections/PS-centralus-westcentralu
                 s-demoRMS/operations/7b6904e2-fc3f-400d-b248-8908fcb282fb
Message        : 
Name           : 7b6904e2-fc3f-400d-b248-8908fcb282fb
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/10/2021 1:05:00 PM
Status         : Succeeded
```

Hapus Pindahkan Sumber Daya dari Pindahkan Koleksi menggunakan "SourceARMID" sebagai input

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

### -MoveCollectionName
.

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

### -MoveResource
Mendapatkan atau mengatur daftar id sumber daya, secara default id sumber daya menerima id sumber daya pindah kecuali tipe input dialihkan melalui properti moveResourceInputType.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MoveResourceInputType
Menentukan tipe input pemindahan sumber daya.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Support.MoveResourceInputType
Parameter Sets: (All)
Aliases:

Required: False
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

### -ResourceGroupName
.

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

### -SubscriptionId
ID Langganan.

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

### -ValidateOnly
Mendapatkan atau mengatur nilai yang mengindikasikan apakah operasi hanya perlu menjalankan prasyarat.

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

### Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Api202101.IOperationStatus

## CATATAN

ALIAS

## RELATED LINKS

