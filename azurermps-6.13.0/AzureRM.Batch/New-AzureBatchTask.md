---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 2B4BFDDA-9721-42E6-84E1-A209CB782954
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/new-azurebatchtask
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/New-AzureBatchTask.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/New-AzureBatchTask.md
ms.openlocfilehash: a081e6da07557033430033adc8ef28cb4b63da8c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141844646"
---
# New-AzureBatchTask

## SYNOPSIS
Membuat tugas Kumpulan di bawah pekerjaan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### JobId_Single (Default)
```
New-AzureBatchTask -JobId <String> -Id <String> [-DisplayName <String>] [-CommandLine <String>]
 [-ResourceFiles <IDictionary>] [-EnvironmentSettings <IDictionary>]
 [-AuthenticationTokenSettings <PSAuthenticationTokenSettings>] [-UserIdentity <PSUserIdentity>]
 [-AffinityInformation <PSAffinityInformation>] [-Constraints <PSTaskConstraints>]
 [-MultiInstanceSettings <PSMultiInstanceSettings>] [-DependsOn <TaskDependencies>]
 [-ApplicationPackageReferences <PSApplicationPackageReference[]>] [-OutputFile <PSOutputFile[]>]
 [-ExitConditions <PSExitConditions>] [-ContainerSettings <PSTaskContainerSettings>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### JobId_Bulk
```
New-AzureBatchTask -JobId <String> [-Tasks <PSCloudTask[]>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### JobObject_Bulk
```
New-AzureBatchTask [-Job <PSCloudJob>] [-Tasks <PSCloudTask[]>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### JobObject_Single
```
New-AzureBatchTask [-Job <PSCloudJob>] -Id <String> [-DisplayName <String>] [-CommandLine <String>]
 [-ResourceFiles <IDictionary>] [-EnvironmentSettings <IDictionary>]
 [-AuthenticationTokenSettings <PSAuthenticationTokenSettings>] [-UserIdentity <PSUserIdentity>]
 [-AffinityInformation <PSAffinityInformation>] [-Constraints <PSTaskConstraints>]
 [-MultiInstanceSettings <PSMultiInstanceSettings>] [-DependsOn <TaskDependencies>]
 [-ApplicationPackageReferences <PSApplicationPackageReference[]>] [-OutputFile <PSOutputFile[]>]
 [-ExitConditions <PSExitConditions>] [-ContainerSettings <PSTaskContainerSettings>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureBatchTask** membuat tugas Azure Batch di bawah pekerjaan yang ditentukan oleh parameter *JobId* atau parameter *Job*.

## EXAMPLES

### Contoh 1: Membuat tugas Kumpulan
```
PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -BatchContext $Context
```

Perintah ini membuat tugas yang memiliki ID Task23 di bawah pekerjaan yang memiliki ID Job-000001.
Tugas menjalankan perintah yang ditentukan.
Gunakan cmdlet **Get-AzureRmBatchAccountKeys** untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Membuat tugas Kumpulan
```
PS C:\> $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
PS C:\> $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
PS C:\>Get-AzureBatchJob -Id "Job-000001" -BatchContext $Context | New-AzureBatchTask -Id "Task26" -CommandLine "cmd /c echo hello > newFile.txt" -UserIdentity $userIdentity -BatchContext $Context
```

Perintah ini mendapatkan pekerjaan Batch yang memiliki ID Job-000001 dengan menggunakan cmdlet **Get-AzureBatchJob** .
Perintah melewati pekerjaan tersebut ke cmdlet saat ini menggunakan operator pipeline.
Perintah membuat tugas yang memiliki ID Task26 di bawah pekerjaan tersebut.
Tugas menjalankan perintah yang ditentukan dengan menggunakan izin yang ditingkatkan.

### Contoh 3: Menambahkan kumpulan tugas ke pekerjaan yang ditentukan menggunakan pipeline
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "ContosoBatchAccount"
PS C:\> $Task01 = New-Object Microsoft.Azure.Commands.Batch.Models.PSCloudTask("Task23", "cmd /c dir /s")
PS C:\> $Task02 = New-Object Microsoft.Azure.Commands.Batch.Models.PSCloudTask("Task24", "cmd /c dir /s")
PS C:\> Get-AzureBatchJob -Id "Job-000001" -BatchContext $Context | New-AzureBatchTask -Tasks @($Task01, $Task02) -BatchContext $Context
```

Perintah pertama membuat referensi objek ke kunci akun untuk akun batch bernama ContosoBatchAccount menggunakan **Get-AzureRmBatchAccountKeys**.
Perintah menyimpan referensi objek ini dalam variabel $Context.
Dua perintah berikutnya membuat objek **PSCloudTask** menggunakan cmdlet New-Object.
Perintah menyimpan tugas dalam variabel $Task 01 dan $Task 02.
Perintah terakhir mendapatkan pekerjaan Batch yang memiliki ID Job-000001 menggunakan **Get-AzureBatchJob**.
Lalu perintah melewati pekerjaan tersebut ke cmdlet saat ini dengan menggunakan operator pipeline.
Perintah menambahkan kumpulan tugas di bawah pekerjaan tersebut.
Perintah menggunakan konteks yang disimpan di $Context.

### Contoh 4: Menambahkan kumpulan tugas ke pekerjaan yang ditentukan
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "ContosoBatchAccount"
PS C:\> $Task01 = New-Object Microsoft.Azure.Commands.Batch.Models.PSCloudTask("Task23", "cmd /c dir /s")
PS C:\> $Task02 = New-Object Microsoft.Azure.Commands.Batch.Models.PSCloudTask("Task24", "cmd /c dir /s")
PS C:\> New-AzureBatchTask -JobId "Job-000001" -Tasks @($Task01, $Task02) -BatchContext $Context
```

Perintah pertama membuat referensi objek ke kunci akun untuk akun batch bernama ContosoBatchAccount menggunakan **Get-AzureRmBatchAccountKeys**.
Perintah menyimpan referensi objek ini dalam variabel $Context.
Dua perintah berikutnya membuat objek **PSCloudTask** menggunakan cmdlet New-Object.
Perintah menyimpan tugas dalam variabel $Task 01 dan $Task 02.
Perintah terakhir menambahkan tugas yang disimpan di $Task 01 dan $Task 02 di bawah pekerjaan yang memiliki ID Job-000001.

### Contoh 5: Menambahkan tugas dengan file output
```
PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -BatchContext $Context
PS C:\>$blobContainerDestination = New-Object Microsoft.Azure.Commands.Batch.Models.PSOutputFileBlobContainerDestination "https://myaccount.blob.core.windows.net/sascontainer?sv=2015-04-05&st=2015-04-29T22%3A18%3A26Z&se=2015-04-30T02%3A23%3A26Z&sr=b&sp=rw&spr=https&sig=Z%2FRHIX5Xcg0Mq2rqI3OlWTjEg2tYkboXr1P9ZUXDtkk%3D"
PS C:\>$destination = New-Object Microsoft.Azure.Commands.Batch.Models.PSOutputFileDestination $blobContainerDestination
PS C:\>$uploadOptions = New-Object Microsoft.Azure.Commands.Batch.Models.PSOutputFileUploadOptions "TaskSuccess"
PS C:\>$outputFile = New-Object Microsoft.Azure.Commands.Batch.Models.PSOutputFile "*.txt", $blobContainerDestination, $uploadOptions

PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -OutputFile $outputFile -BatchContext $Context
```

### Contoh 6: Menambahkan tugas dengan pengaturan token autentikasi
```
PS C:\>$authSettings = New-Object Microsoft.Azure.Commands.Batch.Models.PSAuthenticationTokenSettings
PS C:\>$authSettings.Access = "Job"
PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -AuthenticationTokenSettings $authSettings -BatchContext $Context
```

### Contoh 7: Menambahkan tugas yang berjalan dalam wadah
```
PS C:\>New-AzureBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ContainerSettings New-Object Microsoft.Azure.Commands.Batch.Models.PSTaskContainerSettings "containerImageName"
```

## PARAMETERS

### -AffinityInformation
Menentukan petunjuk lokalitas yang digunakan layanan Batch untuk memilih simpul untuk menjalankan tugas.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSAffinityInformation
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationPackageReferences
```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSApplicationPackageReference[]
Parameter Sets: JobId_Single, JobObject_Single
Aliases: ApplicationPackageReference

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationTokenSettings
Pengaturan untuk token autentikasi yang bisa digunakan tugas untuk melakukan operasi layanan batch.
Jika ini diatur, layanan Batch menyediakan tugas dengan token autentikasi yang dapat digunakan untuk mengautentikasi operasi layanan Batch tanpa memerlukan kunci akses akun. Token disediakan melalui variabel lingkungan AZ_BATCH_AUTHENTICATION_TOKEN. Operasi yang dapat dilakukan tugas menggunakan token bergantung pada pengaturan. Misalnya, tugas bisa meminta izin pekerjaan untuk menambahkan tugas lain ke pekerjaan, atau memeriksa status pekerjaan atau tugas lain.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSAuthenticationTokenSettings
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzureRmBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzureRmBatchAccountKeys untuk mendapatkan objek BatchAccountContext dengan tombol akses yang diisi. Ketika menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

```yaml
Type: Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CommandLine
Menentukan baris perintah untuk tugas tersebut.

```yaml
Type: System.String
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Batasan
Menentukan batasan eksekusi yang berlaku untuk tugas ini.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSTaskConstraints
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerSettings
Pengaturan untuk wadah tempat tugas dijalankan.
Jika kumpulan yang akan menjalankan tugas ini memiliki kontainerKonfigurasi yang diatur, ini harus diatur juga. Jika kumpulan yang akan menjalankan tugas ini tidak memiliki kontainerKonfigurasi yang diatur, ini tidak boleh diatur. Ketika ini ditentukan, semua direktori secara rekurtif di bawah AZ_BATCH_NODE_ROOT_DIR (akar direktori Azure Batch pada simpul) dipetakan ke dalam wadah, semua variabel lingkungan tugas dipetakan ke dalam wadah, dan baris perintah tugas dijalankan dalam wadah.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSTaskContainerSettings
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DependsOn
Menentukan bahwa tugas bergantung pada tugas lain.
Tugas tidak akan dijadwalkan hingga semua tugas depended-on berhasil diselesaikan.

```yaml
Type: Microsoft.Azure.Batch.TaskDependencies
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Menentukan nama tampilan tugas.

```yaml
Type: System.String
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentSettings
Menentukan pengaturan lingkungan, sebagai pasangan kunci/nilai, yang ditambahkan cmdlet ini ke tugas.
Kuncinya adalah nama pengaturan lingkungan.
Nilainya adalah pengaturan lingkungan.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: JobId_Single, JobObject_Single
Aliases: EnvironmentSetting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExitConditions
```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSExitConditions
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID tugas.

```yaml
Type: System.String
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan pekerjaan di mana cmdlet ini membuat tugas.
Untuk mendapatkan objek **PSCloudJob** , gunakan cmdlet Get-AzureBatchJob.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudJob
Parameter Sets: JobObject_Bulk, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan di mana cmdlet ini membuat tugas.

```yaml
Type: System.String
Parameter Sets: JobId_Single, JobId_Bulk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultiInstanceSettings
Menentukan informasi tentang cara menjalankan tugas multi-instans.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFile
Mendapatkan atau mengatur daftar file yang akan diunggah layanan Batch dari simpul komputasi setelah menjalankan baris perintah.
Untuk tugas multi-instans, file hanya akan diunggah dari simpul komputasi tempat tugas utama dijalankan.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSOutputFile[]
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceFiles
Menentukan file sumber daya, sebagai pasangan kunci/nilai, yang diperlukan tugas.
Kuncinya adalah jalur file sumber daya.
Nilainya adalah sumber blob file sumber daya.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: JobId_Single, JobObject_Single
Aliases: ResourceFile

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tugas
Menentukan kumpulan tugas yang akan ditambahkan.
Setiap tugas harus memiliki ID unik.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudTask[]
Parameter Sets: JobId_Bulk, JobObject_Bulk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserIdentity
Identitas pengguna di mana tugas berjalan.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSUserIdentity
Parameter Sets: JobId_Single, JobObject_Single
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSCloudJob
Parameter: Job (ByValue)

### Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter: BatchContext (ByValue)

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchJob](./Get-AzureBatchJob.md)

[Get-AzureBatchTask](./Get-AzureBatchTask.md)

[AzureBatchTask Baru](./New-AzureBatchTask.md)

[Hapus-AzureBatchTask](./Remove-AzureBatchTask.md)

[Stop-AzureBatchTask](./Stop-AzureBatchTask.md)

[Cmdlet Azure Batch](./AzureRM.Batch.md)


