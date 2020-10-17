---
title: 'Lync Server 2013: функции устойчивости сайта филиала'
description: 'Lync Server 2013: функции устойчивости для сайта филиала.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552205"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="dfe31-103">Функции устойчивости сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfe31-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfe31-104">_**Последнее изменение темы:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="dfe31-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="dfe31-105">Если обеспечивается устойчивость связи на сайтах филиалов, то при выходе из строя подключения WAN к центральному сайту или при недоступности центрального сайта продолжают оставаться доступными следующие функции голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dfe31-105">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="dfe31-106">Входящие и исходящие вызовы по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="dfe31-106">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="dfe31-107">Корпоративные вызовы между пользователями как одного сайта, так и разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="dfe31-107">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="dfe31-108">Базовая обработка вызова, включая удержание, возобновление и переключение вызовов.</span><span class="sxs-lookup"><span data-stu-id="dfe31-108">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="dfe31-109">Двусторонний обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="dfe31-109">Two-party instant messaging</span></span>

  - <span data-ttu-id="dfe31-110">Услуги переадресации вызовов, одновременных звонков в нескольких конечных точках, делегирования вызовов и групповых звонков, но только если делегирующий и делегируемый (например, руководитель и администратор руководителя) или все члены группы настроены на одном и том же сайте.</span><span class="sxs-lookup"><span data-stu-id="dfe31-110">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="dfe31-111">Записи регистрации вызовов (CDR).</span><span class="sxs-lookup"><span data-stu-id="dfe31-111">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="dfe31-112">Конференц-связь с телефонным подключением из ТСОП с автосекретарем конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="dfe31-112">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="dfe31-113">Возможности голосовой почты, если настроены параметры маршрутизации голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="dfe31-113">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="dfe31-114">(Дополнительные сведения см. в статье [требования к устойчивости для сайтов филиала для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="dfe31-114">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="dfe31-115">Проверка подлинности и авторизация пользователей.</span><span class="sxs-lookup"><span data-stu-id="dfe31-115">User authentication and authorization</span></span>

<span data-ttu-id="dfe31-116">Следующие функции будут доступны только в том случае, если решение устойчивости является полноценным развертыванием Lync Server на сайте филиала:</span><span class="sxs-lookup"><span data-stu-id="dfe31-116">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="dfe31-117">Обмен мгновенными сообщениями, веб-конференции, а также аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="dfe31-117">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="dfe31-118">Маршрутизация на основании сведений о присутствии и статуса "не беспокоить" (когда вызовы не осуществляются для расширений со статусом "не беспокоить").</span><span class="sxs-lookup"><span data-stu-id="dfe31-118">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="dfe31-119">Обновление параметров переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="dfe31-119">Updating call forwarding settings</span></span>

  - <span data-ttu-id="dfe31-120">Приложение группы ответа и приложение парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="dfe31-120">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="dfe31-121">Подготовка новых телефонов и клиентов, но только в том случае, если на сайте филиала имеются доменные службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dfe31-121">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="dfe31-122">Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="dfe31-122">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="dfe31-123">Если E9-1-1 развернута, а магистральная линия SIP на центральном сайте недоступна из-за отсутствия связи WAN, то устройство для обеспечения связи в филиалах будет направлять вызовы E9-1-1 на локальный шлюз филиала.</span><span class="sxs-lookup"><span data-stu-id="dfe31-123">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="dfe31-124">Для включения этой функции политики маршрутизации голосовой связи пользователей на сайтах филиалов должны направлять вызовы в локальный шлюз в случае сбоя WAN.</span><span class="sxs-lookup"><span data-stu-id="dfe31-124">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfe31-125">SBA (подключение к филиалу) не поддерживается для XMPP.</span><span class="sxs-lookup"><span data-stu-id="dfe31-125">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="dfe31-126">Пользователи, размещенные в конфигурациях SBA, не смогут отправлять мгновенные сообщения и просматривать сведения о присутствии с контактами XMPP.</span><span class="sxs-lookup"><span data-stu-id="dfe31-126">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

