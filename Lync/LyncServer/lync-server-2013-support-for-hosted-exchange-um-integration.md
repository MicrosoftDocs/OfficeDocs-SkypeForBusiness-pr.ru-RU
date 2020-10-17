---
title: Lync Server 2013 — поддержка интеграции размещенной единой системы обмена сообщениями Exchange
description: 'Lync Server 2013: поддержка интеграции размещенной единой системы обмена сообщениями Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546324"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Приложение Lync Server 2013 ExUM Routing поддерживает интеграцию с единой системой обмена сообщениями Exchange в локальной среде, где Lync Server 2013 и Exchange единой системы обмена сообщениями устанавливаются локально на предприятии, или с единой системой обмена сообщениями Exchange, размещенной у поставщика услуг, как показано на следующей схеме.

![Развертывание локальной единой системы обмена сообщениями Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной единой системы обмена сообщениями Lync Server Exchange")

Поддерживаются следующие режимы:

  - **Локальный режим**     Lync Server 2013 и служба единой системы обмена сообщениями Exchange развернуты на локальных серверах предприятия.

  - **Перекрестный режим**     Lync Server 2013 развернут на локальных серверах в Организации, а единая система обмена сообщениями Exchange размещается в средстве поставщика веб-служб, например в центре обработки данных Microsoft Exchange Online.

  - **Смешанный режим**     В развертывании Lync Server 2013 есть некоторые почтовые ящики пользователей, размещенные на локальных серверах Microsoft Exchange Server на предприятии, а некоторые почтовые ящики расположены в размещенном центре обработки данных службы Exchange.
    
    <div>
    

    > [!NOTE]  
    > Смешанный режим можно использовать в качестве переходного решения при оценке и поэтапной миграции пользователей в размещенную единую систему обмена сообщениями Exchange, а также в виде постоянного решения, если вы хотите, чтобы некоторые пользователи сохраняли локальные службы единой системы обмена сообщениями после миграции других пользователей.

    
    </div>

Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP* (также называемое *разделенным доменом*). В этой конфигурации как Lync Server 2013, так и сторонний поставщик услуг единой системы обмена сообщениями Exchange могут получать доступ к тому же адресному пространству домена SIP. Для получения дополнительных сведений ознакомьтесь с [разархитектурой Интеграция размещенной единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) в документации по планированию.

</div>

<span> </span>

</div>

</div>

</div>

