---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 3B15C734-DF57-433A-8854-ACE2B35FF6CB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/set-azurermvmaemextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Set-AzureRmVMAEMExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Set-AzureRmVMAEMExtension.md
ms.openlocfilehash: c006c06d03e1f1c120ed62f38ea8b3e451d8fa21
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142358647"
---
# Set-AzureRmVMAEMExtension

## SYNOPSIS
Mengaktifkan dukungan untuk pemantauan untuk sistem SAP.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVMAEMExtension [-ResourceGroupName] <String> [-VMName] <String> [-EnableWAD]
 [[-WADStorageAccountName] <String>] [[-OSType] <String>] [-SkipStorage]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVMAEMExtension** memperbarui konfigurasi mesin virtual untuk mengaktifkan atau memperbarui dukungan untuk pemantauan sistem SAP yang diinstal pada mesin virtual.
Cmdlet menginstal ekstensi Azure Enhanced Monitoring (AEM) yang mengumpulkan data kinerja dan membuatnya dapat ditemukan untuk sistem SAP.

## EXAMPLES

### Contoh 1: Menggunakan ekstensi AEM
```
PS C:\> Set-AzureRmVMAEMExtension -ResourceGroupName "ResourceGroup11" -VMName "contoso-server" -WADStorageAccountName "stdstorage"
```

Perintah ini mengonfigurasi mesin virtual bernama contoso-server untuk menggunakan ekstensi AEM.
Perintah menentukan akun penyimpanan bernama stdstorage.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -EnableWAD
Jika parameter ini disediakan, commandlet akan mengaktifkan Windows Azure Diagnostics untuk mesin virtual ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSType
Menentukan tipe sistem operasi disk sistem operasi.
Jika disk sistem operasi tidak memiliki tipe, Anda harus menentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah: Windows dan Linux.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya mesin virtual yang diubah cmdlet ini.

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

### -SkipStorage
Menunjukkan bahwa cmdlet ini melewati konfigurasi penyimpanan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual.
Cmdlet ini menambahkan ekstensi AEM untuk mesin virtual yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WADStorageAccountName
Menentukan nama akun penyimpanan yang digunakan cmdlet ini untuk mengonfigurasi ekstensi LinuxDiagnostics atau IaaSDiagnostics.
Jika mesin virtual tidak menggunakan akun penyimpanan standar, Anda harus menentukan nilai untuk parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureRmVMAEMExtension](./Get-AzureRmVMAEMExtension.md)

[Hapus-AzureRmVMAEMExtension](./Remove-AzureRmVMAEMExtension.md)

[Uji-AzureRmVMAEMExtension](./Test-AzureRmVMAEMExtension.md)


