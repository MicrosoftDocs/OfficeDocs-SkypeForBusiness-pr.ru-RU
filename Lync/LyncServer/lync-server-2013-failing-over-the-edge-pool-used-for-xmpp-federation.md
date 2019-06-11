---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для федерации XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f1c0e-102">Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1c0e-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1c0e-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f1c0e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f1c0e-104">В вашей организации используется один пул краев, назначенный пулом для КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="f1c0e-105">Если этот пул отключается, необходимо отдать отказ на КСМПП Федерацию для использования другого пула Edge перед тем, как КСМПП Федерация сможет снова работать.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="f1c0e-106">После установки пулов EDGE и включения КСМПП Федерации вы можете упростить процесс аварийного восстановления, настроив внешние записи DNS SRV для всех пулов Edge для КСМПП Федерации, а не только для одной из них.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="f1c0e-107">Для каждой из этих записей SRV должен быть установлен другой приоритет.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="f1c0e-108">Весь трафик Федерации КСМПП проходит через пул с записью SRV с самым высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="f1c0e-109">Дополнительные сведения о том, как включить и настроить федерацию КСМПП, можно найти [в разделе Настройка КСМПП Федерации в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="f1c0e-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="f1c0e-110">В описанной ниже процедуре EdgePool1 — пул, изначально размещенный КСМПП Federation, и EdgePool2 — пул, который теперь будет размещен КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="f1c0e-111">Сбой в пуле EDGE, используемом для Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="f1c0e-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="f1c0e-112">Если вы еще не развернули другой пул пограничных кромок (Кроме того, который в данный момент не работает), разверните этот пул.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="f1c0e-113">Подробные сведения можно найти [в разделе Развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f1c0e-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="f1c0e-114">На каждом пограничном сервере в новом пограничном пуле, на котором будет размещена КСМПП Федерация (EdgePool2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f1c0e-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="f1c0e-115">Чтобы перенаправить маршрут Федерации КСМПП на EdgePool2, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f1c0e-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="f1c0e-116">В этом примере Site2 — сайт с пулом EDGE, который теперь будет размещаться на маршруте Федерации КСМПП, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="f1c0e-117">На внешнем DNS-сервере измените запись DNS A для Федерации КСМПП, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="f1c0e-118">Если у вас еще нет DNS-записи SRV для Федерации КСМПП, которая разрешается в пул EDGE, который теперь будет размещаться в КСМПП Федерации, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="f1c0e-119">Для этой записи SRV должно быть задано значение Port 5269.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="f1c0e-120">Убедитесь, что в пуле EDGE, на котором будет размещена КСМПП Федерация, есть порт 5269, Открытый извне.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="f1c0e-121">Запустите службы на всех пограничных серверах в пограничном пуле, где будет размещаться Федерация КСМПП:</span><span class="sxs-lookup"><span data-stu-id="f1c0e-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

