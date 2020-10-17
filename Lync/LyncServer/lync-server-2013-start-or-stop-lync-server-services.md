---
title: 'Lync Server 2013: запуск или остановка служб Lync Server'
description: 'Lync Server 2013: запуск или остановка служб Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541865"
---
# <a name="start-or-stop-lync-server-2013-services"></a>Запуск и остановка служб Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

Можно использовать панель управления Lync Server для запуска или остановки всех служб Lync Server 2013, работающих на определенном компьютере или для запуска или остановки определенной службы.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Запуск или остановка всех служб Lync Server на компьютере

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013. Вы можете определить, назначена ли роль CsServerAdministrator или CsAdministrator RBAC, выполнив команду, аналогичную следующей:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).

4.  На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.

5.  Щелкните элемент **Action** (Действие).

6.  Щелкните **Start All services** (Запустить все службы) или **Stop All services** (Остановить все службы).

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Запуск или остановка конкретной службы

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).

4.  На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.

5.  Щелкните элемент **Properties** (Свойства).

6.  Отсортируйте список служб, если это необходимо, и щелкните службу, которую хотите запустить или остановить.

7.  Щелкните элемент **Action** (Действие).

8.  Щелкните **Start service** (Запустить службу) или **Stop service** (Остановить службу).

9.  Нажмите кнопку **Закрыть**.

</div>

<div>

## <a name="see-also"></a>См. также


[Предотвращение сеансов для служб в Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

