---
title: 'Lync Server 2013: поддержка единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Поддержка единой системы обмена сообщениями Exchange в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange (UM) для комбинирования голосовой почты и обмена сообщениями в одной инфраструктуре обмена сообщениями. В Exchange 2013 система обмена сообщениями Exchange состоит из службы Exchange UM, установленной на сервере почтовых ящиков и работающей на нем, а также на маршрутизаторе вызовов UM, установленном и работающем на сервере клиентского доступа. Для развертываний корпоративных голосовых решений Lync Server 2013 в едином хранилище, которое может быть доступно с телефона (то есть с помощью голосового доступа к Outlook) или компьютера, можно объединить сообщения электронной почты Exchange. Обмен UM и Lync Server 2013 работают вместе для обеспечения ответа на звонки, голосового доступа к Outlook и служб автосекретаря для пользователей корпоративной голосовой связи.

Помимо поддержки интеграции с локальными развертываниями единой системы обмена сообщениями Exchange, Lync Server 2013 поддерживает интеграцию с размещенной единой системой обмена сообщениями Exchange. Это позволит вам предоставлять пользователям голосовой почты, если вы перенесете некоторые или все их в размещенный поставщик услуг Exchange, например Microsoft Exchange Online.

Lync Server 2013 поддерживает следующие версии:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (обязательно) или последний пакет обновления (рекомендуется)

  - Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) (обязательно) или последним пакетом обновления (рекомендуется)

Вы не можете разгруппировать единую систему обмена сообщениями Exchange с помощью Lync Server 2013 или базы данных Lync Server 2013. Вы можете установить Exchange UM и Lync Server 2013 в отдельных лесах.

<div>


> [!NOTE]  
> Exchange UM может не потребоваться для развертывания корпоративных голосовых систем с развернутой АТС, так как УАТС может продолжать предоставлять всем пользователям голосовую почту и связанные службы. Если вы захотите отключить УАТС (например, при развертывании магистральной магистрали SIP для подключения по коммутируемой телефонной сети), необходимо заново настроить сервер UM для предоставления голосовой почты пользователям, которые ранее использовали систему голосовой почты УАТС.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

