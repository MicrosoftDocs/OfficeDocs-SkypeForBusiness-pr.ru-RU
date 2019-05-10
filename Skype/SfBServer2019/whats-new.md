---
title: Новые возможности Скайп для Business Server 2019 | Функции
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Эти функции являются новыми в Скайп для Business Server 2019.'
ms.openlocfilehash: 68b6a2c3e3115df58c44603817e2adfc0c83f67c
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835241"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="08601-103">Что такое в Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="08601-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="08601-104">**Сводка:** Прочтите этот раздел, чтобы узнать о новых функций в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="08601-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="08601-105">Новые возможности Скайп для Business Server 2019 относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="08601-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="08601-106">Облачная голосовая почта</span><span class="sxs-lookup"><span data-stu-id="08601-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="08601-107">Соединитель данных звонка</span><span class="sxs-lookup"><span data-stu-id="08601-107">Call Data Connector</span></span>
- <span data-ttu-id="08601-108">Миграция рядом друг с другом</span><span class="sxs-lookup"><span data-stu-id="08601-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="08601-109">Единой службы обмена сообщениями: голосовой почты в облаке</span><span class="sxs-lookup"><span data-stu-id="08601-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="08601-110">Exchange единой системы обмена СООБЩЕНИЯМИ остается доступным в Скайп для Business Server 2019 при Скайп для бизнеса 2019 интеграции с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="08601-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="08601-111">Из-за изменения в поддержке в Exchange 2019 интеграции с Exchange единой системы обмена СООБЩЕНИЯМИ, рекомендуется вместо функции голосовой почты в облаке и облачных автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="08601-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="08601-112">Голосовой почты в облаке включает все Скайп для бизнеса 2019 users& #x 2014 г; ли они размещаются на локальных или online& #x 2014 г., чтобы иметь доступ к одной службы голосовой почты в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08601-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="08601-113">Голосовой почты в облаке для локальных и активные пользователи дает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="08601-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="08601-114">Доступ к голосовой почты в почтовом ящике Exchange с помощью Скайп для клиентов Online бизнеса, групп или Outlook</span><span class="sxs-lookup"><span data-stu-id="08601-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="08601-115">Возможность использования веб-портал для управления их параметры голосовой почты</span><span class="sxs-lookup"><span data-stu-id="08601-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="08601-116">[Планирование голосовой почты облачных служб](../sfbhybrid/hybrid/plan-cloud-voicemail.md) и [Планирование Скайп для Business Server и миграция Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="08601-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="08601-117">Вызов мониторинга: подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="08601-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="08601-118">Подключения к данным вызова существенно упрощает вызов мониторинга в гибридной среде, так как больше не требуется для использования различных наборов локальной и online средства для наблюдения за всеми качество звонка пользователей.</span><span class="sxs-lookup"><span data-stu-id="08601-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="08601-119">Пользователи, размещенные локально или через Интернет, ли можно выбрать для просмотра качества звонка для всей организации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="08601-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="08601-120">С помощью вызова подключения к данным с помощью одного набора инструментов можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="08601-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="08601-121">Мониторинг вам группами Майкрософт, Скайп для бизнеса в Интернет и Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="08601-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="08601-122">Просмотр и устранение неполадок в сети</span><span class="sxs-lookup"><span data-stu-id="08601-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="08601-123">Назначение роли администратора и служба технической поддержки для вызова анализа, позволяют сотрудникам служба технической поддержки для просмотра и устранения неполадок их области ответственности.</span><span class="sxs-lookup"><span data-stu-id="08601-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="08601-124">Для получения дополнительных сведений в разделе [Планирование вызова подключения к данным](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="08601-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="08601-125">См. также</span><span class="sxs-lookup"><span data-stu-id="08601-125">See also</span></span>

[<span data-ttu-id="08601-126">Что, удаленные из Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="08601-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
