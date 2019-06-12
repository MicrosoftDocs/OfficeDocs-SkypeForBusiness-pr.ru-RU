---
title: 'Lync Server 2013: поддержка интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Приложение Lync Server 2013 Ексум поддерживает интеграцию с единой системой обмена сообщениями Exchange (UM) в локальной среде, где Lync Server 2013 и Exchange UM установлены локально внутри организации, или в единой системе обмена сообщениями Exchange, размещенной на поставщик услуг, как показано на приведенной ниже схеме.

![Развертывание локальной системы обмена сообщениями на сервере Lync Server] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной системы обмена сообщениями на сервере Lync Server")

Поддерживаются перечисленные ниже режимы.

  - **Локальный режим**   Lync Server 2013 и Exchange разворачиваются на локальных серверах в пределах организации.

  - **Одноранговый режим**   Lync Server 2013 развернут на локальных серверах в рамках предприятия, а UM-среде Exchange — в средстве поставщика Интернет-услуг, например в центре обработки данных Microsoft Exchange Online.

  - **Смешанный режим**   сервер Lync Server 2013 имеет некоторые почтовые ящики пользователей, расположенные на локальных серверах Microsoft Exchange Server, а некоторые почтовые ящики расположены в центре обработки данных служб Exchange.
    
    <div>
    

    > [!NOTE]  
    > Смешанный режим можно использовать в качестве переходного решения во время оценки и степвисе миграции пользователей на размещенную систему обмена СООБЩЕНИЯми Exchange или как постоянное решение, если вы не хотите, чтобы некоторые пользователи работали в локальной среде обмена СООБЩЕНИЯми после миграции других пользователей.

    
    </div>

Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP* (также называемое *разделенным доменом*). В этой конфигурации как в Lync Server 2013, так и в поставщике служб UM стороннего поставщика могут получить доступ к тому же адресному пространству домена SIP. Подробности можно найти [в разделе Архитектура интеграции единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) в документации по планированию.

</div>

<span> </span>

</div>

</div>

</div>

