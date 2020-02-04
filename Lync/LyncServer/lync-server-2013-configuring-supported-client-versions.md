---
title: 'Lync Server 2013: Настройка поддерживаемых версий клиента'
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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="7c162-102">Настройка поддерживаемых клиентских версий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c162-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c162-103">_**Тема последнего изменения:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="7c162-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="7c162-104">В Lync Server 2013 можно настроить политики версии клиента, чтобы указать версии клиентов, которые поддерживаются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="7c162-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="7c162-105">Кроме того, вы можете использовать конфигурацию глобальной версии клиента, чтобы указать действие по умолчанию для клиентов, у которых нет определенной политики версий, и поэтому они явно не поддерживаются или не ограничены.</span><span class="sxs-lookup"><span data-stu-id="7c162-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="7c162-106">Вы также можете использовать политики версии клиента для управления обновлениями клиентов.</span><span class="sxs-lookup"><span data-stu-id="7c162-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="7c162-107">Если вы настроили политику версии клиента и с помощью параметров **разрешены и обновлены** и **заблокированы и обновлены**, клиенты будут получать обновленное программное обеспечение от службы обновления Windows Server (если вы используете эту службу) или из центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7c162-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="7c162-108">Параметры политики версии клиента</span><span class="sxs-lookup"><span data-stu-id="7c162-108">Client Version Policy Settings</span></span>

<span data-ttu-id="7c162-109">Политика версии клиента по умолчанию требует, чтобы все клиенты выполняли Lync.</span><span class="sxs-lookup"><span data-stu-id="7c162-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="7c162-110">Если на клиентах вашей среды запущены более ранние версии Communicator, может потребоваться перенастройка правил клиентской версии, чтобы предотвратить неожиданное блокирование и обновление клиентов и устройств при подключении к Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c162-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="7c162-111">Вы можете изменить правило по умолчанию или добавить правило, находящихся выше в списке политики версии клиента, для переопределения правила по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c162-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="7c162-112">Кроме того, как выпускаются накопительные обновления (КУС), необходимо настроить политику версии клиента, чтобы затребовать последние обновления.</span><span class="sxs-lookup"><span data-stu-id="7c162-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="7c162-113">Подробные сведения о том, как [указать клиентские приложения, которые можно использовать для входа на Lync Server 2013,](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) находятся в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7c162-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

