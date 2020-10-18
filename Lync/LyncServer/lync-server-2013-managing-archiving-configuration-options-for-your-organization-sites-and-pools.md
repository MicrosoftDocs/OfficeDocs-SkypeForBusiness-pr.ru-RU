---
title: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов'
description: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576625"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы указать способ реализации архивации. Это включает следующие конфигурации архивирования:

  - Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.

  - Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.

Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания. В панели управления Lync Server 2013 вы можете использовать страницу **Конфигурация архивации** группы **Архивация и мониторинга** для управления конфигурациями на глобальном уровне, уровне сайта и на уровне пула. Сведения о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать, а также иерархия конфигураций архивации, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .

<div>


> [!NOTE]  
> Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для всех пользователей, размещенных в Lync Server 2013. По умолчанию архивирование не включено ни для внутренней, ни для внешней связи. При использовании интеграции с Microsoft Exchange необходимо включить и настроить Exchange 2013 для поддержки архивации всех пользователей, размещенных на сервере Exchange 2013 с почтовыми ящиками, на In-Place удержание.<BR>Перед включением архивации необходимо указать соответствующие конфигурации архивации для вашего развертывания и, при необходимости, для определенных узлов и пулов, как описано в этом разделе. Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

**Просмотр сведений о конфигурации архивации с помощью командлетов Windows PowerShell**

  - Сведения о конфигурации архивации можно просмотреть с помощью Windows PowerShell и командлета **Get – CsArchivingConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Чтобы просмотреть сведения о всех параметрах конфигурации архивации, в командной консоли Lync Server используйте следующую команду:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание конфигурации архивации в Lync Server 2013 для управления архивацией определенных сайтов или пулов](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Включение или отключение архивации сеансов обмена мгновенными сообщениями или конференц-связи в Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Включение или отключение очистки архивных данных в Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Включение или отключение критического режима в Lync Server 2013 для блокировки и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации](lync-server-2013-enable-disable-critical-mode.md)

  - [Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Включение или отключение интеграции Lync Server 2013 с хранилищем Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

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

