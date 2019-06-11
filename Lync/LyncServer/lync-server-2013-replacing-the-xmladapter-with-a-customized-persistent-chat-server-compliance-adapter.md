---
title: 'Lync Server 2013: замена Ксмладаптер с настроенным адаптером соответствия для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Замена Ксмладаптер с помощью настроенного адаптера соответствия требованиям сервера для подключения к серверу в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Вы можете написать собственный адаптер, вместо того чтобы использовать Ксмладаптер, установленный на сервере сохраняемого чата. Для этого необходимо предоставить сборку .NET Framework, которая содержит общий класс, реализующий интерфейс **IComplianceAdapter**. Эту сборку необходимо поместить в папку установки сервера сохраняемого чата для каждого сервера в пуле сервера сохраняемого чата. Данные проверки совместимости могут поступать в адаптер с любого сервера проверки совместимости, но на разные экземпляры адаптера с серверов проверки совместимости на поступают повторяющиеся данные.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Реализация интерфейса Икомплианцеадаптер

Интерфейс определен в сборке соответствие. dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance`. Интерфейс определяет два метода, которые должен реализовать пользовательский адаптер.

    void SetConfig(AdapterConfig config)

Этот метод будет вызываться при первой загрузке адаптера с помощью постоянного чата. `AdapterConfig` Содержит постоянную конфигурацию соответствия чатов, связанную с адаптером соответствия требованиям.

    void Translate(ConversationCollection conversations)

Сервер соответствия требованиям в чате вызывает этот метод через определенные интервалы времени, пока для перевода не поступило новых данных. Этот интервал времени равен значению, `RunInterval` заданному в параметрах соответствия требованиям сохраняемого чата.

`ConversationCollection` Содержит сведения о разговоре, собранные с момента последнего вызова этого метода.

</div>

</div>

<span> </span>

</div>

</div>

</div>

