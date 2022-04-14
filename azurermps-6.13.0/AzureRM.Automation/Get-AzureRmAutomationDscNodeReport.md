---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
ms.assetid: 1246C3AC-A123-4EA1-B99E-458A85789109
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.automation/get-azurermautomationdscnodereport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationDscNodeReport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationDscNodeReport.md
ms.openlocfilehash: 747ffdb9df955609a38718016af50bb5434c0224
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141845417"
---
# Get-AzureRmAutomationDscNodeReport

## SYNOPSIS
Mendapatkan laporan yang dikirim dari simpul DSC ke Otomatisasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByAll (Default)
```
Get-AzureRmAutomationDscNodeReport -NodeId <Guid> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByLatest
```
Get-AzureRmAutomationDscNodeReport -NodeId <Guid> [-Latest] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ById
```
Get-AzureRmAutomationDscNodeReport -NodeId <Guid> -Id <Guid> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmAutomationDscNodeReport** mendapatkan laporan yang dikirim dari simpul APS Desired State Configuration (DSC) ke Azure Automation.

## EXAMPLES

### Contoh 1: Dapatkan semua laporan untuk simpul DSC
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup14" -AutomationAccountName "Contoso17" -NodeId $Node.Id
```

Perintah pertama mendapatkan simpul DSC untuk komputer bernama Computer14 di akun Otomatisasi bernama Contoso17.
Perintah menyimpan objek ini dalam variabel $Node.
Perintah kedua mendapatkan metadata untuk semua laporan yang dikirim dari simpul DSC bernama Computer14 ke akun Otomatisasi bernama Contoso17.
Perintah menentukan simpul dengan menggunakan properti **Id** dari objek $Node.

### Contoh 2: Mendapatkan laporan untuk simpul DSC menurut ID laporan
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -NodeId $Node.Id -Id c0a1718e-d8be-4fa3-91b6-82e1d3a36298
```

Perintah pertama mendapatkan simpul DSC untuk komputer bernama Computer14 di akun Otomatisasi bernama Contoso17.
Perintah menyimpan objek ini dalam variabel $Node.
Perintah kedua mendapatkan metadata untuk laporan yang diidentifikasi oleh ID tertentu yang dikirim dari simpul DSC bernama Computer14 ke akun Otomatisasi bernama Contoso17.

### Contoh 3: Dapatkan laporan terbaru untuk simpul DSC
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -NodeId $Node.Id -Latest
```

Perintah pertama mendapatkan simpul DSC untuk komputer bernama Computer14 di akun Otomatisasi bernama Contoso17.
Perintah menyimpan objek ini dalam variabel $Node.
Perintah kedua mendapatkan metadata untuk laporan terbaru yang dikirim dari simpul DSC bernama Computer14 ke akun Otomatisasi bernama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi.
Cmdlet ini mengekspor laporan untuk simpul DSC milik akun yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Menentukan waktu akhir.
Cmdlet ini mendapatkan laporan bahwa Otomatisasi diterima sebelum waktu ini.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID unik laporan simpul DSC untuk didapatkan cmdlet ini.

```yaml
Type: System.Guid
Parameter Sets: ById
Aliases: ReportId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Terbaru
Menunjukkan bahwa cmdlet ini mendapatkan laporan DSC terbaru untuk simpul tertentu saja.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByLatest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeId
Menentukan ID unik simpul DSC tempat cmdlet ini mendapatkan laporan.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi simpul DSC di mana cmdlet ini mendapatkan laporan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu mulai.
Cmdlet ini mendapatkan laporan bahwa Otomatisasi diterima setelah waktu ini.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

### System.Nullable'1[[System.DateTimeOffset, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.DscNode

## CATATAN

## RELATED LINKS

[Get-AzureRmAutomationDscNode](./Get-AzureRmAutomationDscNode.md)

[Ekspor-AzureRmAutomationDscNodeReportContent](./Export-AzureRmAutomationDscNodeReportContent.md)


