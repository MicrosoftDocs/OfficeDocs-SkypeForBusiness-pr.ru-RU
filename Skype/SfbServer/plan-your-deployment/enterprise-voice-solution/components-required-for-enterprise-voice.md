---
title: Компоненты, необходимые для Корпоративная голосовая связь в Skype для бизнеса Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Сводка по Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825829"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="5cbae-103">Компоненты, необходимые для Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5cbae-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="5cbae-104">Сводка по Корпоративная голосовая связь в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5cbae-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="5cbae-105">Чтобы развернуть Корпоративная голосовая связь, в топологии требуются следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="5cbae-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="5cbae-106">Один или несколько серверов-посредников, которые преобразовыют сигналы и, в некоторых конфигурациях, мультимедиа между внутренней инфраструктурой Skype для бизнеса Server, инфраструктурой Корпоративная голосовая связь и шлюзом телефонной сети общего звонков (PSTN) или магистралью SIP.</span><span class="sxs-lookup"><span data-stu-id="5cbae-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="5cbae-107">Серверы-посредники являются важнейшим компонентом в развертывании Корпоративная голосовая связь развертывания.</span><span class="sxs-lookup"><span data-stu-id="5cbae-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="5cbae-108">Дополнительные сведения [см. в компоненте сервера-посредника в Skype для бизнеса Server.](mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="5cbae-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="5cbae-109">Серверы-посредники могут быть размещены вместе с серверами переднего сервера или установлены как автономные серверы.</span><span class="sxs-lookup"><span data-stu-id="5cbae-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="5cbae-110">Компоненты подключения к STN, которые могут включать магистрали SIP или шлюзы STN.</span><span class="sxs-lookup"><span data-stu-id="5cbae-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="5cbae-111">Дополнительные сведения см. в сведениях о компонентах подключения к [STN в Skype для бизнеса Server.](pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="5cbae-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="5cbae-112">Edge Servers, который позволяет использовать Корпоративная голосовая связь пользователями, когда они находятся за пределами брандмауэра вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5cbae-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="5cbae-113">Служба по границе доступа предоставляет сигналы SIP для звонков от пользователей Skype для бизнеса, которые находятся за пределами брандмауэра вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5cbae-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="5cbae-114">Служба A/V Edge обеспечивает обход NAT и брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="5cbae-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="5cbae-115">Абонент, использующий унифицированный коммуникационный клиент (UC) за пределами корпоративного брандмауэра, применяет службу для выполнения индивидуальных вызовов или конференц-вызовов.</span><span class="sxs-lookup"><span data-stu-id="5cbae-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="5cbae-p104">Служба проверки подлинности аудио и видео связана с пограничной службой аудио- и видеоданных и предоставляет услуги проверки подлинности. Внешним пользователям, которые пытаются подключиться к пограничной службе аудио- и видеоданных, требуется маркер проверки подлинности, предоставляемый службой проверки подлинности аудио и видео, для прохождения вызовов.</span><span class="sxs-lookup"><span data-stu-id="5cbae-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="5cbae-118">Кроме того, некоторые Корпоративная голосовая связь на серверах переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="5cbae-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="5cbae-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="5cbae-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

