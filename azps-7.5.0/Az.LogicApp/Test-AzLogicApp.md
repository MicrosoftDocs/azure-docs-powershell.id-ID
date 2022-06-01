---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
ms.assetid: 929F4593-2A71-49B9-87F8-F24FA9F6E314
online version: https://docs.microsoft.com/powershell/module/az.logicapp/test-azlogicapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Test-AzLogicApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Test-AzLogicApp.md
ms.openlocfilehash: 352c504a72c393ec1e742c0667cc43098065b003
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145979455"
---
# Test-AzLogicApp

## SYNOPSIS
Memvalidasi definisi aplikasi logika.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.logicapp/test-azlogicapp) untuk informasi terbaru.

## SYNTAX

### LogicAppWithDefinitionParameterSet
```
Test-AzLogicApp -ResourceGroupName <String> -Name <String> -Location <String> [-State <String>]
 [-Definition <Object>] [-IntegrationAccountId <String>] [-Parameters <Object>] [-ParameterFilePath <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LogicAppWithDefinitionFileParameterSet
```
Test-AzLogicApp -ResourceGroupName <String> -Name <String> -Location <String> [-State <String>]
 [-DefinitionFilePath <String>] [-IntegrationAccountId <String>] [-Parameters <Object>]
 [-ParameterFilePath <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzLogicApp** memvalidasi definisi aplikasi logika dalam grup sumber daya.
Tentukan nama aplikasi logika, nama grup sumber daya, lokasi, status, ID akun integrasi, atau parameter.
Modul ini mendukung parameter dinamis.
Untuk menggunakan parameter dinamis, ketikkan dalam perintah .
Untuk menemukan nama parameter dinamis, ketik tanda hubung (-) setelah nama cmdlet, lalu tekan tombol Tab berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda menghilangkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.

## EXAMPLES

### Contoh 1: Memvalidasi aplikasi logika dengan menggunakan jalur file
```powershell
Test-AzLogicApp -ResourceGroupName "ResourceGroup11" -Name "LogicApp01" -Location "westus" -State "Enabled" -DefinitionFilePath "d:\workflows\Definition.json" -ParameterFilePath "d:\workflows\Parameters.json"
```

Perintah ini memvalidasi aplikasi logika bernama LogicApp01 di grup sumber daya yang ditentukan.
Perintah menentukan definisi dan jalur file parameter.

### Contoh 2: Memvalidasi aplikasi logika dengan menggunakan objek
```powershell
Test-AzLogicApp -ResourceGroupName "ResourceGroup11" -Name "LogicApp01" -Location "westus" -State "Enabled" -Definition [IO.File]::ReadAllText("d:\Workflows\Definition.json") -Parameters @{name1="value1";name2="value2"}
```

Perintah ini memvalidasi aplikasi logika bernama LogicApp01 di grup sumber daya yang ditentukan.
Perintah menentukan definisi dan objek parameter.

### Contoh: 3

Memvalidasi definisi aplikasi logika. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Test-AzLogicApp -DefinitionFilePath 'd:\workflows\Definition.json' -IntegrationAccountId <String> -Location 'westus' -Name 'LogicApp01' -ParameterFilePath 'd:\workflows\Parameters.json' -ResourceGroupName 'ResourceGroup11'
```

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

### -Definisi
Menentukan definisi aplikasi logika sebagai objek atau string dalam format JavaScript Object Notation (JSON).

```yaml
Type: System.Object
Parameter Sets: LogicAppWithDefinitionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionFilePath
Menentukan definisi aplikasi logika Anda sebagai jalur file definisi dalam format JSON.

```yaml
Type: System.String
Parameter Sets: LogicAppWithDefinitionFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntegrationAccountId
Menentukan ID akun integrasi untuk aplikasi logika.

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

### -Lokasi
Menentukan lokasi aplikasi logika.
Masukkan lokasi pusat data Azure, seperti AS Barat atau Asia Tenggara.
Anda dapat menempatkan aplikasi logika di lokasi mana pun.

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

### -Name
Menentukan nama aplikasi logika.

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

### -ParameterFilePath
Menentukan jalur file parameter berformat JSON.

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

### -Parameters
Menentukan objek pengumpulan parameter aplikasi logika.
Tentukan tabel hash, Kamus\<string\>, atau Kamus\<string, WorkflowParameter\>.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

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

### -State
Menentukan status aplikasi logika.
Nilai yang dapat diterima untuk parameter ini adalah: Diaktifkan dan Dinonaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzLogicApp](./Get-AzLogicApp.md)

[New-AzLogicApp](./New-AzLogicApp.md)

[Remove-AzLogicApp](./Remove-AzLogicApp.md)

[Set-AzLogicApp](./Set-AzLogicApp.md)

[Start-AzLogicApp](./Start-AzLogicApp.md)


