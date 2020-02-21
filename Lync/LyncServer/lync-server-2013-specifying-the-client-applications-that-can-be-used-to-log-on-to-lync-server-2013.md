---
title: 'Lync Server 2013: указание клиентских приложений, которые можно использовать для входа в Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81bae91ba4e9eec75e455ab1b3bc03b45c1a4c96
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="90032-102">Указание клиентских приложений, которые можно использовать для входа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90032-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90032-103">_**Последнее изменение темы:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="90032-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="90032-104">Lync Server 2013 позволяет указать версию клиентов, которые поддерживаются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="90032-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="90032-105">Использование политик версий клиентов помогает снизить затраты, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="90032-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="90032-106">Кроме того, это может привести к улучшению взаимодействия с пользователем, так как при взаимодействии более ранних и последующих версий клиентов доступные функции могут быть ограничены более ранней версией клиента.</span><span class="sxs-lookup"><span data-stu-id="90032-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="90032-107">Существует три компонента системы управления версиями клиентов:</span><span class="sxs-lookup"><span data-stu-id="90032-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="90032-108">Параметры конфигурации версий клиентов используются для включения или отключения управления версиями клиентов (глобально или для определенных сайтов).</span><span class="sxs-lookup"><span data-stu-id="90032-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="90032-109">Политики версий клиентов используются для назначения глобального набора правил, а также для определенного сайта, пула или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="90032-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="90032-110">Правила политики версий клиентов составляют политику версий клиентов и используются для определения действий, которые должны выполняться при попытке пользователей войти в систему с определенными клиентами и версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="90032-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90032-111">Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="90032-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90032-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="90032-112">In This Section</span></span>

  - [<span data-ttu-id="90032-113">Параметры конфигурации версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90032-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="90032-114">Политики версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90032-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="90032-115">Правила версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90032-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90032-116">См. также</span><span class="sxs-lookup"><span data-stu-id="90032-116">See Also</span></span>


[<span data-ttu-id="90032-117">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90032-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

