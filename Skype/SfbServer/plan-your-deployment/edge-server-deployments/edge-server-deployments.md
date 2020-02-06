---
title: Планирование развертывания пограничного сервера в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: планирование для среды Microsoft Skype для бизнеса Server Edge. Этот раздел содержит начальные сведения о принципах работы пограничных серверов, а также систематизированные ссылки на разделы с более подробной информацией.'
ms.openlocfilehash: f19f00aab393ed94735f47f2e66ab0a2869d2d7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803369"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="3ced4-104">Планирование развертывания пограничного сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3ced4-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="3ced4-105">**Сводка:** Составьте план для среды Skype для бизнеса Server Edge.</span><span class="sxs-lookup"><span data-stu-id="3ced4-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="3ced4-106">Этот раздел содержит начальные сведения о принципах работы пограничных серверов, а также систематизированные ссылки на разделы с более подробной информацией.</span><span class="sxs-lookup"><span data-stu-id="3ced4-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="3ced4-107">Если вы работаете с серверной средой Skype для бизнеса, на следующий шаг может потребоваться внести в среду пограничный сервер или пул Edge.</span><span class="sxs-lookup"><span data-stu-id="3ced4-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="3ced4-108">Эта роль важна, если вы хотите, чтобы службы, предоставляемые Skype для бизнеса Server, использовались для пользователей, которые находятся за пределами внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="3ced4-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="3ced4-109">These can potentially include:</span><span class="sxs-lookup"><span data-stu-id="3ced4-109">These can potentially include:</span></span>
  
- <span data-ttu-id="3ced4-110">Удаленные пользователи: сотрудники, временно отсутствующие на рабочем месте, в том числе находящиеся в пути.</span><span class="sxs-lookup"><span data-stu-id="3ced4-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="3ced4-111">Федеративные пользователи: сотрудники Организации-партнера.</span><span class="sxs-lookup"><span data-stu-id="3ced4-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="3ced4-112">Пользователи мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="3ced4-112">Mobile Users.</span></span>
    
- <span data-ttu-id="3ced4-113">Потенциальные заказчики, партнеры и анонимные пользователи, которых требуется приглашать на собрания и презентации.</span><span class="sxs-lookup"><span data-stu-id="3ced4-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="3ced4-114">Внешний пользователь, который предоставляет доступ к серверу пограничного сервера, допускает все это.</span><span class="sxs-lookup"><span data-stu-id="3ced4-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="3ced4-115">Ваши внутренние пользователи смогут пользоваться следующими службами, которые размещаются в среде развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3ced4-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="3ced4-116">Обмен мгновенными сообщениями и сведения о присутствии. авторизованные внешние пользователи могут присоединиться в текстовых беседах и конференциях.</span><span class="sxs-lookup"><span data-stu-id="3ced4-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="3ced4-117">Они могут получить сведения о присутствии для других пользователей (кто также может получить информацию о присутствии).</span><span class="sxs-lookup"><span data-stu-id="3ced4-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="3ced4-118">Вы не сможете выполнять многосторонние конференции, если у вас есть общедоступная служба обмена мгновенными сообщениями, это строго одноранговая связь.</span><span class="sxs-lookup"><span data-stu-id="3ced4-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="3ced4-119">Но поддерживаются оба протокола SIP и КСМПП.</span><span class="sxs-lookup"><span data-stu-id="3ced4-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="3ced4-120">Конференции аудио-и видеосвязи (A/V): авторизованные внешние пользователи могут принимать участие в голосовой и видеоконференциях в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3ced4-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="3ced4-121">Веб-конференции: Ваши авторизованные внешние пользователи могут принимать участие в конференциях в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3ced4-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="3ced4-122">Вы также можете включить участие удаленных пользователей, федеративных пользователей и анонимных пользователей, если хотите.</span><span class="sxs-lookup"><span data-stu-id="3ced4-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="3ced4-123">Общедоступные пользователи мгновенного обмена сообщениями не могут участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="3ced4-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="3ced4-124">Кроме того, есть параметры, позволяющие пользователям принимать участие в совместном использовании приложений и рабочих столов, а также выступать в качестве организаторов собраний и выступающих.</span><span class="sxs-lookup"><span data-stu-id="3ced4-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="3ced4-125">Поддерживается доступ к мобильным устройствам, как и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="3ced4-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="3ced4-126">Можно приглашать внешних пользователей на собрания, где требуется их присутствие; при необходимости можно предоставить разрешение участвовать в собрании даже анонимным пользователям.</span><span class="sxs-lookup"><span data-stu-id="3ced4-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="3ced4-p108">Если в организации требуются такие службы, для их развертывания рекомендуется спланировать среду пограничных серверов. Ниже приведен список разделов, содержащих дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="3ced4-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="3ced4-129">Прокси-серверы и шлюзы XMPP доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ced4-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3ced4-130">Дополнительные сведения см. в статье [Перенос федерации XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="3ced4-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="3ced4-131">Разделы по планированию</span><span class="sxs-lookup"><span data-stu-id="3ced4-131">Planning topics:</span></span>

<span data-ttu-id="3ced4-132">Статьи по планированию</span><span class="sxs-lookup"><span data-stu-id="3ced4-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="3ced4-133">Требования к системе пограничных серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ced4-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="3ced4-134">Требования к среде пограничных серверов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ced4-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="3ced4-135">Варианты пограничных серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ced4-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

