---
title: Планирование развертывания edge Server в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: Сводка. Планирование среды Skype для бизнеса Server Edge. В этом разделе вы познакомились с понятиями Edge и поможет вам организоваться с помощью более подробной темы.
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813809"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="32579-104">Планирование развертывания edge Server в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32579-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="32579-105">**Сводка:** Планирование среды Skype для бизнеса Server Edge.</span><span class="sxs-lookup"><span data-stu-id="32579-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="32579-106">В этом разделе вы познакомились с понятиями Edge и поможет вам организоваться с помощью более подробной темы.</span><span class="sxs-lookup"><span data-stu-id="32579-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="32579-107">Если у вас есть среда Skype для бизнеса Server, которая хорошо работает внутри организации, следующим шагом может быть внедрение в среду edge server или пула.</span><span class="sxs-lookup"><span data-stu-id="32579-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="32579-108">Эта роль имеет важное значение, если вы хотите, чтобы службы, предоставляемые Skype для бизнеса Server, использовались людьми, которые находятся за пределами внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="32579-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="32579-109">К ним могут быть потенциально относятся:</span><span class="sxs-lookup"><span data-stu-id="32579-109">These can potentially include:</span></span>
  
- <span data-ttu-id="32579-110">Удаленные пользователи: сотрудники, которые временно или постоянно находятся за ее компьютером.</span><span class="sxs-lookup"><span data-stu-id="32579-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="32579-111">Федераированные пользователи: сотрудники партнерских организаций.</span><span class="sxs-lookup"><span data-stu-id="32579-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="32579-112">Мобильные пользователи.</span><span class="sxs-lookup"><span data-stu-id="32579-112">Mobile Users.</span></span>
    
- <span data-ttu-id="32579-113">Потенциальные клиенты, партнеры и даже анонимные пользователи, приглашенные на собрания и презентации.</span><span class="sxs-lookup"><span data-stu-id="32579-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="32579-114">Доступ внешних пользователей, то есть то, что предоставляют edge-серверы, разрешает все это.</span><span class="sxs-lookup"><span data-stu-id="32579-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="32579-115">Внутренние пользователи смогут пользоваться следующими службами, которые размещены в развертывании Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="32579-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="32579-116">Мгновенные сообщения и присутствие для связи: авторизованные внешние пользователи могут присоединяться к мгновенным беседам и конференциям.</span><span class="sxs-lookup"><span data-stu-id="32579-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="32579-117">Они могут получать сведения о присутствии для других пользователей (которые также получают сведения о присутствии).</span><span class="sxs-lookup"><span data-stu-id="32579-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="32579-118">Вы не сможете делать многостолбные конференции, если используется общедоступный поставщик услуг мгновенных сообщений, т. е. только одноранговая связь.</span><span class="sxs-lookup"><span data-stu-id="32579-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="32579-119">Однако поддерживаются и протоколы SIP, и XMPP.</span><span class="sxs-lookup"><span data-stu-id="32579-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="32579-120">Аудио- и видеоконференции: авторизованные внешние пользователи могут участвовать в аудио- и видеоконференции Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32579-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="32579-121">Веб-конференции: авторизованные внешние пользователи могут участвовать в конференциях Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32579-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="32579-122">Вы также можете включить участие для удаленных пользователей, федераированных пользователей и анонимных пользователей, если хотите.</span><span class="sxs-lookup"><span data-stu-id="32579-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="32579-123">Пользователи общедоступных служб im не могут участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="32579-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="32579-124">Кроме того, можно позволить этим пользователям участвовать в совместном использовании приложений и рабочих столах и даже выступать в качестве организаторов или участников собрания.</span><span class="sxs-lookup"><span data-stu-id="32579-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="32579-125">Поддерживается доступ с мобильных устройств, как и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="32579-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="32579-126">Вы можете приглашать внешних пользователей на собрания, в которых они должны участвовать, даже анонимных пользователей, если вы хотите предоставить им разрешения.</span><span class="sxs-lookup"><span data-stu-id="32579-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="32579-127">Если это похоже на то, что требуется вашей организации, планирование среды edge будет большим помощником по ее развертыванию.</span><span class="sxs-lookup"><span data-stu-id="32579-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="32579-128">Для дальнейшего чтения у нас есть разделы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="32579-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="32579-129">Шлюзы и прокси-серверы XMPP доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32579-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="32579-130">Дополнительные сведения см. в переносе [федерации XMPP.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="32579-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="32579-131">Разделы по планированию:</span><span class="sxs-lookup"><span data-stu-id="32579-131">Planning topics:</span></span>

<span data-ttu-id="32579-132">Статьи по планированию:</span><span class="sxs-lookup"><span data-stu-id="32579-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="32579-133">Требования к системе для сервера Edge Server в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="32579-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="32579-134">Требования к среде для edge Server в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="32579-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="32579-135">Сценарии использования edge Server в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="32579-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

