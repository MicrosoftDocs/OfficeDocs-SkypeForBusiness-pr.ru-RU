---
title: 'Lync Server 2013: поддержка общедоступных мгновенных сообщений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f996e8f15707a0c676ea77a6ffaeb5e6943ac48c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="99fb0-102">Общедоступная поддержка обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99fb0-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99fb0-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="99fb0-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="99fb0-104">Lync Server 2013 поддерживает использование лицензированных поставщиков услуг подключения к общедоступным службам обмена мгновенными сообщениями, а также использование протокола XMPP для реализации специального типа Федерации, который позволяет серверу Lync получать доступ к настроенным XMPP Партнеры по доменам с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="99fb0-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="99fb0-105">Поддержка поставщиком возможности подключения к общедоступным службам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="99fb0-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="99fb0-106">В настоящее время поддерживаются следующие партнеры по возможности подключения к общедоступным службам обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="99fb0-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="99fb0-107">America Online</span><span class="sxs-lookup"><span data-stu-id="99fb0-107">America Online</span></span>

  - <span data-ttu-id="99fb0-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="99fb0-108">Windows Live</span></span>

  - <span data-ttu-id="99fb0-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="99fb0-109">Yahoo\!</span></span>

<span data-ttu-id="99fb0-110">Для связи с пользователями Windows Live Lync Server 2013 поддерживает одноранговые обмен мгновенными сообщениями, а также вызовы аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="99fb0-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="99fb0-111">Для обмена данными с AOL и\!Yahoo Lync Server 2013 поддерживает одноранговые мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="99fb0-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="99fb0-112">Может потребоваться отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="99fb0-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="99fb0-113">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="99fb0-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="99fb0-114">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="99fb0-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="99fb0-115">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="99fb0-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="99fb0-116">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="99fb0-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="99fb0-117">объявлено.</span><span class="sxs-lookup"><span data-stu-id="99fb0-117">has been announced.</span></span> <span data-ttu-id="99fb0-118">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99fb0-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="99fb0-119">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="99fb0-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="99fb0-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="99fb0-120">Messenger.</span></span> <span data-ttu-id="99fb0-121">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="99fb0-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="99fb0-122">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="99fb0-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="99fb0-123">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="99fb0-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="99fb0-124">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="99fb0-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="99fb0-125">Поддержка федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="99fb0-125">XMPP Federation Support</span></span>

<span data-ttu-id="99fb0-p105">Федерация XMPP поддерживает взаимодействие пользователей Lync с настроенными пользователями домена XMPP, использующими общедоступного поставщика, такого как GTalk. Коммуникации с такими пользователями могут включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="99fb0-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="99fb0-128">Одноранговый обмен мгновенными сообщениями и сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="99fb0-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="99fb0-129">Создание федеративных контактов XMPP в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="99fb0-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

