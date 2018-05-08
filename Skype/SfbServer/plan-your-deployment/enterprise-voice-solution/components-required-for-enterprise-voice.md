---
title: Компоненты, необходимые для корпоративной голосовой связи, в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Сводка компонентов корпоративной голосовой связи в Скайп для Business Server.
ms.openlocfilehash: 4f28b0dc42b9a64cae7883490a7e9f5e09dd8d80
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="56fcd-103">Компоненты, необходимые для корпоративной голосовой связи, в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="56fcd-103">Components required for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56fcd-104">Сводка компонентов корпоративной голосовой связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="56fcd-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="56fcd-105">Развертывание корпоративной голосовой связи, используемых в топологии необходимы следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="56fcd-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="56fcd-106">Один или несколько серверов-посредников, которые преобразовывать сигналы и некоторые конфигурации мультимедиа между вашей внутренней Скайп для Business Server, инфраструктурой корпоративной голосовой связи и шлюза телефонной сети (общего пользования PSTN) или протокол Магистраль (SIP).</span><span class="sxs-lookup"><span data-stu-id="56fcd-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="56fcd-107">Серверов-посредников являются наиболее важных компонентов в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="56fcd-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="56fcd-108">Для получения дополнительных сведений см [компонент сервера-посредника в Скайп для Business Server 2015](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="56fcd-108">For more information, see [Mediation Server component in Skype for Business Server 2015](mediation-server.md).</span></span>
    
    <span data-ttu-id="56fcd-109">Серверов-посредников можно, совмещенного с сервера переднего плана или установлена как отдельных серверов.</span><span class="sxs-lookup"><span data-stu-id="56fcd-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="56fcd-110">Компоненты для подключения к ТСОП, которые могут включать в себя магистральные сети SIP или шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="56fcd-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="56fcd-111">Для получения дополнительных сведений см [компоненты подключения к ТСОП в Скайп для Business Server 2015](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="56fcd-111">For more information, see [PSTN connectivity components in Skype for Business Server 2015](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="56fcd-112">Пограничные серверы, которые позволяет использовать функции корпоративной голосовой связи по пользователей, находящихся за пределами брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="56fcd-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="56fcd-113">Пограничная служба доступа предоставляет сигналы SIP для вызовов из Скайп для бизнес-пользователей, находящихся за пределами брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="56fcd-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="56fcd-114">Пограничная служба аудио- и видеоданных обеспечивает обход трансляторов сетевых адресов и брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="56fcd-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="56fcd-115">Вызывающий абонент, работающий с клиентом объединенных коммуникаций (UC) за пределами корпоративного брандмауэра, пользуется пограничной службой аудио- и видеоданных как для индивидуальных вызовов, так и для вызовов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="56fcd-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="56fcd-p104">Служба проверки подлинности аудио и видео связана с пограничной службой аудио- и видеоданных и предоставляет услуги проверки подлинности. Внешним пользователям, которые пытаются подключиться к пограничной службе аудио- и видеоданных, требуется маркер проверки подлинности, предоставляемый службой проверки подлинности аудио и видео, для прохождения вызовов.</span><span class="sxs-lookup"><span data-stu-id="56fcd-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="56fcd-118">Кроме того некоторые компоненты корпоративной голосовой связи запускаются на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="56fcd-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="56fcd-119">Для получения дополнительных сведений об этих компонентов увидеть [компоненты VoIP сервера переднего плана для Скайп для Business Server 2015](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="56fcd-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server 2015](front-end-server-voip.md)</span></span>
    

