---
title: 'Lync Server 2013: Настройка поддерживаемых версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc604efae64d907879ad175b13d7fec9c6b9d99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Настройка поддерживаемых версий клиентов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-14_

В Lync Server 2013 можно настроить политики версий клиентов, чтобы указать версии клиентов, которые поддерживаются в вашей среде. Если для некоторых клиентов политика версий не задана (не поддерживаются явно и не запрещаются явно), то задайте действие по умолчанию для этих клиентов с помощью глобальной конфигурации версий клиентов.

С помощью политик версий клиентов можно управлять обновлениями клиентов. Если при задании политики версий клиентов вы используете параметры **Allow and upgrade** (Разрешить и обновить) и **Block and upgrade** (Блокировать и обновить), то клиенты будут получать обновления программного обеспечения от служб Windows Server Update Services (при использовании) или из Центра обновления Майкрософт.

<div>

## <a name="client-version-policy-settings"></a>Параметры политик версий клиентов

Политика версий клиентов по умолчанию требует, чтобы все клиенты выполняли Lync. Если клиенты в вашей среде работают с более ранними версиями Communicator, может потребоваться перенастройка правил версий клиентов, чтобы предотвратить неожиданное блокирование и обновление клиентов и устройств при подключении к Lync Server 2013. В этом случае измените правило по умолчанию или добавьте правило на более высокую позицию списка политик версий клиентов, чтобы переопределить правило по умолчанию. Кроме того, по мере выхода накопительных обновлений вам потребуется настроить политику версий клиентов для получения последних обновлений. Сведения о том, как [указать клиентские приложения, которые можно использовать для входа в Lync Server 2013,](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) в документации по операциям.

</div>

</div>

<span> </span>

</div>

</div>

</div>

