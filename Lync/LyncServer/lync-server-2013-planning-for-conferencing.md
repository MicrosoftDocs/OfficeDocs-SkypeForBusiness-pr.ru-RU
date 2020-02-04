---
title: 'Lync Server 2013: планирование конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b7813a197dd7cc3116540c605d7efbdb22a04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9ec17-102">Планирование конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ec17-103">_**Тема последнего изменения:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="9ec17-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="9ec17-104">Lync Server 2013 имеет широкий набор возможностей для конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="9ec17-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="9ec17-105">Веб-конференции, в том числе взаимодействие с документами, общий доступ к приложениям и совместный доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="9ec17-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="9ec17-106">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="9ec17-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="9ec17-107">Подробнее об установке и настройке сервера Office Web Apps можно узнать в разделе [Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9ec17-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="9ec17-108">Голосовая или видеосвязь (A/V), позволяющая пользователям использовать голосовые и видеоконференции в реальном времени, не требуя использования внешних служб, таких как служба Microsoft Live Meeting или независимый звуковой мост.</span><span class="sxs-lookup"><span data-stu-id="9ec17-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="9ec17-109">Конференц-связь с телефонным подключением, благодаря которой пользователи могут присоединиться к звуковой части конференции Lync Server 2013 с помощью коммутируемого телефона с коммутируемой телефонной сетью, не требуя от стороннего поставщика услуг голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9ec17-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="9ec17-110">Конференц-связь с помощью мгновенных сообщений, в которой более двух сторон обмениваются данными в одном сеансе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9ec17-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="9ec17-111">Подробные сведения о конференц-связи можно найти [в разделе Планирование серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="9ec17-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="9ec17-112">Lync Server 2013 поддерживает как запланированные конференции, так и конференции незапланированное.</span><span class="sxs-lookup"><span data-stu-id="9ec17-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="9ec17-113">При развертывании Lync Server 2013, сервер переднего плана вы можете выбрать, следует ли также развертывать веб-конференции, Конференции и возможности конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9ec17-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="9ec17-114">Возможности конференц-связи с СООБЩЕНИЯми всегда развертываются автоматически вместе с возможностями обмена мгновенными сообщениями на серверах переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ec17-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ec17-115">Если в развертывании есть собрания, упорядоченные с помощью клиентов Office Communicator 2007 R2 (включая консоль Live Meeting или надстройка конференц-связи для Microsoft Office Outlook), после миграции в Lync эти собрания будут иметь указанные ниже ограничения. Сервер 2013:</span><span class="sxs-lookup"><span data-stu-id="9ec17-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9ec17-116">Пользователи на собрании не смогут использовать возможности совместной работы с данными, в том числе совместную работу с документами, общий доступ к приложениям и совместный доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="9ec17-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="9ec17-117">Проблемы с стабильностью могут возникать, так как клиенты Office Communicator 2007 R2 не поддерживаются в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ec17-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="9ec17-118">Чтобы избежать этих проблем, измените расписание собраний, упорядоченных на клиентах Office Communicator 2007 R2 с помощью Outlook 2010 или Outlook 2013, с помощью надстройки "собрание по сети" для Lync 2010 или для собрания по сети для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9ec17-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="9ec17-119">В следующих разделах описаны вопросы, необходимые для развертывания различных типов возможностей Конференции, включая процесс планирования, компоненты, требования к оборудованию и программному обеспечению, а также процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="9ec17-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9ec17-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="9ec17-120">In This Section</span></span>

  - [<span data-ttu-id="9ec17-121">Обзор конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="9ec17-122">Определение требований для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="9ec17-123">Компоненты и топологии для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="9ec17-124">Технические требования для проведения конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="9ec17-125">Контрольный список развертывания для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="9ec17-126">Поддержка больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ec17-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

