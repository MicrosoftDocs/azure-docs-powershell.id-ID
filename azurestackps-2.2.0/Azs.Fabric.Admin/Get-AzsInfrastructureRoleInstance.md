---
external help file: ''
Module Name: Azs.Fabric.Admin
online version: https://docs.microsoft.com/powershell/module/azs.fabric.admin/get-azsinfrastructureroleinstance
schema: 2.0.0
ms.openlocfilehash: 145c839be9e5e79017f71e940554285d02f88797
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136580031"
---
# Get-AzsInfrastructureRoleInstance

## SYNOPSIS
Mengembalikan instans peran infrastruktur yang diminta.

## SYNTAX

### Daftar (Default)
```
Get-AzsInfrastructureRoleInstance [-Location <String>] [-ResourceGroupName <String>]
 [-SubscriptionId <String[]>] [-Filter <String>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsInfrastructureRoleInstance -Name <String> [-Location <String>] [-ResourceGroupName <String>]
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsInfrastructureRoleInstance -INPUTOBJECT \<IFabricAdminIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan instans peran infrastruktur yang diminta.

## EXAMPLES

### Contoh 1:
```powershell
PS C:\> Get-AzsInfrastructureRoleInstance

A list of all infrastructure role instances.
```

Mengembalikan daftar semua instans peran infrastruktur.

### Contoh 2:
```powershell
PS C:\> Get-AzsInfrastructureRoleInstance -Name "AzS-ACS01"

A single infrastructure role instance based on name.
```

Kembalikan satu contoh peran infrastruktur tunggal berdasarkan nama.

## PARAMETERS

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

### -Filter
Parameter filter OData.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.FabricAdmin.Models.IFabricAdminIdentity
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
Nama instans peran infrastruktur.

```yaml
Type: System.String
Parameter Sets: Get
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
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: -join("System.",(Get-AzLocation)[0].Location)
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure Anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.FabricAdmin.Models.IFabricAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.FabricAdmin.Models.Api20160501.IInfraRoleInstance



## CATATAN

PROPERTI PARAMETER KOMPLEKS Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.

INPUTOBJECT \<IFabricAdminIdentity> : Parameter Identitas
  - `[Drive <String>]`: Nama drive penyimpanan.
  - `[EdgeGateway <String>]`: Nama gateway tepi.
  - `[EdgeGatewayPool <String>]`: Nama gateway pool tepi.
  - `[FabricLocation <String>]`: Fabric location.
  - `[FileShare <String>]`: Fabric file share name.
  - `[IPPool <String>]`: NAMA ip pool.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InfraRole <String>]`: Nama peran infrastruktur.
  - `[InfraRoleInstance <String>]`: Nama instans peran infrastruktur.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[LogicalNetwork <String>]`: Nama jaringan logis.
  - `[LogicalSubnet <String>]`: Nama subnet logika.
  - `[MacAddressPool <String>]`: Nama grup alamat MAC.
  - `[Operation <String>]`: Pengidentifikasi operasi.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ScaleUnit <String>]`: Nama unit skala.
  - `[ScaleUnitNode <String>]`: Nama node unit skala.
  - `[SlbMuxInstance <String>]`: Nama instans MUX SLB.
  - `[StoragePool <String>]`: Storage pool.
  - `[StorageSubSystem <String>]`: Nama sistem penyimpanan.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[Volume <String>]`: Nama volume penyimpanan.

## RELATED LINKS

