---
title: Новые возможности Skype для бизнеса Server 2019 | Функциональные
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: новые возможности в Skype для бизнеса Server 2019.'
ms.openlocfilehash: 4ede00188c8928e0fa3d89857b6d5bfdb0a44ade
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283901"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="84529-103">Что находится в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="84529-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="84529-104">**Сводка:** Прочтите этот раздел, чтобы узнать о новых возможностях Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="84529-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="84529-105">Новые возможности в Skype для бизнеса Server 2019 включают следующее:</span><span class="sxs-lookup"><span data-stu-id="84529-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="84529-106">Облачная голосовая почта</span><span class="sxs-lookup"><span data-stu-id="84529-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="84529-107">Соединитель данных звонка</span><span class="sxs-lookup"><span data-stu-id="84529-107">Call Data Connector</span></span>
- <span data-ttu-id="84529-108">Переход с одной стороны на другую</span><span class="sxs-lookup"><span data-stu-id="84529-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="84529-109">Службы единой системы обмена сообщениями: облачная Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="84529-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="84529-110">Единая система обмена сообщениями Exchange остается доступной в Skype для бизнеса Server 2019 при интеграции Skype для бизнеса 2019 с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="84529-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="84529-111">Из-за изменений в службе поддержки в Exchange 2019 интеграция Exchange UM не выделена в пользу того, чтобы отфильтровать голосовую почту и функции автосекретаря в облаке.</span><span class="sxs-lookup"><span data-stu-id="84529-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="84529-112">Облачная Голосовая почта позволяет всем Skype для бизнеса 2019 Усерс_амп_ # x2014; ли они размещены локально или Онлине_амп_ # x2014; для получения доступа к одной и той же службе голосовой почты в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="84529-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="84529-113">Облачная Голосовая почта обеспечивает следующие преимущества для пользователей, которые не являются локальными и подключенными к Интернету.</span><span class="sxs-lookup"><span data-stu-id="84529-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="84529-114">Доступ к голосовой почте в почтовом ящике Exchange с помощью клиентов Skype для бизнеса Online, Teams или Outlook</span><span class="sxs-lookup"><span data-stu-id="84529-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="84529-115">Возможность управлять параметрами голосовой почты с помощью веб-портала</span><span class="sxs-lookup"><span data-stu-id="84529-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="84529-116">Для получения дополнительных сведений ознакомьтесь со [службой планирования облачной голосовой почты](../sfbhybrid/hybrid/plan-cloud-voicemail.md) и [планированием миграции в Skype для бизнеса Server и Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="84529-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="84529-117">Отслеживание звонков: соединитель данных звонка</span><span class="sxs-lookup"><span data-stu-id="84529-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="84529-118">Соединитель данных вызовов значительно упрощает отслеживание звонков в гибридной среде, так как больше не нужно использовать различные наборы локальных и веб-средств для наблюдения за качеством всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="84529-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="84529-119">Независимо от того, подключены ли ваши пользователи к локальной сети или к Интернету, вы можете выбрать способ просмотра качества связи для всей Организации в сети.</span><span class="sxs-lookup"><span data-stu-id="84529-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="84529-120">С помощью соединителя данных вызова вы можете выполнять следующие задачи, используя один набор инструментов:</span><span class="sxs-lookup"><span data-stu-id="84529-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="84529-121">Отслеживайте ваши возможности пользователей в Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="84529-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="84529-122">Просмотр и устранение неполадок в сети</span><span class="sxs-lookup"><span data-stu-id="84529-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="84529-123">Назначать роли службы поддержки и администраторов для аналитики звонков, чтобы предоставить сотрудникам в службе поддержки возможность просматривать и устранять проблемы с их областями ответственности.</span><span class="sxs-lookup"><span data-stu-id="84529-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="84529-124">Дополнительные сведения вы видите в [соединителе данные о звонках планов](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="84529-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="84529-125">См. также</span><span class="sxs-lookup"><span data-stu-id="84529-125">See also</span></span>

[<span data-ttu-id="84529-126">Что не рекомендуется использовать в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="84529-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
