---
title: 'Lync Server 2013: Настройка поддерживаемых версий клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14bc6decfea38151d1f060b13fa55c81006e98e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Настройка поддерживаемых клиентских версий в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-14_

В Lync Server 2013 можно настроить политики версии клиента, чтобы указать версии клиентов, которые поддерживаются в вашей среде. Кроме того, вы можете использовать конфигурацию глобальной версии клиента, чтобы указать действие по умолчанию для клиентов, у которых нет определенной политики версий, и поэтому они явно не поддерживаются или не ограничены.

Вы также можете использовать политики версии клиента для управления обновлениями клиентов. Если вы настроили политику версии клиента и с помощью параметров **разрешены и обновлены** и заблокированы и **обновлены**, клиенты будут получать обновленное программное обеспечение от службы обновления Windows Server (если вы используете эту службу) или из центра обновления Майкрософт.

<div>

## <a name="client-version-policy-settings"></a>Параметры политики версии клиента

Политика версии клиента по умолчанию требует, чтобы все клиенты выполняли Lync. Если на клиентах вашей среды запущены более ранние версии Communicator, может потребоваться перенастройка правил клиентской версии, чтобы предотвратить неожиданное блокирование и обновление клиентов и устройств при подключении к Lync Server 2013. Вы можете изменить правило по умолчанию или добавить правило, находящихся выше в списке политики версии клиента, для переопределения правила по умолчанию. Кроме того, как выпускаются накопительные обновления (КУС), необходимо настроить политику версии клиента, чтобы затребовать последние обновления. Подробные сведения о том, как [указать клиентские приложения, которые можно использовать для входа на Lync Server 2013,](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) находятся в документации по эксплуатации.

</div>

</div>

<span> </span>

</div>

</div>

</div>

