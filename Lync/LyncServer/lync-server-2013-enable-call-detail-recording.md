---
title: 'Lync Server 2013: включение записи сведений о вызовах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309d96d6aacd5409aa285ddeb4b95837ca98e302
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528796"
---
# <a name="enable-call-detail-recording-in-lync-server-2013"></a>Включение регистрации вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.

Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.

<div>


> [!NOTE]  
> Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см <A href="lync-server-2013-deploying-monitoring.md">в разделе Deploying Monitoring in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>Включение CDR с помощью панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Мониторинг и архивация**, затем **Служба регистрации вызовов**.

4.  На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.
    
    <div>
    

    > [!NOTE]  
    > По умолчанию функция CDR включена.

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Включение CDR с помощью командлетов Windows PowerShell

Вы можете включить CDR с помощью Windows PowerShell и командлета **Set – CsCdrConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>Включение CDR для отдельного места

  - Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>Чтобы отключить CDR для отдельного места

  - Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не приводит к удалению мониторинга. Он приостанавливает сбор и хранение данных CDR.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия

  - Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование мониторинга в Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

