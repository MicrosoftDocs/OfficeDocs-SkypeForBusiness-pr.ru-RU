---
title: Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcd352521285e619c9ceeb55a0699b4d4ea73e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-05_

Когда вы подключаетесь к Skype для бизнеса Online с помощью Windows PowerShell, вы можете использовать около 40 командлетов Skype для бизнеса Online. Однако при управлении Skype для бизнеса Online вы можете использовать только те командлеты 40, которые не ограничиваются. Помимо командлетов Skype для бизнеса Online вы также можете использовать любые другие командлеты Windows PowerShell, установленные на компьютере. (При установке Windows PowerShell 3,0 также устанавливаются сотни основных командлетов Windows PowerShell.) Ваши команды могут сочетать и искать командлеты Skype для бизнеса Online и любые другие командлеты, доступные на компьютере.

Несмотря на то, что полный курс в Windows PowerShell 3,0 выходит за рамки этой статьи, вот несколько примеров, в которых объясняется, почему вы можете использовать командлеты для смешивания и сопоставления. Во-первых, ни один из командлетов Skype для бизнеса Online не содержит команду "Печать", и вы не можете найти такую команду на консоли Windows PowerShell. Итак, как получить распечатку информации, полученной командлетом? Один из способов — получить информацию, а затем отправить эту информацию в командлет **Out-Printer** :

    Get-CsTenant | Out-Printer

Поскольку никакие дополнительные параметры не включены, все данные, возвращенные командлетом **Out-Printer** , будут напечатаны на принтере по умолчанию.

Кроме того, ни один из командлетов Skype для бизнеса Online не содержит параметр, позволяющий сохранять данные в файле. Но это нормально: в этой команде используется командлет **Out-File** для сохранения возвращенных данных в текстовом файле C:\\Logs\\. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Эта команда использует командлет **Select-Object** для ограничения возвращаемых данных и отображения на экране. В этом примере командлет [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) извлекает сведения обо всех пользователях Skype для бизнеса Online, а затем — командлет **Select-Object** используется для ограничения отображаемых данных значением удостоверения пользователя и их политикой архивирования.

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Так как на компьютере будут доступны сотни командлетов, может возникнуть ошибка при определении командлетов для использования в качестве командлетов Skype для бизнеса Online, а также в каких из них нет. Чтобы получить список командлетов Skype для бизнеса Online (и только командлетов Skype для бизнеса Online), необходимо сначала определить имя временного модуля Windows PowerShell, содержащего все командлеты Skype для бизнеса Online. Для этого выполните эту команду в командной строке Windows PowerShell:

    Get-Module

На экране будут показаны такие сведения, как показано ниже.

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Модуль с помощью сценария ModuleType — это модуль, который содержит командлеты Skype для бизнеса Online. Чтобы получить список этих командлетов, выполните командлет **Get-Command** , указав в качестве имени модуля имя модуля сценария.

    Get-Command -Module tmp_5astd3uh.m5v

Возможно, у вас есть несколько модулей со значением "ModuleType", равным сценарию. В этом случае вы можете выполнить следующую команду, чтобы узнать, какой модуль содержит командлет **Get-кстенант** :

    Get-Command Get-CsTenant

Модуль, возвращенный для командлета **Get-кстенант** , будет использоваться в качестве модуля, содержащего все командлеты Skype для бизнеса Online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>См. также


[Введение в Windows PowerShell и Skype для бизнеса Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

