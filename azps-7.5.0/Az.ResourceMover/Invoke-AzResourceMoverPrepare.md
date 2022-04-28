---
external help file: ''
Module Name: Az.ResourceMover
online version: https://docs.microsoft.com/powershell/module/az.resourcemover/invoke-azresourcemoverprepare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Invoke-AzResourceMoverPrepare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Invoke-AzResourceMoverPrepare.md
ms.openlocfilehash: c273163b2851801184a15b795bd3daf5bcab8540
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144111473"
---
# Invoke-AzResourceMoverPrepare

## SYNOPSIS
Memulai persiapan untuk set sumber daya yang disertakan dalam isi permintaan.
Operasi persiapan ada di moveResources yang berada di moveState 'PreparePending' atau 'PrepareFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

## SYNTAX

```
Invoke-AzResourceMoverPrepare -MoveCollectionName <String> -ResourceGroupName <String>
 -MoveResource <String[]> [-SubscriptionId <String>] [-MoveResourceInputType <MoveResourceInputType>]
 [-ValidateOnly] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulai persiapan untuk set sumber daya yang disertakan dalam isi permintaan.
Operasi persiapan ada di moveResources yang berada di moveState 'PreparePending' atau 'PrepareFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

## EXAMPLES

### Contoh 1: Memvalidasi dependek sebelum menyiapkan sumber daya. Dapatkan sumber daya dependen yang diperlukan yang juga perlu disiapkan.
```powershell
$resp = Invoke-AzResourceMoverPrepare -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS"  -MoveResource $('psdemovm') -ValidateOnly

AdditionalInfo : {Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Api20191001Preview.OperationErrorAdditionalInfo}
Code           : MoveCollectionMissingRequiredDependentResources
Detail         : {}
EndTime        : 2/9/2021 9:04:15 AM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RegionMoveRG-centralus-westcentralus/providers/Microsoft.Migr
                 ate/MoveCollections/PS-centralus-westcentralus-demoRMS/12d055bd-ac52-427f-8b05-b4b21c4b51e8
Message        : The operation has failed as required move resources are missing from the input.
                     Possible Causes: Dependent resources are missing from the input.
                     Recommended Action: Retry the operation with all required resources, if the issue persist contact support.

Name           : 12d055bd-ac52-427f-8b05-b4b21c4b51e8
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/9/2021 9:04:14 AM
Status         : Failed

$resp.Code
MoveCollectionMissingRequiredDependentResources

$resp.AdditionalInfo[0].InfoMoveResource

SourceId                                                                                                                                  
--------                                                                                                                                  
/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourcegroups/psdemorm/providers/microsoft.network/networkinterfaces/psdemovm111     
/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/psdemorm/providers/Microsoft.Network/virtualNetworks/psdemorm-vnet     
/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourcegroups/psdemorm/providers/microsoft.network/networksecuritygroups/psdemovm-nsg

```

Validasi dependek sebelum menyiapkan sumber daya.
Dapatkan sumber daya dependen yang diperlukan yang juga perlu disiapkan.

### Contoh 2: Memulai persiapan untuk kumpulan sumber daya dalam Kumpulan Pemindahan menggunakan "Nama MoveResource" sebagai input.
```powershell
Invoke-AzResourceMoverPrepare -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS"  -MoveResource $('PSDemoVM','psdemovm111', 'PSDemoRM-vnet','PSDemoVM-nsg')
```

```output
AAdditionalInfo : 
Code           : 
Detail         : 
EndTime        : 2/9/2021 11:25:13 AM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RG-MoveCollection-demoRMS/providers/Microsoft.Migrate/moveCollections/PS-centralus-westcentralus-demoRMS/operations/49e4429
                 4-24ac-4eac-93da-e7e1c815554d
Message        : 
Name           : 49e44294-24ac-4eac-93da-e7e1c815554d
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/9/2021 10:55:53 AM
Status         : Succeeded
```

Mulai persiapan untuk kumpulan sumber daya dalam Kumpulan Pemindahan menggunakan "Nama MoveResource" sebagai input.

### Contoh 3: Memulai persiapan untuk kumpulan sumber daya dalam Kumpulan Pemindahan menggunakan "SourceARMID".
```powershell
Invoke-AzResourceMoverPrepare -ResourceGroupName "RG-MoveCollection-demoRMS" -MoveCollectionName "PS-centralus-westcentralus-demoRMS" -MoveResourceInputType MoveResourceSourceId  -MoveResource $('/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/PSDemoRMS/providers/Microsoft.Network/networkSecurityGroups/PSDemoVM-nsg')
```

```output
AdditionalInfo :
Code           :
Detail         :
EndTime        : 2/9/2021 11:09:30 AM
Id             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/RG-MoveCollection-demoRMS/providers/Microsoft.Migrate/MoveColl
                 ections/PS-centralus-westcentralus-demoRMS/operations/c7b13d43-a6fe-48e3-bb8c-3ad9e6ba3355
Message        :
Name           : c7b13d43-a6fe-48e3-bb8c-3ad9e6ba3355
Property       : Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Any
StartTime      : 2/9/2021 11:05:27 AM
Status         : Succeeded

```

Mulai persiapan untuk set sumber daya dalam Kumpulan Pemindahan menggunakan "SourceARMID".

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Nama Kumpulan Pemindahan.

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
Mendapatkan atau mengatur daftar ID sumber daya, secara default menerima id sumber daya pemindahan kecuali jenis input dialihkan melalui properti moveResourceInputType.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MoveResourceInputType
Menentukan jenis input sumber daya pemindahan.

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
Nama Grup Sumber Daya.

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
Mendapatkan atau menetapkan nilai yang menunjukkan apakah operasi hanya perlu menjalankan prasyarat.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Api20210801.IOperationStatus

## NOTES

ALIAS

## RELATED LINKS

