---
title: Планирование развертывания пограничного сервера, в Скайп для Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Обзор: Планирование вашей Скайп для пограничного сервера Business среды. Этот раздел содержит начальные сведения о принципах работы пограничных серверов, а также систематизированные ссылки на разделы с более подробной информацией.'
ms.openlocfilehash: 41a1d2771e43a4e217aa8bac6b98331a31d67c92
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965445"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="2052c-104">Планирование развертывания пограничного сервера, в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2052c-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="2052c-105">**Сводка:** План для вашей Скайп для пограничного сервера Business среды.</span><span class="sxs-lookup"><span data-stu-id="2052c-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="2052c-106">Этот раздел содержит начальные сведения о принципах работы пограничных серверов, а также систематизированные ссылки на разделы с более подробной информацией.</span><span class="sxs-lookup"><span data-stu-id="2052c-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="2052c-107">При наличии Скайп для среды Business Server, который работает также во внутренней сети, следующим шагом для вас может быть представлена на пограничный сервер или пограничный пул в среде.</span><span class="sxs-lookup"><span data-stu-id="2052c-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="2052c-108">Эта роль может быть важной, если требуется, чтобы службы, предоставляемые Скайп для бизнеса сервера, который будет использоваться лицами, за пределами внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="2052c-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="2052c-109">Эти потенциально могут включать следующее:</span><span class="sxs-lookup"><span data-stu-id="2052c-109">These can potentially include:</span></span>
  
- <span data-ttu-id="2052c-110">Удаленные пользователи: сотрудники, временно отсутствующие на рабочем месте, в том числе находящиеся в пути.</span><span class="sxs-lookup"><span data-stu-id="2052c-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="2052c-111">Федеративные пользователи: Партнерские организации сотрудников.</span><span class="sxs-lookup"><span data-stu-id="2052c-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="2052c-112">Пользователи мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="2052c-112">Mobile Users.</span></span>
    
- <span data-ttu-id="2052c-113">Потенциальные заказчики, партнеры и анонимные пользователи, которых требуется приглашать на собрания и презентации.</span><span class="sxs-lookup"><span data-stu-id="2052c-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="2052c-114">Доступ внешних пользователей, которая предоставляют пограничных серверов, разрешить все это происходит.</span><span class="sxs-lookup"><span data-stu-id="2052c-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="2052c-115">Внутренние пользователи смогут Оцените следующие службы, которые размещаются в вашей Скайп для развертывания Business Server:</span><span class="sxs-lookup"><span data-stu-id="2052c-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="2052c-116">Обмен мгновенными Сообщениями и сведениями о присутствии для обмена данными: полномочные внешние пользователи могут присоединиться к в мгновенные сообщения и конференциях.</span><span class="sxs-lookup"><span data-stu-id="2052c-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="2052c-117">Их можно получить сведения о присутствии для других пользователей (получение информации о них сведений о присутствии слишком).</span><span class="sxs-lookup"><span data-stu-id="2052c-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="2052c-118">Не сможет выполнить многосторонних конференциях, если вы используете общедоступный поставщик обмена мгновенными Сообщениями, который является строго peer-to-peer связи.</span><span class="sxs-lookup"><span data-stu-id="2052c-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="2052c-119">Но протокола SIP и XMPP, поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2052c-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="2052c-120">Аудио/видео (A / V) конференц-связи: полномочные внешние пользователи могут принимать участие в вашей Скайп Business Server аудио и видео в конференциях.</span><span class="sxs-lookup"><span data-stu-id="2052c-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="2052c-121">Веб-конференции: вашей полномочные внешние пользователи могут принимать участие в вашей Скайп для конференций бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2052c-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="2052c-122">Если вы хотите, можно также включить участия для удаленных пользователей, федеративных пользователей и анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2052c-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="2052c-123">Открытый обмен мгновенными Сообщениями пользователи не могут участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="2052c-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="2052c-124">Также вы можете эти пользователи могут участвовать в приложения и рабочему столу и даже выступать в качестве организаторам собрания или выступающие.</span><span class="sxs-lookup"><span data-stu-id="2052c-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="2052c-125">Поддерживается доступа с мобильных устройств, как и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2052c-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="2052c-126">Можно приглашать внешних пользователей на собрания, где требуется их присутствие; при необходимости можно предоставить разрешение участвовать в собрании даже анонимным пользователям.</span><span class="sxs-lookup"><span data-stu-id="2052c-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="2052c-p108">Если в организации требуются такие службы, для их развертывания рекомендуется спланировать среду пограничных серверов. Ниже приведен список разделов, содержащих дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="2052c-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="2052c-129">XMPP шлюзов и прокси-серверы, доступные в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2052c-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2052c-130">Для получения дополнительных сведений в разделе [федерации XMPP миграции](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="2052c-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="2052c-131">Разделы по планированию</span><span class="sxs-lookup"><span data-stu-id="2052c-131">Planning topics:</span></span>

<span data-ttu-id="2052c-132">Статьи по планированию</span><span class="sxs-lookup"><span data-stu-id="2052c-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="2052c-133">Требования к системе пограничных серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2052c-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="2052c-134">Требования к среде пограничных серверов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2052c-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="2052c-135">Варианты пограничных серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2052c-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

