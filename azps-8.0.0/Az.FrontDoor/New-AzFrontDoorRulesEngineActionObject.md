---
external help file: Microsoft.Azure.PowerShell.Cmdlets.FrontDoor.dll-Help.xml
Module Name: Az.FrontDoor
online version: https://docs.microsoft.com/powershell/module/az.frontdoor/new-azfrontdoorrulesengineactionobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/New-AzFrontDoorRulesEngineActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/New-AzFrontDoorRulesEngineActionObject.md
ms.openlocfilehash: 88f041d3498cd3a0b45f0a4f24e3aaac730f5ef3
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145532513"
---
# New-AzFrontDoorRulesEngineActionObject

## SYNOPSIS
Buat objek PSRulesEngineAction untuk membuat aturan mesin aturan.

## SYNTAX

### ByFieldsWithRegularActionParameterSet (Default)
```
New-AzFrontDoorRulesEngineActionObject
 [-RequestHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-ResponseHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFieldsWithForwardingParameterSet
```
New-AzFrontDoorRulesEngineActionObject
 [-RequestHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-ResponseHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-CustomForwardingPath <String>] [-ForwardingProtocol <String>] -ResourceGroupName <String>
 -FrontDoorName <String> -BackendPoolName <String> [-EnableCaching <Boolean>]
 [-QueryParameterStripDirective <String>] [-DynamicCompression <PSEnabledState>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFieldsWithRedirectParameterSet
```
New-AzFrontDoorRulesEngineActionObject
 [-RequestHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-ResponseHeaderAction <System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]>]
 [-RedirectType <String>] [-RedirectProtocol <String>] [-CustomHost <String>] [-CustomPath <String>]
 [-CustomFragment <String>] [-CustomQueryString <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek PSRulesEngineAction untuk membuat aturan mesin aturan. 

Gunakan cmdlet "New-AzFrontDoorHeaderActionObject" untuk membuat PSHeaderObjects untuk meneruskan ke parameter "-RequestHeaderActions" dan "-ResponseHeaderActions".

## EXAMPLES

### Contoh 1
```powershell
$headerActions = New-AzFrontDoorHeaderActionObject -HeaderActionType "Append" -HeaderName "X-Content-Type-Options" -Value "nosniff"
$headerActions

HeaderName             HeaderActionType Value
----------             ---------------- -----
X-Content-Type-Options           Append nosniff

$rulesEngineAction = New-AzFrontDoorRulesEngineActionObject -ResponseHeaderAction $headerActions
$rulesEngineAction

RequestHeaderActions ResponseHeaderActions    RouteConfigurationOverride
-------------------- ---------------------    --------------------------
{}                   {X-Content-Type-Options}

```

Buat tindakan mesin aturan yang menambahkan nilai header respons dan menunjukkan cara melihat properti tindakan mesin aturan yang dibuat.

### Contoh 2
```powershell
$rulesEngineAction = New-AzFrontDoorRulesEngineActionObject -RequestHeaderAction $headerActions -ForwardingProtocol HttpsOnly -BackendPoolName mybackendpool -ResourceGroupName Jessicl-Test-RG -FrontDoorName jessicl-test-myappfrontend -QueryParameterStripDirective StripNone -DynamicCompression Disabled -EnableCaching $true
$rulesEngineAction

RequestHeaderAction            ResponseHeaderAction RouteConfigurationOverride
-------------------            -------------------- --------------------------
{headeraction1, headeraction2} {}                   Microsoft.Azure.Commands.FrontDoor.Models.PSForwardingConfiguration

$rulesEngineAction.RequestHeaderAction

HeaderName    HeaderActionType Value
----------    ---------------- -----
headeraction1        Overwrite
headeraction2           Append

$rulesEngineAction.ResponseHeaderAction
$rulesEngineAction.RouteConfigurationOverride

CustomForwardingPath         :
ForwardingProtocol           : HttpsOnly
BackendPoolId                : /subscriptions/47f4bc68-6fe4-43a2-be8b-dfd0e290efa2/resourceGroups/myresourcegroup/provi
                               ders/Microsoft.Network/frontDoors/myfrontdoor/BackendPools/mybackendpool
QueryParameterStripDirective : StripNone
DynamicCompression           : Disabled
EnableCaching                : True
```

Buat tindakan mesin aturan yang meneruskan permintaan ke kumpulan backend speicific dan tunjukkan cara melihat properti tindakan mesin aturan yang dibuat.

### Contoh: 3
```powershell
$rulesEngineAction = New-AzFrontDoorRulesEngineActionObject -RedirectType Moved -RedirectProtocol MatchRequest -CustomHost www.contoso.com
$rulesEngineAction

RequestHeaderActions ResponseHeaderActions RouteConfigurationOverride
-------------------- --------------------- --------------------------
{}                   {}                    Microsoft.Azure.Commands.FrontDoor.Models.PSRedirectConfiguration

$rulesEngineAction.RouteConfigurationOverride

RedirectType      : Moved
RedirectProtocol  : MatchRequest
CustomHost        : www.contoso.com
CustomPath        :
CustomFragment    :
CustomQueryString :

```

Buat tindakan mesin aturan yang mengalihkan permintaan ke host lain dan tunjukkan cara melihat properti tindakan mesin aturan yang dibuat.


## PARAMETERS

### -BackendPoolName
Nama BackendPool tempat aturan ini dirutekan

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomForwardingPath
Jalur kustom yang digunakan untuk menulis ulang jalur sumber daya yang cocok dengan aturan ini.
Biarkan kosong untuk menggunakan jalur masuk.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomFragment
Fragmen untuk ditambahkan ke URL pengalihan.
Fragmen adalah bagian dari URL yang muncul setelah #.
Jangan sertakan #.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomHost
Host untuk dialihkan.
Biarkan kosong untuk menggunakan host masuk sebagai host tujuan.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomPath
Jalur lengkap untuk mengalihkan.
Jalur tidak boleh kosong dan harus dimulai dengan /.
Biarkan kosong untuk menggunakan jalur masuk sebagai jalur tujuan.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomQueryString
Kumpulan string kueri yang akan ditempatkan di URL pengalihan.
Mengatur nilai ini akan menggantikan string kueri yang ada; biarkan kosong untuk mempertahankan string kueri masuk.
String kueri harus dalam \<key\>=\<value\> format.
Yang pertama?
dan & akan ditambahkan secara otomatis sehingga jangan sertakan di depan, tetapi lakukan beberapa string kueri terpisah dengan &.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicCompression
Apakah akan mengaktifkan pemadatan dinamis untuk konten yang di-cache.
Nilai default diaktifkan

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSEnabledState
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCaching
Apakah akan mengaktifkan penembolokan untuk rute ini.
Nilai defaultnya adalah false

```yaml
Type: System.Boolean
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardingProtocol
Protokol yang akan digunakan aturan ini saat meneruskan lalu lintas ke backend.
Nilai defaultnya adalah MatchRequest

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontDoorName
Nama Front Door tempat aturan perutean ini berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryParameterStripDirective
Perlakuan istilah kueri URL saat membentuk kunci cache.
Nilai defaultnya adalah StripAll

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectProtocol
Protokol tujuan ke tempat lalu lintas dialihkan.
Nilai defaultnya adalah MatchRequest

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectType
Jenis pengalihan yang akan digunakan aturan saat mengalihkan lalu lintas.
Nilai Default Dipindahkan

```yaml
Type: System.String
Parameter Sets: ByFieldsWithRedirectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestHeaderAction
Daftar tindakan header yang akan diterapkan dari permintaan dari AFD ke asal.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat RoutingRule akan dibuat.

```yaml
Type: System.String
Parameter Sets: ByFieldsWithForwardingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseHeaderAction
Daftar tindakan header yang akan diterapkan dari respons dari AFD ke klien.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.FrontDoor.Models.PSHeaderAction]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.FrontDoor.Models.PSRulesEngineAction

## NOTES

## RELATED LINKS
