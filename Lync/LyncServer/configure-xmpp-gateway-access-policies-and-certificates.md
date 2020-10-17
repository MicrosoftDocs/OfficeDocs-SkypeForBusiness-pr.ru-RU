---
title: Настройка политик доступа и сертификатов шлюза XMPP
description: Настройте политики доступа к шлюзу XMPP и сертификаты.
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
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549715"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Настройка политик доступа и сертификатов шлюза XMPP

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-15_

Федерация XMPP определяет внешнее развертывание на основе протокола XMPP. Конфигурация XMPP обеспечивает доступ пользователей Lync к пользователям домена XMPP следующими способами:

  - Обмен мгновенными сообщениями и отслеживание присутствия — только личное двустороннее общение

  - Создание федеративных контактов XMPP в клиенте Lync

При настройке политик для поддержки федеративных контактов по протоколу XMPP) политики применяются к пользователям федеративных доменов, но не к пользователям поставщиков услуг обмена мгновенными сообщениями по протоколу SIP (например, Windows Live) или федеративных доменов SIP. Вы настраиваете федеративного партнера XMPP для каждого федеративного домена XMPP, для которого необходимо разрешить взаимодействие и добавление контактов пользователями. После задания политик необходимо настроить сертификаты шлюза XMPP.

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

