---
title: 'Lync Server 2013: поддержка единой системы обмена сообщениями Exchange (единой системы обмена сообщениями)'
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
ms.openlocfilehash: 22c65581d76d1622da6b64e0ccaa4e028e276d5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Поддержка единой системы обмена сообщениями Exchange в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange для объединения голосовых сообщений и сообщений электронной почты в единую инфраструктуру обмена сообщениями. В Exchange 2013 единая система обмена сообщениями Exchange состоит из службы единой системы обмена сообщениями Exchange, которая устанавливается и запускается на сервере почтовых ящиков, а также на маршрутизаторе вызовов единой системы обмена сообщениями, установленном и работающем на сервере клиентского доступа. Для развертываний корпоративной голосовой связи в Lync Server 2013 система обмена сообщениями Exchange объединяет обмен голосовыми сообщениями и электронную почту в едином хранилище, доступном с телефона (то есть с помощью голосового доступа к Outlook) или компьютера. Единая система обмена сообщениями Exchange и Lync Server 2013 взаимодействуют для предоставления автоответчика, голосового доступа к Outlook и служб автосекретаря для пользователей корпоративной голосовой связи.

Помимо поддержки интеграции с локальными развертываниями единой системы обмена сообщениями Exchange, Lync Server 2013 поддерживает интеграцию с размещенной единой системой обмена сообщениями Exchange. Это позволяет вам предоставлять возможность обмена голосовыми сообщениями пользователям, если вы выполните миграцию некоторых из них или их всех на поставщика размещенной службы Exchange, такого как Microsoft Exchange Online.

Lync Server 2013 поддерживает следующие версии:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (обязательно) или с последним пакетом обновления (рекомендуется)

  - Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) (обязательно) или последним пакетом обновления (рекомендуется)

Совместное размещение единой системы обмена сообщениями Exchange с Lync Server 2013 или Lync Server 2013 невозможно. Вы можете установить Exchange единой системы обмена сообщениями и Lync Server 2013 в отдельные леса.

<div>


> [!NOTE]  
> Единая система обмена сообщениями Exchange может не потребоваться для развертываний корпоративной голосовой связи с развернутой УАТС, так как УАТС может продолжать предоставлять доступ к голосовой почте и связанным службам всем пользователям. При окончательном отключении УАТС (например, при развертывании магистральной магистрали SIP для подключения к телефонной сети общего пользования) необходимо перенастроить единую систему обмена сообщениями Exchange для предоставления голосовой почты пользователям, которые ранее использовали систему голосовой почты УАТС.



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

