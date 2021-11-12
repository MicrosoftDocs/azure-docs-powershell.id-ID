---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
Module Name: AzureRM.ServiceFabric
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.servicefabric/new-azurermservicefabriccluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/New-AzureRmServiceFabricCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/New-AzureRmServiceFabricCluster.md
ms.openlocfilehash: 5da8d1f48a50cafc970278d59b99750f283a9414
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424623"
---
# New-AzureRmServiceFabricCluster

## SYNOPSIS
This command uses certificates that you provide or system generated self-signed certificates to set up a new service fabric cluster. Templat ini dapat menggunakan templat default atau templat kustom yang telah diberikan. Anda memiliki opsi menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri untuk atau mengambilnya nanti dari kunci vault. 

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByDefaultArmTemplate (Default)
```
New-AzureRmServiceFabricCluster [-ResourceGroupName] <String> [-CertificateOutputFolder <String>]
 [-CertificatePassword <SecureString>] [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>]
 -Location <String> [-Name <String>] [-VmUserName <String>] [-ClusterSize <Int32>]
 [-CertificateSubjectName <String>] -VmPassword <SecureString> [-OS <OperatingSystem>] [-VmSku <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MenurutExistingKeyVault
```
New-AzureRmServiceFabricCluster [-ResourceGroupName] <String> -TemplateFile <String> -ParameterFile <String>
 [-VmPassword <SecureString>] -SecretIdentifier <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByNewVaultxAndVaultName
