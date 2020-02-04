---
title: 'Lync Server 2013: Просмотр списка надежных приложений'
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
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Просмотр списка надежных приложений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Вы можете использовать панель управления Lync Server 2013 для просмотра списка доверенных приложений, развернутых в среде Lync Server 2013. Надежное приложение — это приложение, основанное на управляемом наборе API Microsoft Unified Communications (УКМА 3,0), который является надежным для Lync Server 2013. Это отношение доверия представлено в следующем списке.

  - Доверенные приложения не предназначены для проверки подлинности на сервере Lync Server.

  - Доверенные приложения не заменяются на Lync Server для транзакций SIP, подключений и исходящих голосовых вызовов по протоколу VoIP.

  - Доверенные приложения могут олицетворять любого пользователя и могут присоединиться к конференциям без отображения в списке.

  - Доверенные приложения являются высокодоступными и устойчивыми.

На панели управления Lync Server вы можете просматривать имена приложений, пула, в которых они выполняются, и используемого ими порта.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка надежных приложений

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator. Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти [в разделе Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева щелкните **топология** и выберите пункт **доверенное приложение**.

4.  На странице **Trusted Application (доверенное приложение** ) щелкните заголовок столбца, чтобы отсортировать приложения, если это необходимо.

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

