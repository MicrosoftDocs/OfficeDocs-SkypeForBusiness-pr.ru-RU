---
title: 'Lync Server 2013: помечает приложение Microsoft SIP Processing Language (MSPL) как критическое или некритическое'
description: 'Lync Server 2013: помечает приложение Microsoft SIP Processing Language (MSPL) как критическое или некритическое.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f59fb6614416c1b0e4f49a766a1373483f509d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556555"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Помечает приложение Microsoft SIP Process Language (MSPL) как критическое или некритическое в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Серверные приложения Microsoft SIP Processing Language (MSPL) — это приложения, предназначенные только для скриптов, использующие язык сценариев MSPL, а не API Microsoft Lync 2010. Некоторые серверные приложения MSPL указаны как критичные. Если скрипт является критически важным, он должен начаться во время запуска системы для запуска Lync Server 2013. Если произошел сбой сценария во время работы Lync Server, сервер не завершает работу, но перестает передавать трафик скрипту и записывает ошибки в журнал событий.

С помощью панели управления Lync Server вы можете пометить серверные приложения Microsoft SIP Processing Language (MSPL) как критические или снять их пометки.

Данную возможность поддерживают не все сценарии. Например, сценарий DefaultRouting помечен как критичный, и изменить этот параметр для сценария DefaultRouting нельзя.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Пометка серверного приложения MSPL как критичного и отмена пометки

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Topology** (Топология) и затем щелкните **Server Application** (Серверное приложение).

4.  На странице **Server Application** (Серверное приложение) щелкните заголовок столбца, чтобы отсортировать приложения при необходимости, и затем выберите серверное приложение, которое нужно изменить.

5.  Щелкните элемент **Action** (Действие).

6.  Щелкните элемент **Mark as critical** (Пометить как критичный) или **Unselect as critical** (Отменить пометку) (если сценарий поддерживает эту возможность).

</div>

<div>

## <a name="see-also"></a>См. также


[Включение и отключение серверного приложения Microsoft SIP Processing Language (MSPL) в Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

