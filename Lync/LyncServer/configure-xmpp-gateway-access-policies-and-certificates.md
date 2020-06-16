---
title: Настройка политик доступа и сертификатов шлюза XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Настройка политик доступа и сертификатов шлюза XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - Обмен мгновенными сообщениями и отслеживание присутствия — только личное двустороннее общение

  - Создание федеративных контактов XMPP в клиенте Lync

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

<div>


> [!NOTE]  
> Чтобы начать миграцию шлюза XMPP, необходимо развернуть шлюз Lync Server 2013 XMPP и настроить политики доступа, чтобы разрешить пользователям использовать шлюз Lync Server 2013 XMPP. Перед выполнением этих действий все пользователи должны быть перемещены в развертывание Lync Server 2013. Дополнительные сведения: <A href="configure-xmpp-gateway-on-lync-server-2013.md">Настройка шлюза XMPP в Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Настройка политики внешнего доступа для разрешения доступа пользователей к шлюзу XMPP Lync Server 2013

1.  Откройте Панель управления Lync Server.

2.  На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **External Access Policy** (Политика внешнего доступа).

3.  Щелкните **New** (Создать), а затем щелкните **User policy** (Пользовательская политика).

4.  Введите имя для политики внешнего доступа пользователей.

5.  Добавьте описание политики внешнего доступа пользователей.

6.  Выберите **Enable communications with federated users** (Разрешить взаимодействие с федеративными пользователями).

7.  Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).

8.  Щелкните **Commit** (Сохранить), чтобы сохранить изменение политики сайта или пользователей.

</div>

</div>

<span> </span>

</div>

</div>

</div>

