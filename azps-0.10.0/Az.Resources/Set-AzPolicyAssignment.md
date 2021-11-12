---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: C3B2C33F-8BD4-4E31-9450-EF6A3A6A5325
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/set-Azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Set-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Set-AzPolicyAssignment.md
ms.openlocfilehash: e3cdc70e90217bbf05b0d9eeee85913fac178803a12f11c7d3bb0338650611a9
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419365"
---
# Set-AzPolicyAssignment

## SYNOPSIS
Mengubah penetapan kebijakan.

## SYNTAX

### NameParameterSet (Default)
```
Set-AzPolicyAssignment -Name <String> -Scope <String> [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] [-Sku <Hashtable>] [-AssignIdentity] [-Location <String>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### IdParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] [-Sku <Hashtable>] [-AssignIdentity] [-Location <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzPolicyAssignment** mengubah penetapan kebijakan.
Tentukan tugas berdasarkan ID atau menurut nama dan lingkup.

## EXAMPLES

### Contoh 1: Perbarui nama tampilan
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment' -Scope $ResourceGroup.ResourceId
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -DisplayName 'Do not allow VM creation'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup cmdlet.
Perintah menyimpan objek tersebut dalam $ResourceGroup variabel.
Perintah kedua mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dengan menggunakan Get-AzPolicyAssignment cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
Perintah terakhir memperbarui nama tampilan pada penetapan kebijakan di grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 2: Tambahkan identitas terkelola ke penetapan kebijakan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -AssignIdentity -Location 'westus'
```

Perintah pertama mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dari langganan saat ini dengan menggunakan cmdlet Get-AzPolicyAssignment cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
Perintah terakhir menetapkan identitas terkelola ke penetapan kebijakan.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya untuk digunakan.
Jika Anda tidak menentukan versi, cmdlet ini menggunakan versi terbaru yang tersedia.

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

### -AssignIdentity
Buat dan tetapkan Identitas Azure Active Directory untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists'. Lokasi diperlukan saat menetapkan identitas.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi untuk penetapan kebijakan

```yaml
Type: System.String
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
Type: System.String
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
Type: System.String
Parameter Sets: IdParameterSet
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
Type: System.Management.Automation.ActionPreference
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
Type: System.String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi identitas sumber daya penetapan kebijakan. Ini diperlukan ketika sakelar -AssignIdentity digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Metadata
Metadata yang diperbarui untuk penetapan kebijakan. Ini bisa berupa jalur ke nama file yang berisi metadata, atau metadata sebagai string.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama penetapan kebijakan yang ditentukan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
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
Type: System.String[]
Parameter Sets: (All)
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.String
Parameter Sets: NameParameterSet
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
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: SkuObject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzPolicyAssignment](./Get-AzPolicyAssignment.md)

[New-AzPolicyAssignment](./New-AzPolicyAssignment.md)

[Remove-AzPolicyAssignment](./Remove-AzPolicyAssignment.md)


