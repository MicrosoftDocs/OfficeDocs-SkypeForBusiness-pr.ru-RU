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
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-25_

В этом разделе описаны компоненты Microsoft Exchange Server 2013, необходимые для обеспечения функций единой системы обмена сообщениями Exchange (UM) для развертывания Lync Server 2013. Кроме того, здесь описаны поддерживаемые топологии для локальной интеграции единой системы обмена сообщениями.

<div>

## <a name="exchange-server-components"></a>Компоненты Exchange Server

Для предоставления функций и служб Exchange UM, описанных в [функциях интеграции единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) и корпоративной голосовой связи в Организации, необходимо развернуть сервер почтовых ящиков Microsoft Exchange и сервер клиентского доступа, на котором размещаются почтовые ящики пользователей и есть единое место для хранения электронной почты и голосовой почты. UM Exchange работает как служба на почтовом ящике Exchange и серверах клиентского доступа.

Дополнительные сведения о компонентах UM Exchange в Microsoft Exchange Server 2007 и Microsoft Exchange Server 2010 можно найти в разделе [развертывание локальной системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) в документации по развертыванию.

</div>

<div>

## <a name="supported-topologies"></a>Поддерживаемые топологии

Вы можете развернуть Lync Server 2013 и единую систему обмена сообщениями Exchange (UM) в одном лесе или нескольких лесах. Если развертывание охватывает несколько лесов, необходимо выполнить шаги интеграции Exchange для каждого леса UM Exchange. Кроме того, необходимо настроить каждый лес Microsoft Exchange для доверительных отношений с лесом Lync Server 2013 и лесом сервера Lync Server 2013 для доверительных отношений между каждым лесом Exchange UM. В дополнение к этому доверию лесов параметры Exchange UM для всех пользователей должны быть установлены на объектах пользователей в лесу Lync Server 2013.

Lync Server 2013 поддерживает следующие топологии интеграции Exchange UM.

  - Один лес

  - Один домен (то есть один лес с одним доменом). Lync Server 2013, Microsoft Exchange и пользователи находятся в одном домене.

  - Multiple domain (that is, a root domain with one or more child domains). Сервер Lync Server 2013 и серверы Microsoft Exchange развертываются в разных доменах из домена, где создаются пользователи. Серверы Exchange UM можно разворачивать в разных доменах из пула Lync Server 2013, который они поддерживают.

  - Несколько лесов (то есть лес ресурсов). Lync Server 2013 развернут в одном лесе, и пользователи распределены по нескольким лесам. Атрибуты среды обмена UM для пользователей должны быть реплицированы в лес 2013 для Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Exchange can be deployed in multiple forests. Каждая организация Exchange может предоставлять своим пользователям обмен UM, а Exchange UM может быть развернут в том же лесе, что и Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

