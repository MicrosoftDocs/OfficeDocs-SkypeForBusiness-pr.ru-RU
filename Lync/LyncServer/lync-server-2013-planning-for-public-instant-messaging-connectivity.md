---
title: 'Lync Server 2013: планирование подключения общедоступной службы обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="859fd-102">Планирование подключения общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="859fd-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="859fd-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="859fd-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="859fd-104">Общедоступная служба обмена мгновенными сообщениями является классом Федерации и настроена на разрешение внутренних и внешних пользователей Lync Server 2013 для добавления контактов из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="859fd-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="859fd-105">Контакты Messenger</span><span class="sxs-lookup"><span data-stu-id="859fd-105">Messenger contacts</span></span>

  - <span data-ttu-id="859fd-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="859fd-106">Yahoo\!</span></span> <span data-ttu-id="859fd-107">контакты,</span><span class="sxs-lookup"><span data-stu-id="859fd-107">contacts</span></span>

  - <span data-ttu-id="859fd-108">Контакты из Skype Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="859fd-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="859fd-109">За Сентябрь 1 сентября 2012 г. Лицензия на подписку на общедоступные пользователи Microsoft Lync (PIC усл) больше не доступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="859fd-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="859fd-110">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="859fd-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="859fd-111">Messenger, пока не зайдет Дата завершения обслуживания.</span><span class="sxs-lookup"><span data-stu-id="859fd-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="859fd-112">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="859fd-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="859fd-113">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="859fd-113">has been announced.</span></span> <span data-ttu-id="859fd-114">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="859fd-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="859fd-115">УСЛ PIC является лицензией на подписку "на пользователя", которая требуется для использования Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="859fd-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="859fd-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="859fd-116">Messenger.</span></span> <span data-ttu-id="859fd-117">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого она не будет продлена.</span><span class="sxs-lookup"><span data-stu-id="859fd-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="859fd-118">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="859fd-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="859fd-119">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="859fd-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="859fd-120">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут получать сотни миллионов людей с помощью голосовой почты и голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="859fd-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="859fd-121">Для этого класса Федерации требуются следующие вопросы планирования:</span><span class="sxs-lookup"><span data-stu-id="859fd-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="859fd-122">Пользователи Windows Live Messenger могут иметь доступ к одноранговой голосовой и видеосвязи с пользователями Lync Server 2013, а также обмениваться мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="859fd-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="859fd-123">Пограничные серверы должны соответствовать конкретным требованиям к порту и протоколу.</span><span class="sxs-lookup"><span data-stu-id="859fd-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="859fd-124">Подробности можно найти [в разделе Определение внешних параметров брандмауэра/V и требований к портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="859fd-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="859fd-125">В обмене сообщениями Yahoo нет уникальных требований, кроме тех, которые обычно используются при планировании и развертывании типичного пограничного сервера, предоставляющего Федерацию.</span><span class="sxs-lookup"><span data-stu-id="859fd-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="859fd-126">Для использования Skype Online требуется, чтобы сертификат пограничного сервера, назначенный службе EDGE, использовал улучшенное использование ключа (EKU).</span><span class="sxs-lookup"><span data-stu-id="859fd-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="859fd-127">Содержание</span><span class="sxs-lookup"><span data-stu-id="859fd-127">In This Section</span></span>

  - [<span data-ttu-id="859fd-128">Сведения о сертификате: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="859fd-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="859fd-129">Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="859fd-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="859fd-130">[Сводка DNS: подключение общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="859fd-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

