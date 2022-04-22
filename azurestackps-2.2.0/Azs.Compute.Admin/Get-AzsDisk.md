---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/get-azsdisk
schema: 2.0.0
ms.openlocfilehash: 8acbee92371a00facd2463896d44c4bf4b3825ee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142912079"
---
# Get-AzsDisk

## SYNOPSIS
Mengembalikan disk.

## SYNTAX

### Daftar (Default)
```
Get-AzsDisk [-Location <String>] [-SubscriptionId <String[]>] [-Count \<Int32>] [-ScaleUnit <String>]
 [-SharePath <String>] [-Start \<Int32>] [-Status <String>] [-UserSubscriptionId <String>]
 [-VolumeLabel <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsDisk -Name <String> [-Location <String>] [-SubscriptionId <String[]>] [-ShowSizeDetail]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsDisk -INPUTOBJECT \<IComputeAdminIdentity> [-ShowSizeDetail] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan disk.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
Get-AzsDisk
```



### -------------------------- CONTOH 2 --------------------------
```powershell
Get-AzsDisk -Name "426b8945-8a24-42ad-acdc-c26f16202489"
```

ActualSizeGb : 24 DiskId : 426b8945-8a24-42ad-acdc-c26f16202489 DiskSku : Premium_LRS Disk Tipe : Id Disk : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north west/disks/426b8945-8a24-42ad-acdc-c26f16202489 Lokasi : northwest ManagedBy : Name : northwest/426b8945-8a24-42ad-acdc-c26f16202489 ProvisionSizeGb : 127 SharePath : \\ SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_3 Status : Tipe Tidak Tertaut : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/LADTEST/providers/Microsoft.Comput e/Disks/TEST_OsDisk_1_426b89458a2442adacdcc26f16202489

### -------------------------- CONTOH 3 --------------------------
```powershell
Get-AzsDisk -Count 3
```

ActualSizeGb : 24 DiskId : 20f1619e-4210-47f6-81e6-b89e3028df06 DiskSku : Premium_LRS Disk Tipe : Id Disk : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north west/disks/20f1619e-4210-47f6-81e6-b89e3028df06 Lokasi : northwest ManagedBy : Name : northwest/20f1619e-4210-47f6-81e6-b89e3028df06 ProvisionSizeGb : 127 SharePath : \\ SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_4 Status : Tipe Tidak Tertaut : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/RG1/providers/Microsoft.Compute/Di sks/TEST_OsDisk_1_20f1619e421047f681e6b89e3028df06

ActualSizeGb : 24 DiskId : 38a767e4-4ceb-49fb-a53c-48de9b08aaae DiskSku : Standard_LRS DiskTyPe : Disk Id : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.compute Admin/locations/north west/disks/38a767e4-4ceb-49fb-a53c-48de9b08aae Lokasi : northwest ManagedBy : Name : northwest/38a767e4-4ceb-49fb-a53c-48de9b08aaae ProvisionSizeGb : 127 SharePath : \\ SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_4 Status : Tipe Tidak Tertaut : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/SCTE/providers/Microsoft.Compute/D isks/SCTETest_OsDisk_1_38a767e44ceb49fba53c48de9b08aaae

ActualSizeGb : 24 DiskId : 426b8945-8a24-42ad-acdc-c26f16202489 DiskSku : Premium_LRS Disk Tipe : Id Disk : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north west/disks/426b8945-8a24-42ad-acdc-c26f16202489 Lokasi : northwest ManagedBy : Name : northwest/426b8945-8a24-42ad-acdc-c26f16202489 ProvisionSizeGb : 127 SharePath : \\ SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_3 Status : Tipe Tidak Tertaut : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/LADTEST/providers/Microsoft.Comput e/Disks/TEST_OsDisk_1_426b89458a2442adacdcc26f16202489

### -------------------------- CONTOH 4 --------------------------
```powershell
Get-AzsDisk -Status All -ScaleUnit s-cluster -VolumeLabel Objstore_4
```

ActualSizeGb : 2 DiskId : e4732f76-0753-40ec-80f5-8effdd0b437d DiskSku : Premium_LRS DiskType : Disk Id : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/e4732f76-0753-40ec-80f5-8effdd0b437d Lokasi : redmond ManagedBy : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1 Name :  redmond/e4732f76-0753-40ec-80f5-8effdd0b437d ProvisionSizeGb : 30 SharePath : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4 Status : Tipe Khusus : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/RBACTEST/providers/Microsoft.Compute/Disks/test1_OsDisk_1_e4732f76075340ec80f58effdd0b437d

ActualSizeGb : 1 DiskId : 0485cbc9-1efa-43bd-86c2-0e201d79c528 DiskSku : Premium_LRS DiskType : Disk Id : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/0485cbc9-1efa-43bd-86c2-0e201d79c528 Lokasi : redmond ManagedBy : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1 Name :  redmond/0485cbc9-1efa-43bd-86c2-0e201d79c528 ProvisionSizeGb : 64 SharePath : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4 Status : Tipe Khusus : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/TESTRG1/providers/Microsoft.Compute/Disks/gpsdisk

ActualSizeGb : 1 DiskId : 137893db-e7ce-4907-a488-b35c5e928614 DiskSku : Premium_LRS DiskType : Disk Id : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/137893db-e7ce-4907-a488-b35c5e928614 Lokasi : redmond ManagedBy : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1 Name :  redmond/137893db-e7ce-4907-a488-b35c5e928614 ProvisionSizeGb : 55 SharePath : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4 Status : Tipe Khusus : Microsoft.Compute.Admin/locations/disks UserResourceId : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/RBACTEST/providers/Microsoft.Compute/Disks/testddd

## PARAMETERS

### -Count
Jumlah maksimum diska yang akan dikembalikan.

```yaml
Type: System.Int32
Parameter Sets: List
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Disk memandu sebagai identitas.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DiskId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScaleUnit
Unit skala tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePath
Berbagi tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowSizeDetail
Beralih untuk apakah ringkasan atau informasi ukuran disk mendetail dikembalikan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Get, GetViaIdentity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mulai
Indeks mulai disk dalam kueri.

```yaml
Type: System.Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Parameter status disk.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserSubscriptionId
Id Langganan Pengguna tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeLabel
Label volume volume tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List
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

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20210401.IDisk

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IComputeAdminIdentity>: Parameter Identitas
  - `[DiskId <String>]`: Disk memandu sebagai identitas.
  - `[FeatureName <String>]`: Nama fitur.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya.
  - `[MigrationId <String>]`: Nama panduan pekerjaan migrasi.
  - `[Offer <String>]`: Nama penawaran.
  - `[Publisher <String>]`: Nama penerbit.
  - `[QuotaName <String>]`: Nama kuota.
  - `[ScaleUnitName <String>]`: Nama unit skala.
  - `[Sku <String>]`: Nama SKU.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.
  - `[Type <String>]`: Jenis ekstensi.
  - `[Version <String>]`: Versi sumber daya.

## RELATED LINKS

