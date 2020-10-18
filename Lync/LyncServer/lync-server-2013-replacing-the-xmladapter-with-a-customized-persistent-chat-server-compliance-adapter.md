---
title: 'Lync Server 2013: замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата'
description: 'Lync Server 2013: замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576145"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Вы можете написать настраиваемый адаптер вместо использования Ксмладаптер, установленного с сервером сохраняемого чата. Для этого необходимо предоставить сборку .NET Framework, содержащую общий класс, который реализует интерфейс **IComplianceAdapter**. Эту сборку необходимо поместить в папку установки сервера сохраняемого чата на каждом сервере в пуле серверов сохраняемого чата. Любой из серверов совместимости может предоставлять данные о совместимости адаптеру, но серверы совместимости не могут предоставлять дублированные данные о совместимости нескольким экземплярам адаптера.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Реализация интерфейса Икомплианцеадаптер

Интерфейс определяется в сборке Compliance.dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance` . В интерфейсе определены два метода, которые должен реализовать настраиваемый адаптер.

    void SetConfig(AdapterConfig config)

Сервер соответствия сохраняемого чата будет вызывать этот метод при первой загрузке адаптера. `AdapterConfig`Содержит конфигурацию соответствия сохраняемого чата, относящуюся к адаптеру соответствия.

    void Translate(ConversationCollection conversations)

Сервер соответствия сохраняемого чата вызывает этот метод через определенные интервалы времени до тех пор, пока не переводятся новые данные. Этот интервал времени равен значению, заданному `RunInterval` в настройках соответствия сохраняемого чата.

`ConversationCollection`Содержит сведения о беседе, собранные при последнем вызове этого метода.

</div>

</div>

<span> </span>

</div>

</div>

</div>

