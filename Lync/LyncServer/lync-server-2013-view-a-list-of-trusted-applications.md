---
title: 'Lync Server 2013: Просмотр списка доверенных приложений'
description: 'Lync Server 2013: Просмотр списка доверенных приложений.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d45c682550640c3fc7284e0b60ca6844896b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574795"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Просмотр списка доверенных приложений в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Вы можете использовать панель управления Lync Server 2013 для просмотра списка доверенных приложений, развернутых в среде Lync Server 2013. Доверенное приложение — это приложение, основанное на Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Lync Server 2013. В списке ниже приведены сведения об этом отношении доверия.

  - Доверенные приложения не вызывают проверку подлинности Lync Server.

  - Доверенные приложения не регулируется сервером Lync Server для транзакций SIP, подключений или исходящих звонков по протоколу VoIP.

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

В панели управления Lync Server можно просмотреть имена приложений, пула, в котором они выполняются, и порт, который они используют.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Из учетной записи пользователя, назначенной для роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании. Подробные сведения о предопределенных административных ролях, доступных в Lync Server 2013, приведены в статье [Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Топология**, а затем **Доверенное приложение**.

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).

</div>

<div>

## <a name="see-also"></a>См. также


[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

