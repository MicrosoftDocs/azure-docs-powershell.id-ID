---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: C3B2C33F-8BD4-4E31-9450-EF6A3A6A5325
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyAssignment.md
ms.openlocfilehash: 2ac2e5598d619ee0af52a444125202158f22664b
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136392876"
---
# Set-AzPolicyAssignment

## SYNOPSIS
Mengubah penetapan kebijakan.

## SYNTAX

### NameParameterSet (Default)
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterNameObjectParameterSet
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] -PolicyParameterObject <Hashtable>
 [-Location <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-IdentityType <ManagedIdentityType>] [-IdentityId <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterNameStringParameterSet
```
Set-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-Metadata <String>] -PolicyParameter <String> [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IdParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterIdObjectParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] -PolicyParameterObject <Hashtable> [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterIdStringParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] -Id <String> [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] -PolicyParameter <String> [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObjectParameterSet
```
Set-AzPolicyAssignment [-NotScope <String[]>] [-DisplayName <String>] [-Description <String>]
 [-Metadata <String>] [-Location <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] -InputObject <PsPolicyAssignment> [-NonComplianceMessage <PsNonComplianceMessage[]>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
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

### Contoh 2: Tambahkan identitas terkelola yang ditetapkan sistem ke penetapan kebijakan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -IdentityType 'SystemAssigned' -Location 'westus'
```

Perintah pertama mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dari langganan saat ini dengan menggunakan cmdlet Get-AzPolicyAssignment baru.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
The final command assigns a system assigned managed identity to the policy assignment.

### Contoh 3: Tambahkan pengguna identitas terkelola yang ditetapkan ke penetapan kebijakan
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> $UserAssignedIdentity = Get-AzUserAssignedIdentity -ResourceGroupName 'ResourceGroup1' -Name 'UserAssignedIdentity1'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -IdentityType 'UserAssigned' -Location 'westus' -IdentityId $UserAssignedIdentity.Id
```

Perintah pertama mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dari langganan saat ini dengan menggunakan cmdlet Get-AzPolicyAssignment baru.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
Perintah kedua mendapatkan identitas terkelola yang ditetapkan pengguna bernama UserAssignedIdentity1 dengan menggunakan cmdlet Get-AzUserAssignedIdentity dan menyimpannya dalam variabel $UserAssignedIdentity tersebut.
The final command assigns the user assigned managed identity identified by the **Id** property of $UserAssignedIdentity to the policy assignment.

### Contoh 4: Perbarui parameter penetapan kebijakan dengan objek parameter kebijakan baru
```
PS C:\> $Locations = Get-AzLocation | where {($_.displayname -like 'france*') -or ($_.displayname -like 'uk*')}
PS C:\> $AllowedLocations = @{'listOfAllowedLocations'=($Locations.location)}
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'PolicyAssignment'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -PolicyParameterObject $AllowedLocations
```

Perintah pertama dan kedua membuat objek yang berisi semua kawasan Azure yang namanya dimulai dengan "france" atau "uk".
Perintah kedua menyimpan objek tersebut dalam $AllowedLocations variabel.
Perintah ketiga mendapatkan penetapan kebijakan bernama 'PolicyAssignment' Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
Perintah terakhir memperbarui nilai parameter pada penetapan kebijakan bernama PolicyAssignment.

### Contoh 5: Memperbarui parameter penetapan kebijakan dengan file parameter kebijakan
Buat file yang disebut _AllowedLocations.json_ di direktori kerja lokal dengan konten berikut.

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

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup cmdlet.
Perintah menyimpan objek tersebut dalam $ResourceGroup variabel.
Perintah kedua mendapatkan penetapan kebijakan bernama PenetapanKebesianKebesian dengan menggunakan Get-AzPolicyAssignment cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyAssignment variabel.
Perintah terakhir memperbarui properti enforcementMode pada penetapan kebijakan pada grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 7: Perbarui pesan tidak sesuai
```
PS C:\> $PolicyAssignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicy'
PS C:\> Set-AzPolicyAssignment -Id $PolicyAssignment.ResourceId -NonComplianceMessage @{Message="All resources must follow resource naming guidelines."}
```

Perintah pertama mendapatkan penetapan kebijakan yang bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam $PolicyAssignment variabel.
Perintah terakhir memperbarui pesan tidak memenuhi persyaratan pada penetapan kebijakan dengan pesan baru yang akan ditampilkan jika sumber daya ditolak oleh kebijakan tersebut.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat untuk penetapan kebijakan yang ditentukan cmdlet ini.

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
Menentukan Id identitas terkelola yang ditetapkan pengguna untuk ditetapkan ke penetapan kebijakan ini. Nilai ini diperlukan jika nilai 'UserAssigned' diteruskan ke parameter -IdentityType. 

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
Menentukan tipe identitas terkelola untuk ditetapkan ke penetapan kebijakan ini. Jika nilai 'SystemAssigned' disediakan, identitas terkelola yang ditetapkan untuk sistem akan dihasilkan dan ditetapkan untuk penetapan kebijakan ini. Jika nilai 'UserAssigned' disediakan, identitas yang ditetapkan pengguna yang diberikan melalui Id-nya ke parameter -IdentityId ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas. Izin harus diberikan ke identitas menggunakan identitas New-AzRoleAssignment setelah identitas yang ditetapkan sistem dibuat. Parameter IdentityType akan didahulukan jika kedua parameter AssignIdentity dan IdentityType digunakan.

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
Objek penetapan kebijakan untuk memperbarui yang merupakan output dari cmdlet lainnya.

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
Lokasi identitas sumber daya penetapan kebijakan. Hal ini diperlukan saat nilai -IdentityType disediakan.

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
Parameter Sets: NameParameterSet, PolicyParameterNameObjectParameterSet, PolicyParameterNameStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NonComplianceMessage
Pesan non-kepatuhan yang menjelaskan mengapa sumber daya tidak patuh dengan kebijakan tersebut.

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

### -PolicyParameter
Jalur file parameter kebijakan atau string baru untuk penetapan kebijakan.

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
Cmdlet ini mempertimbangkan versi API prari release ketika cmdlet menentukan versi mana yang akan digunakan secara otomatis.

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
Parameter Sets: NameParameterSet, PolicyParameterNameObjectParameterSet, PolicyParameterNameStringParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Nullable'1[[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode, Microsoft.Azure.PowerShell.Cmdlets.ResourceManager, Version=3.5.0.0, Culture=neutral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

## CATATAN

## RELATED LINKS

[Get-AzPolicyAssignment](./Get-AzPolicyAssignment.md)

[New-AzPolicyAssignment](./New-AzPolicyAssignment.md)

[Remove-AzPolicyAssignment](./Remove-AzPolicyAssignment.md)


