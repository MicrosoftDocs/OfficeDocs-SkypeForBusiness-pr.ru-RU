---
title: 'Lync Server 2013: мгновенные сообщения (IM) и присутствие'
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
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="ab9cc-102">Мгновенные сообщения (IM) и присутствие в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab9cc-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab9cc-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ab9cc-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ab9cc-104">Обмен мгновенными сообщениями и присутствие автоматически устанавливаются в любой среде развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="ab9cc-105">Сведения о *присутствии* позволяют пользователям в нужное время подходить к работе с коллегами, чтобы стать более эффективной рабочей средой.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="ab9cc-106">Присутствие пользователя — это набор данных, который включает в себя доступность, готовность к общению, дополнительные заметки (например, расположение и состояние), а также способ связи с пользователем.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="ab9cc-107">Присутствие в Lync Server с изображениями, сведениями о расположении и обширным набором состояний присутствия, включающий "отключенные трудозатраты", "не беспокоить", и "быть справа назад", в дополнение к основным состояниям, таким как "доступно", "занят" и "в конференц-связи".</span><span class="sxs-lookup"><span data-stu-id="ab9cc-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="ab9cc-108">Администраторы также могут определять настраиваемые состояния присутствия, связанные с организациями.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="ab9cc-109">Управление контактами и параметры доступа пользователей позволяют пользователям управлять сведениями, которые могут просматривать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="ab9cc-110">Пользователи могут задавать различные уровни контактов, каждый из которых может просматривать различные уровни сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="ab9cc-111">Просто взгляните на список контактов, пользователи могут найти все, что необходимо для наглядного знания.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="ab9cc-112">Простые цветные значки определяют состояние присутствия другого пользователя, а также отображается изображение и расположение.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="ab9cc-113">Интеграция с Lync Server и другими продуктами, такими как Outlook и SharePoint, при появлении имени контакта, например в сообщении электронной почты или на веб-сайте группы, также отображается состояние и контактные данные.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="ab9cc-114">Кроме того, если вы развертываете Exchange 2013, Lync Server и Exchange 2013 могут совместно использовать единое хранилище контактов, которое может быть доступно клиентам любого продукта.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="ab9cc-115">Благодаря функции обмена мгновенными сообщениями в Lync Server пользователи могут быстро переключаться между ними с помощью актуальных данных.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="ab9cc-116">Если вы предпочитаете, пользователи также смогут общаться с пользователями общедоступных сетей обмена мгновенными сообщениями, таких как\!MSN/Windows Live, Yahoo и AOL.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="ab9cc-117">Обратите внимание, что для общедоступной службы обмена мгновенными сообщениями с Windows Live, AOL и Yahoo может потребоваться отдельная лицензия.\!</span><span class="sxs-lookup"><span data-stu-id="ab9cc-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="ab9cc-118">Lync Server также включает в себя совместимость с помощью расширенного обмена сообщениями и протокола присутствия (КСМПП), чтобы пользователи могли обмениваться сообщениями и сведениями о присутствии с пользователями служб КСМПП, таких как Google чата.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ab9cc-119">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ab9cc-120">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ab9cc-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ab9cc-121">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="ab9cc-122">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ab9cc-123">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-123">has been announced.</span></span> <span data-ttu-id="ab9cc-124">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ab9cc-125">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ab9cc-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-126">Messenger.</span></span> <span data-ttu-id="ab9cc-127">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="ab9cc-128">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ab9cc-129">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ab9cc-130">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ab9cc-131">Журнал бесед позволяет пользователям отслеживать старые текстовые беседы, а также получать информацию, которая могла бы быть передана в сообщении из месяца назад.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="ab9cc-132">Функция сохраняемый чат позволяет пользователям принимать участие в многофакторных беседах, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ab9cc-133">Сообщения, опубликованные в помещениях чатов (дискуссионные форумы), могут быть постоянными (то есть доступны во времени), чтобы люди из разных местоположений и отделов могли участвовать в работе, даже если они не подключены к Интернету одновременно.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="ab9cc-134">Если в вашей организации должны следовать правила соответствия требованиям, вы можете развернуть функцию архивации сообщений, чтобы архивировать содержимое мгновенных сообщений для всех пользователей в организации или только для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="ab9cc-135">Если вы также разворачиваете Exchange 2013, Архив обмена мгновенными сообщениями можно интегрировать с функцией хранение на месте в Exchange, чтобы обеспечить единое администрирование для вашего соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab9cc-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

