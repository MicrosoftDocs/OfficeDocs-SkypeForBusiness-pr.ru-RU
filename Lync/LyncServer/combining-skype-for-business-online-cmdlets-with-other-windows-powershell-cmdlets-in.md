---
title: Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в
description: Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd18f60891d48a54eb2f77f189ea8417e0b5e93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548005"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-05_

При подключении к Skype для бизнеса Online с помощью Windows PowerShell около 40 командлетов Skype для бизнеса Online будут доступны для использования. Однако при управлении Skype для бизнеса Online не ограничено использование только этих командлетов 40. Кроме командлетов Skype для бизнеса Online, вы также можете использовать любые другие командлеты Windows PowerShell, установленные на компьютере. (При установке Windows PowerShell 3,0 также устанавливаются сотни основных командлетов Windows PowerShell.) Команды могут сочетать и сопоставлять командлеты Skype для бизнеса Online, а также любые другие командлеты, доступные на вашем компьютере.

Несмотря на то, что полный курс в Windows PowerShell 3,0 выходит за рамки этой статьи, здесь представлено несколько примеров, в которых показано, что вы можете использовать командлеты для сочетания и сравнения. Во-первых, ни один из командлетов Skype для бизнеса Online не включает команду "Печать", поэтому в консоли Windows PowerShell не удается найти такую команду:. Как получить распечатку информации, полученной командлетом? Один способ получить сведения, а затем отправить их в командлет **Out-Printer** :

    Get-CsTenant | Out-Printer

Так как дополнительные параметры не включены, все данные, возвращенные командлетом **Out-Printer** , будут распечатаны на принтере по умолчанию.

Аналогично, ни один из командлетов Skype для бизнеса Online не содержит параметр, позволяющий сохранять данные в файл. Но это нормально: Эта команда использует командлет **Out – File** для сохранения возвращенных данных в текстовом файле C: \\ logs \\Tenants.txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Эта команда использует командлет **Select-Object** для ограничения данных, возвращаемых и отображаемых на экране. В этом примере командлет [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) получает сведения обо всех пользователях Skype для бизнеса Online, а затем используется командлет **Select-Object** , чтобы ограничить отображаемые данные значением удостоверения пользователя и их политикой архивации:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Так как на компьютере будут доступны сотни командлетов, может быть трудно определить, какие командлеты используются в командлетах Skype для бизнеса Online, а какие нет. Чтобы получить список командлетов Skype для бизнеса Online (и только командлетов Skype для бизнеса Online), сначала необходимо определить имя временного модуля Windows PowerShell, содержащего все командлеты Skype для бизнеса Online. Чтобы сделать это, запустите эту команду в командной строке Windows PowerShell:

    Get-Module

На экране будут отображаться следующие сведения:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Модуль с скриптом ModuleType — это модуль, который содержит командлеты Skype для бизнеса Online. Чтобы получить список этих командлетов, выполните командлет **Get – Command** , используя имя модуля скрипта в качестве имени модуля:

    Get-Command -Module tmp_5astd3uh.m5v

Возможно, у вас может быть несколько модулей со значением ModuleType, равным сценарию. В этом случае можно выполнить следующую команду, чтобы узнать, какой модуль включает командлет **Get – CsTenant** :

    Get-Command Get-CsTenant

Модуль, возвращенный для командлета **Get-CsTenant** , будет модулем, содержащим все командлеты Skype для бизнеса Online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>См. также


[Введение в Windows PowerShell и Skype для бизнеса Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

