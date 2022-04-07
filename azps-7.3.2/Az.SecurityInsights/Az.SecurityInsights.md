---
Module Name: Az.SecurityInsights
Module Guid: 453d4fb9-65ec-4cf1-8358-6a0fbd995d19
Download Help Link: https://docs.microsoft.com/powershell/module/az.securityinsights
Help Version: 1.1.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Az.SecurityInsights.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Az.SecurityInsights.md
ms.openlocfilehash: 136c6911a8fb713e2de09562fe70ad75721ca19c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140554579"
---
# Az.SecurityInsights Module
## Deskripsi
Microsoft Azure Sentinel adalah solusi scalable, cloud-native, security information event management (AUTOMAT) dan security orchestration automated response (SOAR). Azure Sentinel menghadirkan analitik keamanan cerdas dan kecerdasan ancaman di seluruh perusahaan, menyediakan satu solusi untuk deteksi peringatan, visibilitas ancaman, pencarian proaktif, dan respons ancaman.<br/> Modul PowerShell Azure Sentinel (Az.SecurityInsights) memungkinkan Anda berinteraksi dengan komponen berikut ini: * Insiden * Aturan Analitik (Aturan Peringatan)
* Templat Aturan Analitik
* Tindakan Aturan Analitik (seperti melampirkan Playbooks Azure Logic Apps ke aturan Anda)
* Bookmark
* Konektor Data
* Komentar

Semua cmdlet dapat bekerja dengan objek koneksi untuk menyediakan sumber dayaGroupName dan workspaceName seperti dalam contoh berikut ini:

## Cmdlet Az.SecurityInsights
### [Get-AzSentinelAlertRule](Get-AzSentinelAlertRule.md)
Mendapatkan aturan analitik tertentu atau semua (Aturan Pemberitahuan).

### [Get-AzSentinelAlertRuleAction](Get-AzSentinelAlertRuleAction.md)
Mendapatkan Respons Otomatis (Tindakan Aturan Pemberitahuan) untuk Aturan Analitik, seperti Azure Logic Apps Playbook.<br/>
Aturan Otomatisasi Azure Sentinel akan didukung di masa mendatang.

*Catatan: Hal ini memerlukan nilai parameter "AlertRuleId"*

### [Get-AzSentinelAlertRuleTemplate](Get-AzSentinelAlertRuleTemplate.md)
Mendapatkan Templat Aturan Analitik.

### [Get-AzSentinelBookmark](Get-AzSentinelBookmark.md)
Mendapatkan Bookmark. <br/>
Bookmark digunakan untuk mempertahankan kueri, komentar, dan tag untuk insiden tertentu.<br/>
Buat Bookmark terlebih dahulu, lalu tambahkan ke insiden.

### [Get-azsentinelDataConnector](Get-AzSentinelDataConnector.md)
Mendapatkan Konektor Data. <br/><br/>
Harap diperhatikan bahwa dukungan otomatisasi hanya tersedia untuk konektor data berikut ini:
* AADDataConnector
* AATPDataConnector
* ASCDataConnector
* AwsCloudTrailDataConnector
* MCASDataConnector
* MDATPDataConnector
* OfficeDataConnector
* TIDataConnector

### [Get-AzSentinelIncident](Get-AzSentinelIncident.md)
Dapatkan satu atau beberapa Insiden Azure Sentinel.

### [Get-AzSentinelIncidentComment](Get-AzSentinelIncidentComment.md)
Mendapatkan Komentar Insiden.

### [New-AzSentinelAlertRule](New-AzSentinelAlertRule.md)
Membuat Aturan Analitik (Aturan Pemberitahuan).

### [New-AzSentinelAlertRuleAction](New-AzSentinelAlertRuleAction.md)
Menambahkan Respons Otomatis ke Aturan Analitik.

### [New-AzsentinelBookmark](New-AzSentinelBookmark.md)
Membuat Bookmark untuk insiden tertentu.<br/>

### [New-azsentinelDataConnector](New-AzSentinelDataConnector.md)
Membuat Konektor Data.

### [New-AzSentinelIncident](New-AzSentinelIncident.md)
Membuat Insiden.

### [New-AzSentinelIncidentComment](New-AzSentinelIncidentComment.md)
Menambahkan Komentar ke Insiden.

### [New-AzSentinelIncidentOwner](New-AzSentinelIncidentOwner.md)
Membuat objek Pemilik Insiden untuk memperbarui pemilik insiden.

### [Remove-AzSentinelAlertRule](Remove-AzSentinelAlertRule.md)
Menghapus Aturan Analitik (AlertRule)

### [Remove-AzSentinelAlertRuleAction](Remove-AzSentinelAlertRuleAction.md)
Menghapus Respons Otomatis dari Aturan Analitik.

### [Remove-AzSentinelBookmark](Remove-AzSentinelBookmark.md)
Menghapus Bookmark.

### [Remove-azsentinelDataConnector](Remove-AzSentinelDataConnector.md)
Menghapus Konektor Data.

### [Remove-AzSentinelIncident](Remove-AzSentinelIncident.md)
Menghapus Insiden.

### [Update-AzSentinelAlertRule](Update-AzSentinelAlertRule.md)
Memperbarui Aturan Analitik (Aturan Pemberitahuan).

### [Update-AzSentinelAlertRuleAction](Update-AzSentinelAlertRuleAction.md)
Memperbarui Respons Otomatis (Tindakan Aturan Pemberitahuan).

### [Update-AzSentinelBookmark](Update-AzSentinelBookmark.md)
Memperbarui Bookmark.

### [Update-azsentinelDataConnector](Update-AzSentinelDataConnector.md)
Memperbarui Konektor Data.

### [Update-AzSentinelIncident](Update-AzSentinelIncident.md)
Memperbarui Insiden