```
New-AzureRmServiceFabricCluster [-ResourceGroupName] <String> -TemplateFile <String> -ParameterFile <String>
 [-CertificateOutputFolder <String>] [-CertificatePassword <SecureString>] [-KeyVaultResouceGroupName <String>]
 [-KeyVaultName <String>] [-CertificateSubjectName <String>] [-VmPassword <SecureString>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MenurutExistingVaultxAndVaultName
```
New-AzureRmServiceFabricCluster [-ResourceGroupName] <String> -TemplateFile <String> -ParameterFile <String>
 -CertificateFile <String> [-CertificatePassword <SecureString>] [-SecondaryCertificateFile <String>]
 [-SecondaryCertificatePassword <SecureString>] [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>]
 [-VmPassword <SecureString>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah **New-AzureRmServiceFabricCluster** menggunakan sertifikat yang Anda sediakan atau sistem yang dihasilkan sertifikat yang ditandatangani sendiri untuk menyiapkan kluster kain layanan baru. Templat yang digunakan bisa merupakan templat default atau templat kustom yang Anda sediakan. Anda memiliki opsi menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri atau mengambilnya nanti dari kunci vault.

Jika Anda menentukan templat kustom dan file parameter, Anda tidak perlu menyediakan informasi sertifikat dalam file parameter, sistem akan mengisi parameter ini.

Empat opsi tersebut dijelaskan secara mendetail di bawah ini. Gulir ke bawah untuk penjelasan dari setiap parameter.

## EXAMPLES

### Contoh 1: Menentukan ukuran kluster saja, nama subjek sertifikat, dan OS untuk menyebarkan kluster.
```
$pass="Password#1234" | ConvertTo-SecureString -AsPlainText -Force
$RGname="test01"
$clusterloc="SouthCentralUS"
$subname="{0}.{1}.cloudapp.azure.com" -f $RGname, $clusterloc
$pfxfolder="~\Documents"

Write-Output "Create cluster in '$clusterloc' with cert subject name '$subname' and cert output path '$pfxfolder'"

New-AzureRmServiceFabricCluster -ResourceGroupName $RGname -Location $clusterloc -ClusterSize 3 -VmPassword $pass -CertificateSubjectName $subname -CertificateOutputFolder $pfxfolder -CertificatePassword $pass -OS WindowsServer2016Datacenter
```

Perintah ini hanya menentukan ukuran kluster, nama subjek sertifikat, dan OS untuk menyebarkan kluster.

### Contoh 2: Menentukan sumber daya Sertifikat yang sudah ada dalam penyimpanan kunci dan templat kustom untuk menyebarkan kluster
```
$RGname="test20"
$templateParmfile="C:\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploytest.parameters.json"
$templateFile="C:\azure-quickstart-templates\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploy.json"
$secretId="https://test1.vault.azure.net:443/secrets/testcertificate4/56ec774dc61a462bbc645ffc9b4b225f"

New-AzureRmServiceFabricCluster -ResourceGroupName $RGname -TemplateFile $templateFile -ParameterFile $templateParmfile -SecretIdentifier $secretId
```

Perintah ini menentukan sumber daya Sertifikat yang sudah ada dalam penyimpanan kunci dan templat kustom untuk menyebarkan kluster.

### Contoh 3: Buat kluster baru menggunakan templat kustom. Menentukan nama grup sumber daya yang berbeda untuk vault kunci dan meminta sistem mengunggah sertifikat baru ke dalamnya
```
$pass="Password#1234" | ConvertTo-SecureString -AsPlainText -Force
$RGname="test20"
$keyVaultRG="test20kvrg"
$keyVault="test20kv"
$clusterloc="SouthCentralUS"
$subname="{0}.{1}.$clusterloc.cloudapp.azure.com" -f $RGName, $clusterloc
$pfxfolder="~\Documents"
$templateParmfile="C:\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploytest.parameters.json"
$templateFile="C:\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploy.json"

New-AzureRmServiceFabricCluster -ResourceGroupName $RGname -TemplateFile $templateFile -ParameterFile $templateParmfile -CertificateOutputFolder $pfxfolder -CertificatePassword $pass -KeyVaultResouceGroupName $keyVaultRG  -KeyVaultName $keyVault -CertificateSubjectName $subname
```

Perintah ini membuat kluster baru menggunakan templat kustom. Menentukan nama grup sumber daya yang berbeda untuk vault kunci dan meminta sistem mengunggah sertifikat baru ke dalamnya

### Contoh 4: Bawa Sertifikat Anda sendiri dan templat kustom dan buat kluster baru
```
$pass="Password#1234" | ConvertTo-SecureString -AsPlainText -Force
$RGname="test20"
$keyVaultRG="test20kvrg"
$keyVault="test20kv"
$pfxsourcefile="c:\Mycertificates\my2017Prodcert.pfx"
$templateParmfile="~\Documents\GitHub\azure-quickstart-templates-parms\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploytest.parameters.json"
$templateFile="~\GitHub\azure-quickstart-templates\service-fabric-secure-nsg-cluster-65-node-3-nodetype\azuredeploy.json"

New-AzureRmServiceFabricCluster -ResourceGroupName $RGname -TemplateFile $templateFile -ParameterFile $templateParmfile -CertificateFile $pfxsourcefile -CertificatePassword $pass -KeyVaultResouceGroupName $keyVaultRG -KeyVaultName $keyVault
```

Perintah ini akan memungkinkan Anda membawa Sertifikat dan templat kustom Anda sendiri serta membuat kluster baru.

## PARAMETERS

### -CertificateFile
Jalur file sertifikat yang sudah ada untuk sertifikat kluster utama.

```yaml
Type: String
Parameter Sets: ByExistingPfxAndVaultName
Aliases: Source

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateOutputFolder
Folder file sertifikat baru yang akan dibuat.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate, ByNewPfxAndVaultName
Aliases: Destination

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificatePassword
Kata sandi file sertifikat.

```yaml
Type: SecureString
Parameter Sets: ByDefaultArmTemplate, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: CertPassword

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateSubjectName
Nama subjek sertifikat yang akan dibuat.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate, ByNewPfxAndVaultName
Aliases: Subject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClusterSize
Jumlah node di kluster. Defaultnya adalah 5 node.

```yaml
Type: Int32
Parameter Sets: ByDefaultArmTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -KeyVaultName
Nama key vault Azure. Jika tidak diberikan, pengaturan defaultnya akan diberikan ke nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyVaultResouceGroupName
Nama grup sumber daya penyimpanan tombol Azure. Jika tidak, akan defaultnya adalah nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi grup sumber daya.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Tentukan nama kluster. Jika tidak diberikan, akan sama seperti nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate
Aliases: ClusterName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OS
Sistem Operasi VM yang menjadi kluster.

```yaml
Type: OperatingSystem
Parameter Sets: ByDefaultArmTemplate
Aliases: VmImage
Accepted values: WindowsServer2012R2Datacenter, WindowsServer2016Datacenter, WindowsServer2016DatacenterwithContainers, UbuntuServer1604

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParameterFile
Jalur ke file parameter templat.

```yaml
Type: String
Parameter Sets: ByExistingKeyVault, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecondaryCertificateFile
Jalur file sertifikat yang sudah ada untuk sertifikat kluster sekunder.

```yaml
Type: String
Parameter Sets: ByExistingPfxAndVaultName
Aliases: SecSource

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SecondaryCertificatePassword
Kata sandi file sertifikat.

```yaml
Type: SecureString
Parameter Sets: ByExistingPfxAndVaultName
Aliases: SecCertPassword

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SecretIdentifier
URL rahasia penyimpanan kunci Azure yang sudah ada, misalnya: https://mykv.vault.azure.net:443/secrets/mysecrets/55ec7c4dc61a462bbc645ffc9b4b225f ' '.

```yaml
Type: String
Parameter Sets: ByExistingKeyVault
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TemplateFile
Jalur ke file templat.

```yaml
Type: String
Parameter Sets: ByExistingKeyVault, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VmPassword
Kata sandi Vm.

```yaml
Type: SecureString
Parameter Sets: ByDefaultArmTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SecureString
Parameter Sets: ByExistingKeyVault, ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Vmsku
The Vm Sku.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate
Aliases: Sku

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmUserName
Nama pengguna untuk pembuatan log ke Vm.

```yaml
Type: String
Parameter Sets: ByDefaultArmTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String
System.Security.SecureString System.Int32 Microsoft.Azure.Commands.ServiceFabric.Models.OperatingSystem

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSDeploymentResult

## CATATAN

## RELATED LINKS

