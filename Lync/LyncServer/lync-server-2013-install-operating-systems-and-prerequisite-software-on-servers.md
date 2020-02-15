---
title: Установка операционных систем и необходимого программного обеспечения на серверы
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24441af263d9ebd73f61d350f898e26fa89e6f48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Установка операционных систем и необходимого программного обеспечения на серверы для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-07-24_

После настройки аппаратной и системной инфраструктуры необходимо установить соответствующие операционные системы и обновления Windows в дополнение ко всем необходимым программным обеспечением на каждом развертываемом сервере. Сюда входят все роли сервера Lync Server 2013 и все дополнительные серверы инфраструктуры или серверы SQL Server, необходимые для развертывания.

<div>


> [!NOTE]
> В этом разделе описывается установка операционных систем и необходимого программного обеспечения для внутренних серверов. Если вы развертываете пограничные серверы для поддержки доступа внешних пользователей, вам также потребуется установить операционные системы и необходимое программное обеспечение для этих серверов, в том числе пограничных серверов и обратных прокси-серверов. Подробнее о подготовке серверов к поддержке доступа внешних пользователей можно узнать в статье <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в сети периметра для Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Установка операционных систем Windows на серверах

На каждом развертываемом сервере установите соответствующую операционную систему Windows следующим образом.

  - **Серверы, на которых работает Lync Server 2013**   дополнительные сведения о требованиях к операционной системе для серверов, на которых работает Lync Server 2013, приведены в статье поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

  - **Серверы баз данных**   дополнительные сведения о требованиях к операционной системе для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, представлены в документации по SQL Server. Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)по адресу.

<div>


> [!NOTE]
> При установке Lync Server 2013 на Windows Server&nbsp;2008&nbsp;R2 с пакетом обновления 1 (SP1) необходимо сначала установить обновление, описанное в статье базы знаний Майкрософт 2646886, "исправить: повреждение кучи возникает, когда модуль вызывает метод InsertEntityBody Method в службах IIS 7,5", где <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>Кроме того, необходимо внести изменения в реестр, как описано в статье базы знаний, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">идентификаторы событий 32402, 61045 заносятся в журнал на серверах переднего плана Lync Server 2013, установленных в Windows server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Установка центра обновления Windows на серверах

Установите на каждом сервере следующие обновления из центра обновления Windows:

  - **Обновление Windows для серверов, на которых работает Lync Server 2013**   для получения сведений об обновлениях из центра обновления Windows, необходимых для серверов с Lync Server 2013, ознакомьтесь с [дополнительными требованиями к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

  - **Серверы баз данных**   для получения сведений об обновлениях из центра обновления Windows, которые необходимы для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, ознакомьтесь с документацией по SQL Server 2012. Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)по адресу.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Установка другого необходимого программного обеспечения на серверах

Lync Server 2013 требует установки следующего дополнительного программного обеспечения на серверах:

  - **Необходимое программное обеспечение для серверов, на которых работает Lync Server 2013**   дополнительные требования к программному обеспечению для серверов, на которых работает Lync Server 2013, зависят от развертываемой роли сервера. Сведения о конкретных требованиях к программному обеспечению для каждого сервера приведены в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

  - ****   Для поддержки сценариев проверки подлинности между серверами в Windows Identity Foundation Lync Server 2013 требуется установка Windows Identity Foundation. Чтобы проверить, установлена ли эта платформа уже на компьютере, откройте панель управления, щелкните **Программы и компоненты**, **Просмотр установленных обновлений** и убедитесь в наличии Windows Identity Foundation в разделе **Microsoft Windows**. Подробные сведения об установке Windows Identity Foundation можно найти [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)в разделе.

  - **Microsoft .NET Framework 4,5**   для Lync Server 2013 необходим 64-разрядный выпуск Microsoft .NET Framework 4,5.

  - **Необходимое программное обеспечение для серверов**   баз данных дополнительные сведения об обновлении Windows, которое необходимо для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)представлены в документации по SQL Server 2012.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 автоматически устанавливает Microsoft SQL Server 2012 Express на каждом сервере Standard Edition и на каждом сервере, на котором работает Lync Server 2013, на котором расположено локальное хранилище конфигурации.

    
    </div>

  - **Среда выполнения**   формата Windows Media для всех серверов переднего плана и серверов Standard Edition, на которых будет развертываться конференция, должна быть установлена среда выполнения формата Windows Media Format. Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.
    
    <div>
    

    > [!NOTE]
    > Для Windows Server 2012 и Windows Server 2012 R2 среда выполнения Windows Media Format устанавливается вместе с Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Для Windows Server&nbsp;2008 и windows Server&nbsp;2008&nbsp;R2 среда выполнения формата Windows Media устанавливается в составе рабочего стола Windows. Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013. Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

