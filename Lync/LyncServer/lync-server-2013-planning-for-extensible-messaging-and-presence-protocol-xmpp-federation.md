---
title: Планирование Федерации Extensible Messaging and Presence Protocol (XMPP)
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
ms.openlocfilehash: 4308bd09d571c41349ed9362affa220cf9723e3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526536"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Планирование Федерации XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Предыдущие версии Lync Server и Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с развертываниями XMPP. В Microsoft Lync Server 2013 функция XMPP может быть развернута в качестве компонента. Функции XMPP устанавливаются в двух частях: прокси-сервер XMPP, выполняющийся на пограничном сервере, и шлюз XMPP, работающий на серверах переднего плана.

Развертывание и Настройка XMPP рассматривается в разделе [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) вы планируете поддерживать XMPP в Организации, определяя правила портов и протоколов в брандмауэре, настройку сертификатов и добавление записей DNS. В следующих подразделах этого раздела приводится сводка сведений, необходимых для успешного планирования Федерации XMPP для развертывания.

<div>


> [!IMPORTANT]
> Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите. Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Сводка по сертификатам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Сводка по портам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Сводка по DNS — Федерация XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка Федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Настройка политик для управления доступом федеративных пользователей XMPP в Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))  
[Get — CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))  
[Get — Ксксмппгатевайконфигуратион](https://technet.microsoft.com/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

