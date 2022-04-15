---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
ms.assetid: 2EA28B90-4BAE-45DF-BD2E-60C74F53FB7B
online version: https://docs.microsoft.com/powershell/module/az.logicapp/get-azlogicapprunaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Get-AzLogicAppRunAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Get-AzLogicAppRunAction.md
ms.openlocfilehash: 5cf666c12d87908efcb6f6f0753810488c87a3f1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142168399"
---
# Get-AzLogicAppRunAction

## SYNOPSIS

Mendapatkan tindakan dari aplikasi logika yang dijalankan.

## SYNTAX

```powershell
Get-AzLogicAppRunAction -ResourceGroupName <String> -Name <String> -RunName <String> [-ActionName <String>]
 [-FollowNextPageLink] [-MaximumFollowNextPageLink <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzLogicAppRunAction** mendapatkan tindakan dari aplikasi logika yang dijalankan.
Cmdlet ini mengembalikan objek **WorkflowRunAction** .
Tentukan aplikasi logika, grup sumber daya, dan jalankan.
Modul ini mendukung parameter dinamis.
Untuk menggunakan parameter dinamis, ketikkan dalam perintah.
Untuk menemukan nama parameter dinamis, ketik tanda hubung (-) setelah nama cmdlet, lalu tekan tombol Tab berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda menghilangkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.

## EXAMPLES

### Contoh 1: Mendapatkan tindakan dari menjalankan Aplikasi Logika

```powershell
Get-AzLogicAppRunAction -ResourceGroupName "ResourceGroup11" -Name "LogicApp05" -RunName "08585925184423369718380498702CU26" -ActionName "LogicAppAction01"
```

```output
Code        : NotFound
EndTime     : 1/13/2016 2:42:56 PM
Error       : 
InputsLink  : Microsoft.Azure.Management.Logic.Models.ContentLink
Name        : LogicAppAction01
OutputsLink : Microsoft.Azure.Management.Logic.Models.ContentLink
StartTime   : 1/13/2016 2:42:55 PM
Status      : Failed
TrackingId  : 
Type        :
```

Perintah ini mendapatkan tindakan Aplikasi Logika tertentu dari aplikasi logika bernama LogicApp05 untuk dijalankan dengan pengidentifikasi 08585925184423369718380498702CU26.

### Contoh 2: Dapatkan semua tindakan dari aplikasi logika yang dijalankan

```powershell
Get-AzLogicAppRunAction -ResourceGroupName "ResourceGroup11" -Name "LogicApp05" -RunName "08585925184423369718380498702CU26" -FollowNextPageLink
```

Perintah ini mendapatkan semua tindakan Aplikasi Logika dari run dengan pengidentifikasi 08585925184423369718380498702CU26 dari aplikasi logika bernama LogicApp05.

## PARAMETERS

### -ActionName

Menentukan nama tindakan dalam aplikasi logika yang dijalankan.
Cmdlet ini mendapatkan tindakan yang ditentukan parameter ini.

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

### -FollowNextPageLink

Menunjukkan cmdlet harus mengikuti tautan halaman berikutnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumFollowNextPageLink

Menentukan berapa kali untuk mengikuti tautan halaman berikutnya jika FollowNextPageLink digunakan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama

Menentukan nama aplikasi logika di mana cmdlet ini mendapatkan tindakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName

Menentukan nama grup sumber daya tempat cmdlet ini mendapatkan tindakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunName

Menentukan nama aplikasi logika yang dijalankan.
Cmdlet ini mendapatkan tindakan untuk menjalankan yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.WorkflowRunAction

## CATATAN

## RELATED LINKS

[Get-AzLogicAppRunHistory](./Get-AzLogicAppRunHistory.md)

[Stop-AzLogicAppRun](./Stop-AzLogicAppRun.md)
