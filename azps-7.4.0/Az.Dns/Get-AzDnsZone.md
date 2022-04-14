---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: B831ABE6-348C-4DD6-9295-18D23A1FDF63
online version: https://docs.microsoft.com/powershell/module/az.dns/get-azdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsZone.md
ms.openlocfilehash: ce4345bf091ab83b6007496b63abde662673f47f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837744"
---
# Get-AzDnsZone

## SYNOPSIS
Mendapatkan zona DNS.

## SYNTAX

### Default (Default)
```
Get-AzDnsZone [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Grup Sumber Daya
```
Get-AzDnsZone [-Name <String>] -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDnsZone** mendapatkan zona Domain Name System (DNS) dari grup sumber daya yang ditentukan.
Jika Anda menentukan parameter *Nama* , objek **DnsZone** tunggal akan dikembalikan.
Jika Anda tidak menentukan parameter *Nama* , array yang berisi semua zona dalam grup sumber daya tertentu akan dikembalikan.
Anda bisa menggunakan objek **DnsZone** untuk memperbarui zona, misalnya Anda bisa menambahkan objek **RecordSet** ke dalamnya.

## EXAMPLES

### Contoh 1: Dapatkan zona
```powershell
$Zone = Get-AzDnsZone -ResourceGroupName "MyResourceGroup" -Name "myzone.com"
```

Contoh ini mendapatkan zona DNS bernama myzone.com dari grup sumber daya yang ditentukan, lalu menyimpannya dalam variabel $Zone.

### Contoh 2: Dapatkan semua zona dalam grup sumber daya
```powershell
$Zones = Get-AzDnsZone -ResourceGroupName "MyResourceGroup"
```

Contoh ini mendapatkan semua zona DNS dalam grup sumber daya yang ditentukan, lalu menyimpannya dalam variabel $Zones.

### Contoh 3: Dapatkan semua zona dalam langganan
```powershell
$Zones = Get-AzDnsZone
```

Contoh ini mendapatkan semua zona DNS dalam langganan Azure saat ini, lalu menyimpannya dalam variabel $Zones.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama zona DNS yang akan didapatkan.
Jika Anda tidak menentukan nilai untuk parameter *Nama* , cmdlet ini mendapatkan semua zona DNS dalam grup sumber daya yang ditentukan.
Jika Anda juga menghilangkan parameter *ResourceGroupName* , cmdlet ini akan mendapatkan semua zona DNS dalam langganan Azure saat ini.

```yaml
Type: System.String
Parameter Sets: ResourceGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona DNS untuk didapatkan.
Jika anda tidak menentukan *ResourceGroupName*, maka Anda juga harus menghilangkan parameter *Name* .
Dalam hal ini, cmdlet ini mendapatkan semua zona DNS dalam langganan Azure saat ini.

```yaml
Type: System.String
Parameter Sets: ResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone

## CATATAN

## RELATED LINKS

[New-AzDnsZone](./New-AzDnsZone.md)

[Hapus-AzDnsZone](./Remove-AzDnsZone.md)

[Set-AzDnsZone](./Set-AzDnsZone.md)
