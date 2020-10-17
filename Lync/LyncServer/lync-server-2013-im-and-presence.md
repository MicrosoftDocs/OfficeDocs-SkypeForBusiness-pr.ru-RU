---
title: Обмен мгновенными сообщениями и присутствие в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26e4b9c2814b8e9e5bf57e2e798b4b803d7401fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507266"
---
# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="dcd96-102">Мгновенные сообщения и сведения о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcd96-102">IM and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcd96-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dcd96-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="dcd96-104">Обмен мгновенными сообщениями и присутствие автоматически устанавливаются в любом развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcd96-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="dcd96-105">Сведения о *присутствии* дают пользователям возможность обращаться к коллегам в правильное время и в правильной форме, что создает более эффективную рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="dcd96-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="dcd96-106">Присутствие пользователя — это набор сведений, включающих сведения о доступности, готовности общаться, дополнительные примечания (например, о местонахождении и состоянии), а также способы контакта.</span><span class="sxs-lookup"><span data-stu-id="dcd96-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="dcd96-107">Сведения о присутствии расширены в Lync Server с изображениями, сведениями о расположении и обширным набором состояний присутствия, включающим "отключенные работы", "не беспокоить" и "Будьте в наличии", а также основные состояния, такие как "доступно", "занято" и "в конференции".</span><span class="sxs-lookup"><span data-stu-id="dcd96-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="dcd96-108">Администраторы также могут определять особые, относящиеся к конкретной организации состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="dcd96-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="dcd96-p102">Параметры управления контактами и доступом пользователей дают пользователям возможность указывать, какие сведения могут видеть остальные. Пользователи могут устанавливать разные уровни контактов, каждый из которых может видеть разные уровни сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="dcd96-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="dcd96-p103">Просто посмотрев на список контактов, пользователи с первого взгляда могут найти все, что им нужно знать. Простые цветные значки указывают состояние присутствия других пользователей; также показываются изображения пользователей и сведения об их местонахождении.</span><span class="sxs-lookup"><span data-stu-id="dcd96-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="dcd96-113">При интеграции Lync Server и других продуктов, таких как Outlook и SharePoint, при появлении имени контакта, например в сообщении электронной почты или на веб-сайте группы, также отображается состояние и контактные данные.</span><span class="sxs-lookup"><span data-stu-id="dcd96-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="dcd96-114">Кроме того, при развертывании Exchange 2013, Lync Server и Exchange 2013 могут совместно использовать единое хранилище контактов, доступное клиентам любой из продуктов.</span><span class="sxs-lookup"><span data-stu-id="dcd96-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="dcd96-115">Благодаря обмену мгновенными сообщениями в Lync Server пользователи могут быстро обмениваться сообщениями с помощью этих сведений.</span><span class="sxs-lookup"><span data-stu-id="dcd96-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="dcd96-116">При желании пользователи также могут общаться с пользователями общедоступных сетей обмена мгновенными сообщениями, таких как MSN/Windows Live, Yahoo \! и AOL.</span><span class="sxs-lookup"><span data-stu-id="dcd96-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="dcd96-117">Обратите внимание, что для подключения к общедоступным службам обмена мгновенными сообщениями с Windows Live, AOL и Yahoo может потребоваться отдельная лицензия.\!</span><span class="sxs-lookup"><span data-stu-id="dcd96-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="dcd96-118">Lync Server также включает в себя совместимость с расширенными сообщениями и протоколом присутствия (XMPP), поэтому пользователи могут обмениваться МГНОВЕНными сообщениями и сведениями о присутствии с пользователями служб XMPP, таких как Google говорите.</span><span class="sxs-lookup"><span data-stu-id="dcd96-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="dcd96-119">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="dcd96-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="dcd96-120">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dcd96-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dcd96-121">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="dcd96-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="dcd96-122">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dcd96-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="dcd96-123">объявлено.</span><span class="sxs-lookup"><span data-stu-id="dcd96-123">has been announced.</span></span> <span data-ttu-id="dcd96-124">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dcd96-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dcd96-125">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dcd96-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="dcd96-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="dcd96-126">Messenger.</span></span> <span data-ttu-id="dcd96-127">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="dcd96-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="dcd96-128">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="dcd96-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dcd96-129">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="dcd96-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="dcd96-130">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="dcd96-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="dcd96-131">Журнал бесед дает пользователям возможность отслеживать старые беседы системы обмена мгновенными сообщениями и извлекать сведения, которые были переданы в мгновенном сообщении несколько месяцев назад.</span><span class="sxs-lookup"><span data-stu-id="dcd96-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="dcd96-132">Функция сохраняемого чата позволяет пользователям участвовать в многосторонних беседах на основе тем, которые сохраняются со временем.</span><span class="sxs-lookup"><span data-stu-id="dcd96-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="dcd96-133">Сообщения, опубликованные в комнатах чата (форумах обсуждений) могут сохраняться, чтобы пользователи из разных мест и отделов могли участвовать в них, даже если они находится в сети не одновременно.</span><span class="sxs-lookup"><span data-stu-id="dcd96-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="dcd96-134">Если организация обязана придерживаться нормативных правил, можно развернуть функцию архивации сообщений, чтобы архивировать содержимое мгновенных сообщений всех пользователей в организации или только отдельных указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="dcd96-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="dcd96-135">Если вы также развертываете Exchange 2013, ваш архив обмена мгновенными сообщениями можно интегрировать с функцией хранения In-Place Exchange, чтобы обеспечить единое административное взаимодействие для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dcd96-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

