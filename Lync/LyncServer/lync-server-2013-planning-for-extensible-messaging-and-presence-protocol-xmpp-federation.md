---
title: Планирование интеграции расширенной службы обмена сообщениями и протоколом присутствия (КСМПП)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee0543d36cb43a05042ca4341a837ae10b52051
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Планирование Федерации протоколов обмена сообщениями и присутствия в КСМПП в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Предыдущие версии Lync Server и Office Communications Server предоставили шлюз расширенных сообщений и протоколов доступа (КСМПП), который можно развернуть как отдельную серверную роль, разрешающую Федерацию с помощью КСМППных развертываний. В Microsoft Lync Server 2013 функциональность КСМПП может быть развернута как функция. Функции КСМПП устанавливаются в двух частях: прокси-сервер КСМПП, который работает на пограничном сервере и шлюз КСМПП, который работает на серверах переднего плана.

Развертывание и настройка КСМПП рассматривается при [развертывании внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) вы планируете поддерживать КСМПП в вашей организации, определяя правила порта и протоколов в брандмауэре, настройку сертификатов и добавление записей DNS. В следующих разделах приведены сведения о том, как вам потребуется успешно спланировать КСМПП Федерацию для развертывания.

<div>


> [!IMPORTANT]
> Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Сведения о сертификате — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Общие сведения о DNS — расширяемая Федерация протоколов обмена сообщениями и доступности КСМПП в Lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

