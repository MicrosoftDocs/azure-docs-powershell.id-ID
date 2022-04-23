---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 43D01A97-75B9-46CE-B007-26FE6A97C31C
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/update-azcontainerservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Update-AzContainerService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Update-AzContainerService.md
ms.openlocfilehash: 1a15486b3e24dec3af66cb98391bd8322c28d2e6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143363087"
---
# Update-AzContainerService

## SYNOPSIS
Memperbarui status layanan kontainer.

## SYNTAX

```
Update-AzContainerService [-ResourceGroupName] <String> [-Name] <String>
 [-ContainerService] <PSContainerService> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzContainerService** memperbarui status layanan kontainer agar sesuai dengan instans lokal layanan.

## EXAMPLES

### Contoh 1: Memperbarui layanan kontainer
```
PS C:\> Get-AzContainerService -ResourceGroupName "ResourceGroup17" -Name "CSResourceGroup17" | Remove-AzContainerServiceAgentPoolProfile -Name "AgentPool01" | Add-AzContainerServiceAgentPoolProfile -Name "AgentPool01" -VmSize "Standard_A1" -DnsPrefix "APResourceGroup17" -Count 2 | Update-AzContainerService -ResourceGroupName "ResourceGroup17" -Name "CSResourceGroup17"
```

Perintah ini mendapatkan layanan kontainer bernama CSResourceGroup17 menggunakan cmdlet Get-AzContainerService.
Perintah melewati objek tersebut ke cmdlet Remove-AzContainerServiceAgentPoolProfile menggunakan operator pipeline.

**Remove-AzContainerServiceAgentPoolProfile** menghapus profil bernama AgentPool01.
Perintah melewati hasil ke cmdlet Add-AzContainerServiceAgentPoolProfile.

**Add-AzContainerServiceAgentPoolProfile** menambahkan profil yang memiliki nama AgentPool01, dan memiliki properti yang ditentukan.
Perintah melewati hasil ke cmdlet saat ini.

Cmdlet saat ini memperbarui layanan kontainer untuk mencerminkan perubahan yang dibuat dalam perintah ini.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerService
Menentukan objek **ContainerService** lokal yang berisi perubahan.

```yaml
Type: PSContainerService
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama layanan kontainer yang diperbarui cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya layanan kontainer yang diperbarui cmdlet ini.

```yaml
Type: String
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.

Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### ContainerService
Parameter 'ContainerService' menerima nilai tipe 'ContainerService' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSContainerService

## NOTES

## RELATED LINKS

[Add-AzContainerServiceAgentPoolProfile](./Add-AzContainerServiceAgentPoolProfile.md)

[Get-AzContainerService](./Get-AzContainerService.md)

[New-AzContainerService](./New-AzContainerService.md)

[Hapus-AzContainerService](./Remove-AzContainerService.md)

[Remove-AzContainerServiceAgentPoolProfile](./Remove-AzContainerServiceAgentPoolProfile.md)


