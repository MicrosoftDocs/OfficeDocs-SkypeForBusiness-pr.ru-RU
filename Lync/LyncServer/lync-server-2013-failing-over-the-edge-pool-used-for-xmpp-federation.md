---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для федерации XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

В вашей организации используется один пул краев, назначенный пулом для КСМПП Федерации. Если этот пул отключается, необходимо отдать отказ на КСМПП Федерацию для использования другого пула Edge перед тем, как КСМПП Федерация сможет снова работать.

После установки пулов EDGE и включения КСМПП Федерации вы можете упростить процесс аварийного восстановления, настроив внешние записи DNS SRV для всех пулов Edge для КСМПП Федерации, а не только для одной из них. Для каждой из этих записей SRV должен быть установлен другой приоритет. Весь трафик Федерации КСМПП проходит через пул с записью SRV с самым высоким приоритетом. Дополнительные сведения о том, как включить и настроить федерацию КСМПП, можно найти [в разделе Настройка КСМПП Федерации в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

В описанной ниже процедуре EdgePool1 — пул, изначально размещенный КСМПП Federation, и EdgePool2 — пул, который теперь будет размещен КСМПП Федерации.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Сбой в пуле EDGE, используемом для Федерации КСМПП

1.  Если вы еще не развернули другой пул пограничных кромок (Кроме того, который в данный момент не работает), разверните этот пул. Подробные сведения можно найти [в разделе Развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  На каждом пограничном сервере в новом пограничном пуле, на котором будет размещена КСМПП Федерация (EdgePool2), запустите следующий командлет:
    
        Stop-CsWindowsService

3.  Чтобы перенаправить маршрут Федерации КСМПП на EdgePool2, выполните следующий командлет:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    В этом примере Site2 — сайт с пулом EDGE, который теперь будет размещаться на маршруте Федерации КСМПП, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.

4.  На внешнем DNS-сервере измените запись DNS A для Федерации КСМПП, чтобы она указывала на EdgeServer2.contoso.com.

5.  Если у вас еще нет DNS-записи SRV для Федерации КСМПП, которая разрешается в пул EDGE, который теперь будет размещаться в КСМПП Федерации, необходимо добавить его, как показано в следующем примере. Для этой записи SRV должно быть задано значение Port 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Убедитесь, что в пуле EDGE, на котором будет размещена КСМПП Федерация, есть порт 5269, Открытый извне.

7.  Запустите службы на всех пограничных серверах в пограничном пуле, где будет размещаться Федерация КСМПП:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

