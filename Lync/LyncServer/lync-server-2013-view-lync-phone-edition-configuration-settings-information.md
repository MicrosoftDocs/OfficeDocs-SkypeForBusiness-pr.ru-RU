---
title: 'Lync Server 2013: Просмотр сведений о параметрах конфигурации Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 509bc25e6466e4e6f90271645b2a3a8ff271bd84
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Просмотр сведений о параметрах конфигурации Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете просмотреть сведения о конфигурации устройств, на которых работает Lync Phone Edition. Эти данные объединены в коллекции. При установке Lync Server вы получаете коллекцию параметров Lync Phone Edition, которые применяются ко всем устройствам с Lync Phone Edition в вашем развертывании. Также можно создать новые коллекции настройки для отдельного сайта. Настройки сайта имеют приоритет перед глобальными настройками. Каждая коллекция настроек содержит имя, область (глобальная область или область сайта), параметр безопасности SIP, уровень ведения журнала, уровень качества обслуживания при использовании голосовой связи, данные о блокировке телефона, минимальную длину персонального идентификационного номера (ПИН-кода), а также интервал автоматической блокировки телефона.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Просмотр сведений о конфигурации устройств с Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.

4.  На странице **Конфигурация устройства** щелкните коллекцию настроек, данные о которых требуется просмотреть. Имя, область, параметр безопасности SIP, уровень качества голосовой связи и параметры блокировки телефона перечислены на главной странице. Для просмотра данных об уровне ведения журнала и сведений о блокировке телефона щелкните меню **Правка** и нажмите **Показать подробности**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell

Параметры конфигурации Lync Phone Edition можно просмотреть с помощью командной консоли Lync Server и командлета **Get – CsUCPhoneConfiguration** . Вы можете запустить этот командлет из командной консоли Lync Server 2013 Management Shell или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Просмотр сведений о конфигурации Lync Phone Edition

  - Чтобы просмотреть сведения обо всех параметрах конфигурации Lync Phone Edition, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsUCPhoneConfiguration
    
    Команда возвращает данные в следующем виде:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Дополнительные сведения см. в статье [Get – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Принудительная Блокировка телефона в Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

