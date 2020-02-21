---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для Федерации XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee795b6f4dd1f3ff1077fb739cad9709b2c8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

В организации присутствует только один пограничный пул, назначенный  качестве пула для федерации XMPP. Если этот пул перестанет работать, необходимо выполнить отработку отказа федерации XMPP для использования другого пограничного пула, чтобы федерация XMPP снова начала функционировать.\

При первой установке пограничных пулов и включении федерации XMPP можно упростить процедуру аварийного восстановления путем определения внешних SRV-записей DNS для всех пограничных пулов федерации XMPP, а не только одного. Каждая из этих SRV-записей должна содержать собственное значение приоритета. Весь трафик федерации XMPP проходит через пул с SRV-записью, имеющей наивысший приоритет. Дополнительные сведения о включении и настройке Федерации XMPP можно найти [в статье Настройка Федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

В следующей процедуре EdgePool1 — это пул, в котором изначально была размещена федерация XMPP, а EdgePool2 — пул, в котором будет размещена федерация XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Отработка отказа пограничного пула, используемого для федерации XMPP

1.  Если другой пограничный пул еще не развернут (т. е. единственный пограничный пул в настоящее время не работает), разверните новый пул. Дополнительную информацию можно узнать [в статье Развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  На каждом пограничном сервере в новом пограничном пуле, который теперь размещает федерацию XMPP EdgePool2), запустите следующий командлет:
    
        Stop-CsWindowsService

3.  Выполните следующий командлет, чтобы переопределить маршрут федерации XMPP на сервер EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    В этом примере Site2 — это сайт, содержащий пограничный пул, который в настоящее время содержит пограничный пул, через который проходит маршрут федерации XMPP, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.

4.  На внешнем DNS-сервере измените запись узла A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.

5.  Если отсутствует SRV-запись федерации XMPP, которая разрешается в адрес пограничного пула, поддерживающего в настоящее время федерацию XMPP, необходимо добавить ее, как показано в следующем примере. В этой SRV-записи необходимо указать значение порта 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Убедитесь, что на внешнем интерфейсе пограничного пула, в котором теперь размещена федерация XMPP, открыт порт 5269.

7.  Запустите службу на всех пограничных серверах в пограничном пуле, содержащем федерацию XMPP:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

