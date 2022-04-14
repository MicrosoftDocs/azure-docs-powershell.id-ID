---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CognitiveServices.dll-Help.xml
Module Name: Az.CognitiveServices
online version: https://docs.microsoft.com/powershell/module/az.cognitiveservices/undo-azcognitiveservicesaccountremoval
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Undo-AzCognitiveServicesAccountRemoval.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Undo-AzCognitiveServicesAccountRemoval.md
ms.openlocfilehash: 74bdd82caee742a45a6b317349f01a546e571bdb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142273111"
---
# Undo-AzCognitiveServicesAccountRemoval

## SYNOPSIS
Memulihkan akun yang dihapus.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cognitiveservices/undo-azcognitiveservicesaccountremoval) untuk informasi terbaru.

## SYNTAX

```
Undo-AzCognitiveServicesAccountRemoval [-Location] <String> [-ResourceGroupName] <String> [-Name] <String>
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Undo-AzCognitiveServicesAccountRemoval** memulihkan akun Cognitive Services yang dihapus dengan lembut.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Undo-AzCognitiveServicesAccountRemoval -Location "Central US EUAP" -ResourceGroupName "ResourceGroupName" -Name "ResourceName"
```

Pulihkan akun Cognitive Services yang dihapus dengan lembut. Akun dibuat di "Central US EUAP", grup sumber daya dan nama sumber daya adalah "ResourceGroupName" dan "ResourceName". Jika grup sumber daya telah dihapus, Anda dapat membuat grup sumber daya baru dengan nama yang sama sebelum menjalankan `Undo-AzCognitiveServicesAccountRemoval`

## PARAMETERS

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

### -Paksa
Jangan meminta konfirmasi.

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

### -Lokasi
Lokasi Akun Layanan Kognitif.

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

### -Nama
Nama Akun Layanan Kognitif.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CognitiveServicesAccountName, AccountName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

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

### System.String

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzCognitiveServicesAccount](./Get-AzCognitiveServicesAccount.md)

[New-AzCognitiveServicesAccount](./New-AzCognitiveServicesAccount.md)

[Hapus-AzCognitiveServicesAccount](./Remove-AzCognitiveServicesAccount.md)
