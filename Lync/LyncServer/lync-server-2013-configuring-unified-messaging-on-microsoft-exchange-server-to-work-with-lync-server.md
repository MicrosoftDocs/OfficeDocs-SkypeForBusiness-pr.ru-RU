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
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Настройка единой системы обмена сообщениями на сервере Microsoft Exchange Server для работы с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Если вы хотите использовать единую систему обмена сообщениями Exchange для обеспечения ответа на звонки, голосового доступа к Outlook или служб автоматического ассистента для пользователей корпоративной голосовой связи, читайте <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">план интеграции единой системы обмена сообщениями в Lync Server 2013</A> в документации по планированию, а затем следуйте инструкциям, приведенным в этом разделе.



</div>

Чтобы настроить единую систему обмена сообщениями Exchange для работы с корпоративной голосовой связью, необходимо выполнить указанные ниже действия.

  - Настройка сертификатов на сервере, на котором запущены службы единой системы обмена сообщениями Exchange
    
    <div>
    

    > [!NOTE]  
    > Добавляйте все серверы клиентского доступа и почтовых ящиков ко всем абонентам SIP URI для UM. Если нет, Маршрутизация исходящих вызовов не будет работать должным образом.

    
    </div>

  - Создайте одну или несколько абонентов SIP с помощью URI для обмена сообщениями, а также с телефонными номерами абонентов, а затем создайте соответствующие абонентские планы Lync Server.

  - С помощью сценария **ексчукутил. ps1** вы можете:
    
      - Создание IP-шлюзов UM.
    
      - Создание групп слежения UM.
    
      - Предоставьте Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory UM.

  - Создайте объект автоматического ассистента UM.

  - Создайте объект абонентского доступа.

  - Создание универсального кода ресурса (URI) SIP для каждого пользователя и сопоставление пользователей с помощью абонентской группы SIP URI.

<div>

## <a name="requirements-and-recommendations"></a>Требования и рекомендации

Прежде чем приступить к работе, в документации в этом разделе предполагается, что вы развернули следующие роли Exchange 2013: клиентский доступ и почтовый ящик. В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями Exchange работает в качестве службы на этих серверах.

Дополнительные сведения о развертывании Exchange 2013 можно найти в библиотеке Exchange 2013 TechNet по адресу[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Также обратите внимание на следующее:

  - Если в нескольких лесах установлено приложение Exchange UM, для каждого леса UM необходимо выполнить инструкции интеграции с Exchange Server. Кроме того, каждый лес UM необходимо настроить для доверия к лесу, в котором развернут сервер Lync Server 2013, и в лесу, в котором развернут Lync Server 2013, должен быть настроен для доверия к каждому лесу UM.

  - Этапы интеграции выполняются как на ролях сервера Exchange, так и на серверах, на которых работает служба единой системы обмена сообщениями, а также на сервере с Lync Server 2013. Перед выполнением шагов интеграции Lync Server 2013 необходимо выполнить инструкции интеграции с единой системой обмена сообщениями Exchange Server.
    
    <div>
    

    > [!NOTE]  
    > Чтобы узнать, какие этапы интеграции выполняются на каких серверах и для каких ролей администратора, ознакомьтесь со статьей <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</A>.

    
    </div>

Следующие средства должны быть доступны на каждом сервере, на котором запущена служба единой системы обмена сообщениями Exchange.

  - Консоль управления Exchange

  - Сценарий **ексчукутил. ps1**, который выполняет следующие задачи:
    
      - Создает IP-шлюз UM для каждого сервера Lync Server 2013.
    
      - Создание группы слежения для каждого шлюза. Идентификатор пилотной программы для каждой из групп слежения указывает абонентскую группу UM SIP, используемую интерфейсным пулом или сервером Standard Edition, который связан с шлюзом.
    
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

