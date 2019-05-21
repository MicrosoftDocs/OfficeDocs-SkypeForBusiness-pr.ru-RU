---
title: Компоненты, необходимые для корпоративной голосовой связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Сводка по компонентам корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277008"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="61dc7-103">Компоненты, необходимые для корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61dc7-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="61dc7-104">Сводка по компонентам корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61dc7-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="61dc7-105">Для развертывания корпоративной голосовой связи в вашей топологии необходимы следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="61dc7-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="61dc7-106">Один или несколько серверов-посредников, в которых переводятся сигналы и в некоторых конфигурациях — носители между внутренней сетью Skype для бизнеса Server, Корпоративная инфраструктура голосовой связи и шлюз для коммутируемой коммутируемой телефонной сети или Протокол инициирования сеанса. (SIP).</span><span class="sxs-lookup"><span data-stu-id="61dc7-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="61dc7-107">Серверы обновлений — это самый важный компонент в развертывании вашей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="61dc7-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="61dc7-108">Дополнительные сведения можно найти [в разделе Сервер исправлений в Skype для бизнеса Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="61dc7-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="61dc7-109">Серверы исправлений можно расставлять с серверными интерфейсами или устанавливать как отдельные серверы.</span><span class="sxs-lookup"><span data-stu-id="61dc7-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="61dc7-110">Компоненты для подключения к ТСОП, которые могут включать в себя магистральные сети SIP или шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="61dc7-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="61dc7-111">Дополнительные сведения можно найти [в разделе Компоненты подключения PSTN в Skype для бизнеса Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="61dc7-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="61dc7-112">Пограничные серверы, позволяющие вашим пользователям работать с корпоративными голосовыми функциями, если они находятся за пределами брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="61dc7-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="61dc7-113">Служба пограничного доступа предоставляет сигналы SIP для звонков из пользователей Skype для бизнеса, которые находятся за пределами брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="61dc7-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="61dc7-114">Пограничная служба аудио- и видеоданных обеспечивает обход трансляторов сетевых адресов и брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="61dc7-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="61dc7-115">Вызывающий абонент, работающий с клиентом объединенных коммуникаций (UC) за пределами корпоративного брандмауэра, пользуется пограничной службой аудио- и видеоданных как для индивидуальных вызовов, так и для вызовов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="61dc7-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="61dc7-p104">Служба проверки подлинности аудио и видео связана с пограничной службой аудио- и видеоданных и предоставляет услуги проверки подлинности. Внешним пользователям, которые пытаются подключиться к пограничной службе аудио- и видеоданных, требуется маркер проверки подлинности, предоставляемый службой проверки подлинности аудио и видео, для прохождения вызовов.</span><span class="sxs-lookup"><span data-stu-id="61dc7-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="61dc7-118">Кроме того, некоторые корпоративные компоненты голосовой связи работают на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="61dc7-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="61dc7-119">Подробнее об этих компонентах можно найти в разделе [компонент VoIP сервер переднего плана для Skype для бизнеса Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="61dc7-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

