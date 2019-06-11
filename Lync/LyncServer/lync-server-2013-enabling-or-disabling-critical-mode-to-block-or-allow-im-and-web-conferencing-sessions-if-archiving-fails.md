---
title: 'Lync Server 2013: Включение и отключение критического режима для блокирования и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>Включение и отключение критического режима в Lync Server 2013 для блокирования и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

В панели управления Lync Server 2013 вы можете включать и отключать критический режим с помощью конфигураций архивации. К ним относятся следующие конфигурации архивации:

  - Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.

  - Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.

Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания. Сведения о способах реализации конфигураций архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, приведены в разделе [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, развертывание Документация или операционные документы.

<div>


> [!NOTE]  
> Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для пользователей, расположенных на Lync Server 2013. По умолчанию архивация не включена для внутренней и внешней связи. Перед включением архивации в любых политиках следует задать соответствующие конфигурации архивации для развертывания и (необязательно) для определенных сайтов и пулов, как описано в этом разделе. Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.<BR>Если вы решите, что после развертывания архивации требуется использовать Exchange Server Integration для хранения данных и файлов на серверах Exchange 2013, а все пользователи находятся на серверах Exchange 2013, необходимо удалить конфигурацию базы данных SQL Server из Ваша топология. Для этого необходимо использовать Topology Builder. Подробнее смотрите в разделе <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных для архивации в Lync Server 2013</A> в документации по эксплуатации.



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>Включение и отключение блокировки сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.

4.  В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.

5.  Для выбора режима архивации в случае сбоя установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.

6.  Щелкните **Исполнить**.

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>Включение и отключение критического режима с помощью командлетов Windows PowerShell

Вы можете включить или отключить критический режим с помощью командлета **Set-ксарчивингконфигуратион** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-enable-critical-mode"></a>Включение критического режима

  - Чтобы включить критический режим, установите для свойства Блокконарчивефаилуре значение true ($True). Например:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>Отключение критического режима

  - Чтобы отключить критический режим, установите для свойства Блокконарчивефаилуре значение false ($False). Например:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Изменение параметров базы данных для архивации в Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  


[Как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

