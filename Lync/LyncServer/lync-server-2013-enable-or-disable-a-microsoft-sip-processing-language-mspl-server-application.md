---
title: 'Lync Server 2013: Включение или отключение серверного приложения Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9efa0fb6e0ab1cce452ecccfdc5c63d795f3a0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Включение и отключение серверного приложения Microsoft SIP Processing Language (MSPL) в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

С помощью панели управления Lync Server можно включать и отключать серверные приложения Microsoft SIP Processing Language (MSPL), выполняемые в среде Lync Server 2013. Эти приложения представляют собой приложения на основе сценариев, которые вместо Microsoft Lync 2013 Preview API используют язык сценариев.

Не все сценарии могут быть включены или отключены. Например, сценарий DefaultRouting включен и это значение нельзя изменить.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Включение или отключение серверного приложения MSPL

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Topology** (Топология) и затем щелкните **Server Application** (Серверное приложение).

4.  На странице **Server Application** (Серверное приложение) щелкните заголовок столбца, чтобы отсортировать приложения при необходимости, и затем выберите серверное приложение, которое нужно изменить.

5.  Щелкните меню **Action** (Действие).

6.  Щелкните **Enable application** (Включить приложение) или **Disable application** (Отключить приложение) (если сценарий поддерживает этот параметр).

</div>

<div>

## <a name="see-also"></a>См. также


[Помечает приложение Microsoft SIP Process Language (MSPL) как критическое или некритическое в Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

