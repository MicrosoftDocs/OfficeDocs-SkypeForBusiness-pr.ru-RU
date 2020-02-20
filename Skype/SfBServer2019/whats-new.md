---
title: Новые возможности Skype для бизнеса Server 2019 | Функции
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Эти функции являются новыми в Skype для бизнеса Server 2019.
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129402"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="992a1-103">Что входит в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="992a1-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="992a1-104">**Сводка:** В этом разделе рассказывается о новых возможностях Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="992a1-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="992a1-105">К новым функциям в Skype для бизнеса Server 2019 относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="992a1-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="992a1-106">Облачная Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="992a1-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="992a1-107">Соединитель данных вызовов</span><span class="sxs-lookup"><span data-stu-id="992a1-107">Call Data Connector</span></span>
- <span data-ttu-id="992a1-108">Параллельная миграция</span><span class="sxs-lookup"><span data-stu-id="992a1-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="992a1-109">Службы единой системы обмена сообщениями: облачная Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="992a1-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="992a1-110">Единая система обмена сообщениями Exchange остается доступной в Skype для бизнеса Server 2019 при интеграции Skype для бизнеса 2019 с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="992a1-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="992a1-111">Из-за изменений в поддержке в Exchange 2019 интеграция единой системы обмена сообщениями Exchange не выделена в пользу использования облачных голосовых функций и функций автосекретаря Cloud.</span><span class="sxs-lookup"><span data-stu-id="992a1-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="992a1-112">Облачная Голосовая почта позволяет всем пользователям Skype для бизнеса 2019&#x2014;, размещены ли они в локальной среде или в сети&#x2014;, чтобы иметь доступ к одной и той же службе голосовой почты в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="992a1-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="992a1-113">Облачная Голосовая почта предоставляет следующие преимущества для локальных пользователей и пользователей в сети:</span><span class="sxs-lookup"><span data-stu-id="992a1-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="992a1-114">Доступ к голосовой почте в своем почтовом ящике Exchange с помощью клиентов Skype для бизнеса Online, Teams или Outlook</span><span class="sxs-lookup"><span data-stu-id="992a1-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="992a1-115">Возможность использования веб-портала для управления параметрами голосовой почты</span><span class="sxs-lookup"><span data-stu-id="992a1-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="992a1-116">Дополнительные сведения см. в статье [Plan облачная служба голосовой почты](../sfbhybrid/hybrid/plan-cloud-voicemail.md) и [Планирование переноса Skype для бизнеса Server и Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="992a1-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="992a1-117">Отслеживание звонков: соединитель данных вызовов</span><span class="sxs-lookup"><span data-stu-id="992a1-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="992a1-118">Соединитель данных вызовов значительно упрощает отслеживание звонков в гибридной среде, так как больше не требуется использовать разные наборы локальных и интерактивных средств для отслеживания качества звонков для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="992a1-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="992a1-119">Независимо от того, размещены ли ваши пользователи в локальной организации или в сети, можно выбрать просмотр качества звонков для всей Организации в сети.</span><span class="sxs-lookup"><span data-stu-id="992a1-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="992a1-120">С помощью соединителя данных вызовов можно выполнять следующие задачи с помощью одного набора инструментов:</span><span class="sxs-lookup"><span data-stu-id="992a1-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="992a1-121">Следите за работой пользователей в Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="992a1-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="992a1-122">Просмотр и устранение неполадок в сети</span><span class="sxs-lookup"><span data-stu-id="992a1-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="992a1-123">Назначьте роли службы поддержки и администратора для анализа вызовов, чтобы предоставить сотрудникам службы поддержки возможность просматривать и устранять свои обязанности.</span><span class="sxs-lookup"><span data-stu-id="992a1-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="992a1-124">Дополнительную информацию можно узнать в статье [Plan Call Connector Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="992a1-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="992a1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="992a1-125">See also</span></span>

[<span data-ttu-id="992a1-126">Устаревшие возможности Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="992a1-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
