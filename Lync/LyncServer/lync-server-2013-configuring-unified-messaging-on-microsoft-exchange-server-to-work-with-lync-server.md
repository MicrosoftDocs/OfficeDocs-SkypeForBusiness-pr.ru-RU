---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange Server для работы с Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3d90f738741c2815d01041a7d2293e978cd2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Настройка единой системы обмена сообщениями на сервере Microsoft Exchange Server для работы с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Если вы хотите использовать единую систему обмена сообщениями Exchange для предоставления автоответчика, голосового доступа к Outlook или служб автосекретаря для пользователей корпоративной голосовой связи, ознакомьтесь с разделом <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</A> в документации по планированию, а затем следуйте инструкциям, приведенным в этом разделе.



</div>

Чтобы настроить единую систему обмена сообщениями Exchange для работы с корпоративной голосовой связью, необходимо выполнить следующие задачи:

  - Настройка сертификатов на сервере, на котором запущены службы единой системы обмена сообщениями Exchange
    
    <div>
    

    > [!NOTE]  
    > Добавить все серверы клиентского доступа и почтовых ящиков во все абонентские группы URI для SIP единой системы обмена сообщениями. В противном случае маршрутизация исходящих вызовов не сможет работать ожидаемым образом.

    
    </div>

  - Создайте одну или несколько абонентских групп URI SIP с единой системой обмена сообщениями, а также номера телефонов абонентского доступа, если необходимо, а затем создайте соответствующие абонентские группы Lync Server.

  - С помощью сценария **exchucutil.ps1**:
    
      - создать IP-шлюзы единой системы обмена сообщениями;
    
      - создать сервисные группы единой системы обмена сообщениями;
    
      - Предоставьте Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory единой системы обмена сообщениями.

  - создать объект автосекретаря единой системы обмена сообщениями;

  - создать объект абонентского доступа;

  - создать URI для SIP для каждого пользователя и связать пользователей с абонентской группой SIP единой системы обмена сообщениями.

<div>

## <a name="requirements-and-recommendations"></a>Требования и рекомендации

Прежде чем приступать к работе, в документации в этом разделе предполагается, что вы развернули следующие роли Exchange 2013: клиентский доступ и почтовый ящик. В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями Exchange работает как служба на этих серверах.

Подробнее о развертывании Exchange 2013 можно узнать в библиотеке Exchange 2013 TechNet по адресу[https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

Также обратите внимание на следующее.

  - Если единая система обмена сообщениями установлена в нескольких лесах, для каждого леса единой системы обмена сообщениями необходимо выполнить интеграцию с Exchange Server. Кроме того, каждый лес единой системы обмена сообщениями должен быть настроен для доверия лесу, в котором развернут Lync Server 2013, и лес, в котором развернут Lync Server 2013, должен быть настроен для доверия каждого леса единой системы обмена сообщениями.

  - Этапы интеграции выполняются как в ролях сервера Exchange, где выполняются службы единой системы обмена сообщениями, так и на сервере, на котором работает Lync Server 2013. Перед выполнением интеграции Lync Server 2013 необходимо выполнить действия по интеграции единой системы обмена сообщениями Exchange Server.
    
    <div>
    

    > [!NOTE]  
    > Чтобы узнать, какие действия по интеграции выполняются на серверах и ролях администраторов, ознакомьтесь со статьей <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</A>.

    
    </div>

На каждом сервере, на котором запущена служба единой системы обмена сообщениями Exchange, должны быть доступны следующие средства:

  - командная консоль Exchange;

  - сценарий **exchucutil.ps1**, выполняющий следующие задачи:
    
      - Создает шлюз IP единой системы обмена сообщениями для каждого сервера Lync Server 2013.
    
      - Создает сервисную группу для каждого шлюза. Пилотный идентификатор каждой сервисной группы указывает абонентскую группу универсального кода ресурса (URI) SIP единой системы обмена сообщениями, которую использует интерфейсный пул или сервер Standard Edition, связанный с шлюзом.
    
      - Предоставляет Lync Server 2013 разрешение на чтение объектов единой системы обмена сообщениями Exchange в доменных службах Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

