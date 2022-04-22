---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: C3B2C33F-8BD4-4E31-9450-EF6A3A6A5325
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyAssignment.md
ms.openlocfilehash: 9073f4c44a25c6e51daa4c04a608f0f7c56a7f14
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143009729"
---
# Set-AzPolicyAssignment

## SYNOPSIS
Mengubah penetapan kebijakan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/set-azpolicyassignment) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterNameObjectParameterSet
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] -PolicyParameterObject <Hashtable> [-AssignIdentity]
 [-Location <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-IdentityType <ManagedIdentityType>] [-IdentityId <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterNameStringParameterSet
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] -PolicyParameter <String> [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IdParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterIdObjectParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] -PolicyParameterObject <Hashtable> [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterIdStringParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] -PolicyParameter <String> [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObjectParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] [-AssignIdentity] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] -InputObject <PsPolicyAssignment> [-NonComplianceMessage <PsNonComplianceMessage[]>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzPolicyAssignment** mengubah penetapan kebijakan.
Tentukan tugas menurut ID atau menurut nama dan lingkup.

## EXAMPLES

### Contoh 1: Memperbarui nama tampilan
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment' -Scope $ResourceGroup.ResourceId
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -DisplayName 'Do not allow VM creation'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan penetapan kebijakan bernama PolicyAssignment menggunakan cmdlet Get-AzPolicyAssignment.
Perintah menyimpan objek tersebut dalam variabel $PolicyAssignment.
Perintah akhir memperbarui nama tampilan pada penetapan kebijakan pada grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 2: Menambahkan sistem yang ditetapkan identitas terkelola ke penetapan kebijakan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -IdentityType 'SystemAssigned' -Location 'westus'
```

Perintah pertama mendapatkan penetapan kebijakan bernama PolicyAssignment dari langganan saat ini menggunakan cmdlet Get-AzPolicyAssignment.
Perintah menyimpan objek tersebut dalam variabel $PolicyAssignment.
Perintah akhir menetapkan identitas terkelola sistem yang ditetapkan untuk penetapan kebijakan.

### Contoh 3: Menambahkan identitas terkelola yang ditetapkan pengguna ke penetapan kebijakan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> $UserAssignedIdentity = Get-AzUserAssignedIdentity -ResourceGroupName 'ResourceGroup1' -Name 'UserAssignedIdentity1'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -IdentityType 'UserAssigned' -Location 'westus' -IdentityId $UserAssignedIdentity.Id
```

Perintah pertama mendapatkan penetapan kebijakan bernama PolicyAssignment dari langganan saat ini menggunakan cmdlet Get-AzPolicyAssignment.
Perintah menyimpan objek tersebut dalam variabel $PolicyAssignment.
Perintah kedua mendapatkan identitas terkelola yang ditetapkan pengguna bernama UserAssignedIdentity1 dengan menggunakan cmdlet Get-AzUserAssignedIdentity dan menyimpannya dalam variabel $UserAssignedIdentity.
Perintah akhir menetapkan identitas terkelola yang ditetapkan pengguna yang diidentifikasi oleh properti **Id** dari $UserAssignedIdentity ke penetapan kebijakan.

### Contoh 4: Memperbarui parameter penetapan kebijakan dengan objek parameter kebijakan baru
```
PS C:\> $Locations = Get-AzLocation | where {($_.displayname -like 'france*') -or ($_.displayname -like 'uk*')}
PS C:\> $AllowedLocations = @{'listOfAllowedLocations'=($Locations.location)}
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -PolicyParameterObject $AllowedLocations
```

Perintah pertama dan kedua membuat objek yang berisi semua kawasan Azure yang namanya dimulai dengan "france" atau "uk".
Perintah kedua menyimpan objek tersebut dalam variabel $AllowedLocations.
Perintah ketiga mendapatkan penetapan kebijakan bernama 'PolicyAssignment' Perintah menyimpan objek tersebut dalam variabel $PolicyAssignment.
Perintah akhir memperbarui nilai parameter pada penetapan kebijakan bernama PolicyAssignment.

### Contoh 5: Memperbarui parameter penetapan kebijakan dengan file parameter kebijakan
Buat file yang disebut _AllowedLocations.json_ di direktori kerja lokal dengan konten berikut ini.

```
{
    "listOfAllowedLocations":  {
      "value": [
        "uksouth",
        "ukwest",
        "francecentral",
        "francesouth"
      ]
    }
}
```

```
PS C:\> Set-AzPolicyAssignment -Name 'PolicyAssignment' -PolicyParameter .\AllowedLocations.json
```

Perintah memperbarui penetapan kebijakan bernama 'PolicyAssignment' menggunakan file parameter kebijakan AllowedLocations.json dari direktori kerja lokal.

### Contoh 6: Memperbarui enforcementMode
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment' -Scope $ResourceGroup.ResourceId
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -EnforcementMode Default
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan penetapan kebijakan bernama PolicyAssignment menggunakan cmdlet Get-AzPolicyAssignment.
Perintah menyimpan objek tersebut dalam variabel $PolicyAssignment.
Perintah akhir memperbarui properti enforcementMode pada penetapan kebijakan pada grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 7: Memperbarui pesan non-kepatuhan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicy'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -NonComplianceMessage @{Message="All resources must follow resource naming guidelines."}
```

Perintah pertama mendapatkan penetapan kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam variabel $PolicyAssignment.
Perintah akhir memperbarui pesan ketidaksesuaian pada penetapan kebijakan dengan pesan baru yang akan ditampilkan jika sumber daya ditolak oleh kebijakan.

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
Buat dan tetapkan identitas terkelola sistem yang ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas.

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

### -EnforcementMode
Mode penerapan untuk penetapan kebijakan. Saat ini, nilai yang valid adalah Default, DoNotEnforce.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode]
Parameter Sets: (All)
Aliases:
Accepted values: Default, DoNotEnforce

Required: False
Position: Named
Default value: Default
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat untuk penetapan kebijakan yang diubah cmdlet ini.

```yaml
Type: System.String
Parameter Sets: IdParameterSet, PolicyParameterIdObjectParameterSet, PolicyParameterIdStringParameterSet
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityId
Menentukan ID identitas terkelola yang ditetapkan pengguna untuk ditetapkan ke penetapan kebijakan ini. Nilai ini diperlukan jika nilai 'UserAssigned' dikirimkan ke parameter -IdentityType. 

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

### -IdentityType
Menentukan tipe identitas terkelola untuk ditetapkan ke penetapan kebijakan ini. Jika nilai 'SystemAssigned' disediakan, identitas terkelola yang ditetapkan sistem akan dihasilkan dan ditetapkan untuk penetapan kebijakan ini. Jika nilai 'UserAssigned' disediakan, identitas yang ditetapkan pengguna yang dikirimkan melalui Id ke parameter -IdentityId ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas. Izin harus diberikan ke identitas menggunakan New-AzRoleAssignment setelah identitas yang ditetapkan sistem dibuat. Parameter IdentityType akan diberikan prioritas jika parameter AssignIdentity dan IdentityType digunakan.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Resources.ManagedIdentityType]
Parameter Sets: (All)
Aliases:
Accepted values: SystemAssigned, UserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek penetapan kebijakan untuk memperbarui yang merupakan output dari cmdlet lain.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi identitas sumber daya penetapan kebijakan. Ini diperlukan ketika nilai -IdentityType disediakan.

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
Menentukan nama penetapan kebijakan yang diubah cmdlet ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet, PolicyParameterNameObjectParameterSet, PolicyParameterNameStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NonComplianceMessage
Pesan tidak sesuai yang menjelaskan mengapa sumber daya tidak sesuai dengan kebijakan.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotScope
Penetapan kebijakan bukan lingkup.

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

### -PolicyParameter
Kebijakan baru parameter jalur file atau string untuk penetapan kebijakan.

```yaml
Type: System.String
Parameter Sets: PolicyParameterNameStringParameterSet, PolicyParameterIdStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyParameterObject
Objek parameter kebijakan baru untuk penetapan kebijakan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: PolicyParameterNameObjectParameterSet, PolicyParameterIdObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pra
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API prarilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Menentukan lingkup penerapan kebijakan.

```yaml
Type: System.String
Parameter Sets: NameParameterSet, PolicyParameterNameObjectParameterSet, PolicyParameterNameStringParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Nullable'1[[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode, Microsoft.Azure.PowerShell.Cmdlets.ResourceManager, Version=3.5.0.0, Culture=neutral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

## NOTES

## RELATED LINKS

[Get-AzPolicyAssignment](./Get-AzPolicyAssignment.md)

[New-AzPolicyAssignment](./New-AzPolicyAssignment.md)

[Remove-AzPolicyAssignment](./Remove-AzPolicyAssignment.md)


