---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 39AADD19-2EDD-4C1F-BC9E-22186DD9A085
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmoperatingsystem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMOperatingSystem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMOperatingSystem.md
ms.openlocfilehash: 26c3a82b1ae645f9d36411a4c0d6037629171064
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136561229"
---
# Set-AzVMOperatingSystem

## SYNOPSIS
Mengatur properti sistem operasi untuk mesin virtual.

## SYNTAX

### Windows (Default)
```
Set-AzVMOperatingSystem [-VM] <PSVirtualMachine> [-Windows] [-ComputerName] <String>
 [-Credential] <PSCredential> [[-CustomData] <String>] [-ProvisionVMAgent] [-EnableAutoUpdate]
 [[-TimeZone] <String>] [-WinRMHttp] [-PatchMode <String>] [-EnableHotpatching] [-AssessmentMode <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WindowsWinRmHttps
```
Set-AzVMOperatingSystem [-VM] <PSVirtualMachine> [-Windows] [-ComputerName] <String>
 [-Credential] <PSCredential> [[-CustomData] <String>] [-ProvisionVMAgent] [-EnableAutoUpdate]
 [[-TimeZone] <String>] [-WinRMHttp] [-WinRMHttps] [-WinRMCertificateUrl] <Uri> [-PatchMode <String>]
 [-EnableHotpatching] [-AssessmentMode <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### WindowsDisableVMAgent
```
Set-AzVMOperatingSystem [-VM] <PSVirtualMachine> [-Windows] [-ComputerName] <String>
 [-Credential] <PSCredential> [[-CustomData] <String>] [-DisableVMAgent] [-EnableAutoUpdate]
 [[-TimeZone] <String>] [-WinRMHttp] [-PatchMode <String>] [-EnableHotpatching] [-AssessmentMode <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WindowsDisableVMAgentWinRmHttps
```
Set-AzVMOperatingSystem [-VM] <PSVirtualMachine> [-Windows] [-ComputerName] <String>
 [-Credential] <PSCredential> [[-CustomData] <String>] [-DisableVMAgent] [-EnableAutoUpdate]
 [[-TimeZone] <String>] [-WinRMHttp] [-WinRMHttps] [-WinRMCertificateUrl] <Uri> [-PatchMode <String>]
 [-EnableHotpatching] [-AssessmentMode <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Linux
```
Set-AzVMOperatingSystem [-VM] <PSVirtualMachine> [-Linux] [-ComputerName] <String> [-Credential] <PSCredential>
 [[-CustomData] <String>] [-PatchMode <String>] [-DisablePasswordAuthentication] [-AssessmentMode <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMOperatingSystem** mengatur properti sistem operasi untuk mesin virtual.
Anda dapat menentukan kredensial masuk, nama komputer, dan tipe sistem operasi.

## EXAMPLES

### Contoh 1: Mengatur properti sistem operasi untuk mesin virtual baru
```
$SecurePassword = ConvertTo-SecureString "Password" -AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ("FullerP", $SecurePassword); 
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
$ComputerName = "ContosoVM122"
$WinRMCertUrl = "http://keyVaultName.vault.azure.net/secrets/secretName/secretVersion"
$TimeZone = "Pacific Standard Time"
$CustomData = "echo 'Hello World'"
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Windows -ComputerName $ComputerName -Credential $Credential -CustomData $CustomData -WinRMHttp -WinRMHttps -WinRMCertificateUrl $WinRMCertUrl -ProvisionVMAgent -EnableAutoUpdate -TimeZone $TimeZone -PatchMode "AutomaticByPlatform"
```

Perintah pertama mengonversi kata sandi ke string aman, lalu menyimpannya di $SecurePassword variabel.
Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` .
Perintah kedua membuat kredensial untuk FullerP pengguna dan kata sandi yang disimpan di $SecurePassword, lalu menyimpan kredensial di $Credential lain.
Untuk informasi selengkapnya, ketik `Get-Help New-Object` .
Perintah ketiga mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah keempat membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.
Empat perintah berikutnya menetapkan nilai ke variabel untuk digunakan dalam perintah berikut.
Karena Anda bisa menentukan string ini secara langsung di perintah **Set-AzVMOperatingSystem,** pendekatan ini hanya digunakan untuk keterbacaan.
Namun, Anda mungkin menggunakan pendekatan seperti ini dalam skrip.
Perintah terakhir mengatur properti sistem operasi untuk mesin virtual yang disimpan di $VirtualMachine.
Perintah menggunakan kredensial yang disimpan di $Credential.
Perintah menggunakan variabel yang ditetapkan di perintah sebelumnya untuk beberapa parameter.

### Contoh 2: Mengatur properti sistem operasi untuk mesin virtual baru dengan hot patching diaktifkan
```
$SecurePassword = ConvertTo-SecureString "Password" -AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ("FullerP", $SecurePassword); 
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
$ComputerName = "ContosoVM122"
$WinRMCertUrl = "http://keyVaultName.vault.azure.net/secrets/secretName/secretVersion"
$TimeZone = "Pacific Standard Time"
$CustomData = "echo 'Hello World'"
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Windows -ComputerName $ComputerName -Credential $Credential -CustomData $CustomData -WinRMHttp -WinRMHttps -WinRMCertificateUrl $WinRMCertUrl -ProvisionVMAgent -EnableAutoUpdate -TimeZone $TimeZone -PatchMode "AutomaticByPlatform" -EnableHotPatching
```

Perintah pertama mengonversi kata sandi ke string aman, lalu menyimpannya di $SecurePassword variabel.
Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` .
Perintah kedua membuat kredensial untuk FullerP pengguna dan kata sandi yang disimpan di $SecurePassword, lalu menyimpan kredensial di $Credential lain.
Untuk informasi selengkapnya, ketik `Get-Help New-Object` .
Perintah ketiga mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah keempat membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.
Empat perintah berikutnya menetapkan nilai ke variabel untuk digunakan dalam perintah berikut.
Karena Anda bisa menentukan string ini secara langsung di perintah **Set-AzVMOperatingSystem,** pendekatan ini hanya digunakan untuk keterbacaan.
Namun, Anda mungkin menggunakan pendekatan seperti ini dalam skrip.
Perintah terakhir mengatur properti sistem operasi untuk mesin virtual yang disimpan di $VirtualMachine.
Perintah menggunakan kredensial yang disimpan di $Credential.
Perintah menggunakan variabel yang ditetapkan di perintah sebelumnya untuk beberapa parameter.
Perintah tersebut mengaktifkan Hotpatching pada mesin virtual.

### Contoh 3: Mengatur properti sistem operasi untuk komputer virtual Linux baru
```
$SecurePassword = ConvertTo-SecureString "Password" -AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ("FullerP", $SecurePassword); 
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
$ComputerName = "ContosoVM122"
$CustomData = "echo 'Hello World'"
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Linux -ComputerName $ComputerName -Credential $Credential -CustomData $CustomData -PatchMode "AutomaticByPlatform"
```

Perintah pertama mengonversi kata sandi ke string aman, lalu menyimpannya di $SecurePassword variabel.
Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` .
Perintah kedua membuat kredensial untuk FullerP pengguna dan kata sandi yang disimpan di $SecurePassword, lalu menyimpan kredensial di $Credential lain.
Untuk informasi selengkapnya, ketik `Get-Help New-Object` .
Perintah ketiga mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah keempat membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.
Dua perintah berikutnya menetapkan nilai ke variabel untuk digunakan dalam perintah berikut.
Perintah terakhir mengatur properti sistem operasi untuk mesin virtual yang disimpan di $VirtualMachine.
Perintah menggunakan kredensial yang disimpan di $Credential.
Perintah menggunakan variabel yang ditetapkan di perintah sebelumnya untuk beberapa parameter.
Perintah mengatur nilai mode patch di komputer virtual ke "AutomaticByPlatform".

## PARAMETERS

### -AssessmentMode
Nilai mode penilaian otomatis untuk mesin virtual. Nilai yang mungkin adalah ImageDefault dan AutomaticByPlatform.

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

### -ComputerName
Menentukan nama komputer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Menentukan nama pengguna dan kata sandi untuk komputer virtual sebagai objek **PSCredential.**
Untuk mendapatkan kredensial, gunakan cmdlet Get-Credential.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomData
Menentukan string yang akan diteruskan ke komputer virtual. Untuk informasi selengkapnya lihat [Data Kustom di VM Azure.](https://docs.microsoft.com/azure/virtual-machines/custom-data)
**Catatan: Tidak direkomendasikan untuk menyimpan informasi sensitif dalam data kustom.**


```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DisablePasswordAuthentication
Mengindikasikan bahwa cmdlet ini menonaktifkan autentikasi kata sandi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Linux
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableVMAgent
Nonaktifkan Ketentuan VM Agent.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutoUpdate
Cmdlet ini mengaktifkan pembaruan otomatis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows, WindowsWinRmHttps, WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableHotpatching
Memungkinkan pelanggan untuk melakukan patch VM Azure mereka tanpa memerlukan reboot. Untuk enableHotpatching, 'provisionVMAgent' harus diatur ke true dan 'patchMode' harus diatur ke 'AutomaticByPlatform'.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows, WindowsWinRmHttps, WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Menunjukkan bahwa tipe sistem operasi adalah Linux.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Linux
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PatchMode
Menentukan mode patch dalam tamu ke mesin virtual IaaS.<br><br>
Nilai yang mungkin adalah:<br>
**AutomaticByPlatform** - Penginstalan patch untuk mesin virtual akan dikelola oleh Azure. Gunakan dengan -Windows atau -Linux. Requires -ProvisionVMAgent. Memerlukan -EnableAutoUpdate ketika digunakan dengan -Windows. <br>
**AutomaticByOS** - Instalasi patch untuk mesin virtual akan dikelola oleh OS. Gunakan dengan -Windows. Memerlukan -ProvisionVMAgent dan -EnableAutoUpdate.<br>
**Manual** - Anda mengontrol aplikasi patch ke komputer virtual. Gunakan dengan -Windows. Requires -ProvisionVMAgent.<br>
**ImageDefault** - Penginstalan patch dikelola oleh pengaturan default di gambar OS. Gunakan dengan -Linux.

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

### -ProvisionVMAgent
Menunjukkan bahwa pengaturan itu mengharuskan agar agen mesin virtual diinstal di komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows, WindowsWinRmHttps
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona Waktu
Menentukan zona waktu mesin virtual. misalnya Waktu Standar \" \" Pasifik. <br>
Nilai yang mungkin dapat [TimeZoneInfo.Id](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.id?#System_TimeZoneInfo_Id) nilai dari zona waktu yang dikembalikan oleh [TimeZoneInfo.GetSystemTimeZones.](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.getsystemtimezones)

```yaml
Type: System.String
Parameter Sets: Windows, WindowsWinRmHttps, WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual lokal untuk mengatur properti sistem operasi.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet Get-AzVM baru.
Buat objek mesin virtual menggunakan cmdlet New-AzVMConfig baru.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa tipe sistem operasi Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows, WindowsWinRmHttps, WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WinRMCertificateUrl
Menentukan URI sertifikat WinRM.
Ini perlu disimpan di Key Vault.

```yaml
Type: System.Uri
Parameter Sets: WindowsWinRmHttps, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: True
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WinRMHttp
Menunjukkan bahwa sistem operasi ini menggunakan WinRM HTTP.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows, WindowsWinRmHttps, WindowsDisableVMAgent, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WinRMHttps
Menunjukkan bahwa sistem operasi ini menggunakan HTTPS WinRM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsWinRmHttps, WindowsDisableVMAgentWinRmHttps
Aliases:

Required: True
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.Management.Automation.SwitchParameter

### System.String

### System.Management.Automation.PSCredential

### System.Uri

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-azvm](./Get-AzVM.md)

[New-azvmConfig](./New-AzVMConfig.md)


