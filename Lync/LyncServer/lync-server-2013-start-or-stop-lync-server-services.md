---
title: 'Lync Server 2013: запуск и остановка служб Lync Server'
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
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Запуск и остановка служб Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

С помощью панели управления Lync Server можно запускать и останавливать все службы Lync Server 2013, запущенные на конкретном компьютере, а также запускать и останавливать определенную службу.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Запуск и остановка всех служб Lync Server на компьютере

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013. Вы можете определить, назначена ли вам роль Кссерверадминистратор или Ксадминистратор RBAC, выполнив команду, подобную следующей:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева щелкните **топология** и выберите **состояние**.

4.  На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущены службы, которые вы хотите запустить или остановить, а затем щелкните его.

5.  Нажмите кнопку **действие**.

6.  Нажмите кнопку **начать все службы** или **остановить все службы**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Запуск и остановка определенной службы

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева щелкните **топология** и выберите **состояние**.

4.  На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущена служба, которую вы хотите запустить или остановить, а затем щелкните ее.

5.  Нажмите кнопку **Свойства**.

6.  При необходимости отсортируйте список служб и выберите службу, которую вы хотите запустить или остановить.

7.  Нажмите кнопку **действие**.

8.  Нажмите кнопку **запустить службу** или **остановить службу**.

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

