---
title: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В панели управления Lync Server 2013 вы можете настроить способ реализации архивации с помощью конфигураций архивации. К ним относятся следующие конфигурации архивации:

  - Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.

  - Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.

Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания. В панели управления Lync Server 2013 можно использовать страницу **Конфигурация архивации** в группе Архивация **и мониторинг** для управления конфигурациями на глобальном уровне, уровне сайта и уровне пула. Сведения о том, как работают конфигурации архивации, в том числе доступные для выбора параметры и иерархию конфигураций архивации, описаны [в разделе как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, развертывание Документация или операционные документы.

<div>


> [!NOTE]  
> Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для всех пользователей, расположенных на Lync Server 2013. По умолчанию архивация не включена для внутренней и внешней связи. Если вы используете Microsoft Exchange Integration, вы должны включить и настроить Exchange 2013 для поддержки архивирования для всех пользователей, использующих Exchange 2013 с почтовыми ящиками, которые помещаются на хранение на месте.<BR>Перед включением архивации следует задать соответствующие конфигурации архивации для развертывания и, при необходимости, для определенных сайтов и пулов, как описано в этом разделе. Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

**Просмотр сведений о конфигурации архивации с помощью командлетов Windows PowerShell**

  - Вы можете просматривать сведения о конфигурации архивации с помощью Windows PowerShell и командлета **Get-ксарчивингконфигуратион** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.
    
    В командной консоли Lync Server выполните следующую команду, чтобы просмотреть сведения о всех параметрах конфигурации архивирования.
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание конфигурации архивации в Lync Server 2013 для управления архивированием определенных сайтов и пулов](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Включение и отключение архивирования сеансов обмена мгновенными сообщениями и конференц-связи в Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Включение и отключение очистки архивированных данных в Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Включение и отключение критического режима в Lync Server 2013 для блокирования и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Включение и отключение отправки отказа от архивирования федеративным партнерам в Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Включение и отключение интеграции Lync Server 2013 с хранилищем Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Удаление конфигурации архивации в Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Управление архивированием Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

