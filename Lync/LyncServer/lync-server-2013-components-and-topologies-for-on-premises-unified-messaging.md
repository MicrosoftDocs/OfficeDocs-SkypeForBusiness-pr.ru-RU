---
title: 'Lync Server 2013: компоненты и топологии для локальной единой системы обмена сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543af1cc9b4dbb437b36273945f9f2cb6112c6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-25_

В этом разделе описываются компоненты Microsoft Exchange Server 2013, необходимые для обеспечения возможности единой системы обмена сообщениями Exchange в развертывании Lync Server 2013. Здесь также описываются поддерживаемые топологии для локальной интеграции единой системы обмена сообщениями Exchange.

<div>

## <a name="exchange-server-components"></a>Компоненты Exchange Server

Для предоставления функций и служб единой системы обмена сообщениями Exchange, описанных в статье [функции интегрированной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) , пользователям корпоративной голосовой связи в Организации необходимо развернуть сервер почтовых ящиков и сервер клиентского доступа Microsoft Exchange, на котором размещаются почтовые ящики пользователей, а также одно место хранения для электронной почты и голосовой почты. Единая система обмена сообщениями Exchange работает как служба на серверах почтовых ящиков Exchange и серверах клиентского доступа.

Дополнительные сведения о компонентах единой системы обмена сообщениями Exchange в Microsoft Exchange Server 2007 и Microsoft Exchange Server 2010 приведены в статье [развертывание локальной единой системы обмена сообщениями Exchange для предоставления пользователю Lync Server 2013 голосовой почты](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) в документации по развертыванию.

</div>

<div>

## <a name="supported-topologies"></a>Поддерживаемые топологии

Вы можете развернуть Lync Server 2013 и единую систему обмена сообщениями Exchange (UM) в одном лесу или нескольких лесах. Если развертывание охватывает несколько лесов, необходимо выполнить действия по интеграции Exchange для каждого леса единой системы обмена сообщениями Exchange. Кроме того, необходимо настроить каждый лес Microsoft Exchange так, чтобы он доверял лесу Lync Server 2013 и лесу Lync Server 2013 доверять каждому лесу единой системы обмена сообщениями Exchange. В дополнение к этому доверию лесов параметры Exchange единой системы обмена сообщениями для всех пользователей должны быть установлены для объектов User в лесу Lync Server 2013.

Lync Server 2013 поддерживает следующие топологии интеграции с единой системой обмена сообщениями Exchange:

  - один лес;

  - Один домен (то есть один лес с одним доменом). Lync Server 2013, Microsoft Exchange и пользователи находятся в одном домене.

  - Несколько доменов (корневой домен с одним или несколькими дочерними доменами). Lync Server 2013 и Microsoft Exchange Server развернуты в разных доменах из домена, в котором создаются пользователи. Серверы единой системы обмена сообщениями Exchange можно развертывать в разных доменах из пула Lync Server 2013, который они поддерживают.

  - Несколько лесов (то есть лес ресурсов). Lync Server 2013 развернут в отдельном лесу, а затем пользователи распределены по нескольким лесам. Атрибуты единой системы обмена сообщениями пользователей Exchange необходимо реплицировать в лес Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange можно развертывать в нескольких лесах. Каждая организация Exchange может предоставлять пользователям единую систему обмена сообщениями Exchange, а единая система обмена сообщениями Exchange может быть развернута в том же лесу, что и Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

