---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: C3B2C33F-8BD4-4E31-9450-EF6A3A6A5325
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/set-azurermpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmPolicyAssignment.md
ms.openlocfilehash: 97be8f9eef611a87dae045df680d2823dc2f7acb
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421777"
---
# Set-AzureRmPolicyAssignment

## SYNOPSIS
Mengubah penetapan kebijakan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByPolicyAssignmentName (Default)
```
Set-AzureRmPolicyAssignment -Name <String> -Scope <String> [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Sku <Hashtable>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### SetByPolicyAssignmentId
```
Set-AzureRmPolicyAssignment -Id <String> [-DisplayName <String>] [-Description <String>] [-Sku <Hashtable>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmPolicyAssignment** mengubah penetapan kebijakan.
Tentukan tugas berdasarkan ID atau menurut nama dan lingkup.

## EXAMPLES

### Contoh 1: Perbarui nama tampilan
```
PS C:\>$ResourceGroup = Get-AzureRmResourceGroup -Name "ResourceGroup11"
PS C:\> $PolicyAssignment = Get-AzureRmPolicyAssignment -Name "PolicyAssignment" -Scope $ResourceGroup.ResourceId
PS C:\> Set-AzureRmPolicyAssignment -Id $PolicyAssignment.ResourceId -DisplayName "Do not allow VM creation"
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzureRMResourceGroup cmdlet.
Perintah menyimpan objek tersebut dalam $ResourceGroup variabel.

Perintah kedua mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dengan menggunakan Get-AzureRmPolicyAssignment cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.

Perintah terakhir memperbarui nama tampilan pada penetapan kebijakan yang diidentifikasi oleh properti **ResourceId** $PolicyAssignment.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya untuk digunakan.
Jika Anda tidak menentukan versi, cmdlet ini menggunakan versi terbaru yang tersedia.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Deskripsi
Deskripsi untuk penetapan kebijakan

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Menentukan nama tampilan baru untuk penetapan kebijakan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat untuk penetapan kebijakan yang ditentukan cmdlet ini.

```yaml
Type: String
Parameter Sets: SetByPolicyAssignmentId
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama penetapan kebijakan yang ditentukan cmdlet ini.

```yaml
Type: String
Parameter Sets: SetByPolicyAssignmentName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotScope
Penetapan kebijakan tidak lingkup.

```yaml
Type: String[]
Parameter Sets: SetByPolicyAssignmentName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Mengindikasikan bahwa cmdlet ini mempertimbangkan versi API prari perilisan bila secara otomatis menentukan versi mana yang akan digunakan.

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

### -Lingkup
Menentukan lingkup di mana kebijakan diterapkan.

```yaml
Type: String
Parameter Sets: SetByPolicyAssignmentName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Tabel hash yang menyatakan properti sku.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: SkuObject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

## RELATED LINKS

[Get-AzureRmPolicyAssignment](./Get-AzureRmPolicyAssignment.md)

[New-AzureRmPolicyAssignment](./New-AzureRmPolicyAssignment.md)

[Remove-AzureRmPolicyAssignment](./Remove-AzureRmPolicyAssignment.md)


