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
ms.openlocfilehash: cecc551eef4cb7574674c9f7de39f27b4efc8710
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517396"
---
# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="c81f2-102">Настройка поддерживаемых версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81f2-102">Configuring supported client versions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c81f2-103">_**Последнее изменение темы:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="c81f2-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="c81f2-104">В Lync Server 2013 можно настроить политики версий клиентов, чтобы указать версии клиентов, которые поддерживаются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="c81f2-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="c81f2-105">Если для некоторых клиентов политика версий не задана (не поддерживаются явно и не запрещаются явно), то задайте действие по умолчанию для этих клиентов с помощью глобальной конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="c81f2-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="c81f2-p102">С помощью политик версий клиентов можно управлять обновлениями клиентов. Если при задании политики версий клиентов вы используете параметры **Allow and upgrade** (Разрешить и обновить) и **Block and upgrade** (Блокировать и обновить), то клиенты будут получать обновления программного обеспечения от служб Windows Server Update Services (при использовании) или из Центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c81f2-p102">You can also use client version policies to manage client updates. When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="c81f2-108">Параметры политик версий клиентов</span><span class="sxs-lookup"><span data-stu-id="c81f2-108">Client Version Policy Settings</span></span>

<span data-ttu-id="c81f2-109">Политика версий клиентов по умолчанию требует, чтобы все клиенты выполняли Lync.</span><span class="sxs-lookup"><span data-stu-id="c81f2-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="c81f2-110">Если клиенты в вашей среде работают с более ранними версиями Communicator, может потребоваться перенастройка правил версий клиентов, чтобы предотвратить неожиданное блокирование и обновление клиентов и устройств при подключении к Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c81f2-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="c81f2-111">В этом случае измените правило по умолчанию или добавьте правило на более высокую позицию списка политик версий клиентов, чтобы переопределить правило по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c81f2-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="c81f2-112">Кроме того, по мере выхода накопительных обновлений вам потребуется настроить политику версий клиентов для получения последних обновлений.</span><span class="sxs-lookup"><span data-stu-id="c81f2-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="c81f2-113">Сведения о том, как [указать клиентские приложения, которые можно использовать для входа в Lync Server 2013,](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="c81f2-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

