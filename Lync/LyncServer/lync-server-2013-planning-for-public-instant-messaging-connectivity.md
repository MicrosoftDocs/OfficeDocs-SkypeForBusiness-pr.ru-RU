---
title: 'Lync Server 2013: планирование подключения к общедоступным службам обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540173ea468947786e2ead4927ccc66eb2f3ceda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526506"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="41584-102">Планирование подключений к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41584-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41584-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="41584-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="41584-104">Общедоступная служба обмена мгновенными сообщениями — это класс Федерации, который позволяет внутренним и внешним пользователям Lync Server 2013 добавлять контакты из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="41584-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="41584-105">Контакты Messenger</span><span class="sxs-lookup"><span data-stu-id="41584-105">Messenger contacts</span></span>

  - <span data-ttu-id="41584-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="41584-106">Yahoo\!</span></span> <span data-ttu-id="41584-107">contacts</span><span class="sxs-lookup"><span data-stu-id="41584-107">contacts</span></span>

  - <span data-ttu-id="41584-108">Контакты America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="41584-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="41584-109">С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="41584-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="41584-110">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="41584-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="41584-111">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="41584-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="41584-112">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="41584-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="41584-113">объявлено.</span><span class="sxs-lookup"><span data-stu-id="41584-113">has been announced.</span></span> <span data-ttu-id="41584-114">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="41584-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="41584-115">УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo!</span><span class="sxs-lookup"><span data-stu-id="41584-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="41584-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="41584-116">Messenger.</span></span> <span data-ttu-id="41584-117">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="41584-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="41584-118">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="41584-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="41584-119">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="41584-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="41584-120">В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="41584-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="41584-121">При планировании для этого класса федерации необходимо учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="41584-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="41584-122">В дополнение к обмену мгновенными сообщениями пользователи Windows Live Messenger могут иметь возможность однорангового аудио-и визуального взаимодействия с пользователями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41584-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="41584-123">Пограничные серверы должны отвечать определенным требованиям к портам и протоколам.</span><span class="sxs-lookup"><span data-stu-id="41584-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="41584-124">Подробнее: [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41584-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="41584-125">Для обмена мгновенными сообщениями Yahoo не предъявляются уникальные требования, кроме тех, которые обычно используются при планировании и развертывании типичного пограничного сервера, обеспечивающего Федерацию.</span><span class="sxs-lookup"><span data-stu-id="41584-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="41584-126">Для работы в Америке Online необходимо, чтобы сертификат пограничного сервера, назначенный пограничной службе доступа, использовал расширенное использование ключа (EKU) клиента.</span><span class="sxs-lookup"><span data-stu-id="41584-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="41584-127">Содержание</span><span class="sxs-lookup"><span data-stu-id="41584-127">In This Section</span></span>

  - [<span data-ttu-id="41584-128">Сводка по сертификатам: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41584-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="41584-129">Сводка по портам — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41584-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="41584-130">[Сводка по DNS — подключение к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="41584-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

