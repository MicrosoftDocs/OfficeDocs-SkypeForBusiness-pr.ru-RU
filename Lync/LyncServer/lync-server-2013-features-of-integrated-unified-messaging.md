---
title: 'Lync Server 2013: функции интегрированной единой системы обмена сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a>Функции интегрированной единой системы обмена сообщениями и Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Lync Server 2013, корпоративный голосовой интерфейс использует инфраструктуру единой системы обмена сообщениями Exchange для обеспечения ответа на звонки, уведомления о звонках, доступа к голосовой почте (в том числе голосовой почты) и служб автоматического ассистента.

<div>

## <a name="call-answering"></a>Автоответчик

Функция автоответчика обеспечивает прием голосовых сообщений от имени пользователя, который не может ответить на звонок. При этом воспроизводится персональное приветствие и записывается сообщение, которое затем помещается в очередь на доставку в почтовый ящик пользователя, хранящийся на сервере почтовых ящиков Exchange.

Если звонящий оставляет сообщение, оно помещается в ящик входящих сообщений пользователя. Если звонящий решает не оставлять сообщение, в почтовом ящике сохраняется уведомление о пропущенном звонке. Пользователь затем может получить доступ к своему ящику входящих сообщений с помощью клиента обмена сообщениями и совместной работы Microsoft Outlook, Outlook Web Access, технологии Exchange ActiveSync или голосового доступа к Outlook. Темы и приоритет звонков могут отображаться так же, как для электронной почты.

</div>

<div>

## <a name="outlook-voice-access"></a>Outlook Voice Access

Голосовой доступ к Outlook позволяет корпоративному голосовому пользователю получать доступ не только к голосовой почте, но и к почтовому ящику Exchange, в том числе к электронной почте, календарю и контактам из интерфейса телефонной связи. Номер доступа абонента назначается администратором единой системы обмена сообщениями Exchange.

</div>

<div>

## <a name="auto-attendant"></a>Автоматический секретарь

Автосекретарь — это функция единой системы обмена сообщениями Exchange, которую можно использовать для настройки телефонного номера, который пользователи за пределами могут набрать для представителей компании. In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system. Список доступных параметров настраивается администратором единой системы обмена сообщениями Exchange на сервере Exchange UM.

</div>

<div>

## <a name="fax-services"></a>Факсимильные службы

В UM Exchange есть функции факса, позволяющие пользователям принимать входящие факсы в почтовые ящики Exchange. Подробности можно найти в разделе "Единая система обмена сообщениями" в документации [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)по серверу Microsoft Exchange Server по адресу.

<div>


> [!NOTE]  
> Службы факсов, предоставленные сервером Exchange UM, недоступны в развертываниях Lync Server, которые объединены с Microsoft Exchange Server 2010, Exchange 2010 с последним пакетом обновления или Exchange 2013.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

