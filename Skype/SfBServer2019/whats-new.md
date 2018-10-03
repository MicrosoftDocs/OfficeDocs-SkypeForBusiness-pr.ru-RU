---
title: Новые возможности в Skype для бизнеса Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Эти функции являются новыми в Скайп для Business Server 2019.'
ms.openlocfilehash: 7b4e07ab6fbb7bfddcd056c9d6c4cd9d836d9a8e
ms.sourcegitcommit: 02ff91505a2f185bb3c1059a1b26ee31bb272438
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "25027328"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="1e75f-103">Что такое в Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1e75f-103">What's in Skype for Business Server 2019</span></span> 

<span data-ttu-id="1e75f-104">**Сводка:** Прочтите этот раздел, чтобы узнать о новых функций в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1e75f-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

[!INCLUDE [disclaimer](disclaimer.md)]

<span data-ttu-id="1e75f-105">Новые возможности Скайп для Business Server 2019 относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="1e75f-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="1e75f-106">Облако голосовой почты</span><span class="sxs-lookup"><span data-stu-id="1e75f-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="1e75f-107">Подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="1e75f-107">Call Data Connector</span></span>
- <span data-ttu-id="1e75f-108">Миграция рядом друг с другом</span><span class="sxs-lookup"><span data-stu-id="1e75f-108">Side-by-side migration</span></span>
- <span data-ttu-id="1e75f-109">Миграция по группам</span><span class="sxs-lookup"><span data-stu-id="1e75f-109">Migration to Teams</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="1e75f-110">Единой службы обмена сообщениями: голосовой почты в облаке</span><span class="sxs-lookup"><span data-stu-id="1e75f-110">Unified messaging services: Cloud Voicemail</span></span> 

<span data-ttu-id="1e75f-111">Exchange единой системы обмена СООБЩЕНИЯМИ остается доступным в Скайп для Business Server 2019 при Скайп для бизнеса 2019 интеграции с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="1e75f-111">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="1e75f-112">Из-за изменения в поддержке в Exchange 2019 интеграции с Exchange единой системы обмена СООБЩЕНИЯМИ, отзыва emphasised пользу функции голосовой почты в облаке и облачных автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="1e75f-112">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="1e75f-113">Голосовая почта облачных включает все Скайп для пользователей Business 2019 & #x 2014 г.; ли они размещены локально или через Интернет & #x 2014 г. иметь доступ к одной службы голосовой почты в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1e75f-113">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="1e75f-114">Голосовой почты в облаке для локальных и активные пользователи дает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="1e75f-114">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="1e75f-115">Доступ к голосовой почты в почтовом ящике Exchange с помощью Скайп для клиентов Online бизнеса, групп или Outlook</span><span class="sxs-lookup"><span data-stu-id="1e75f-115">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span> 
- <span data-ttu-id="1e75f-116">Возможность использования веб-портал для управления их параметры голосовой почты</span><span class="sxs-lookup"><span data-stu-id="1e75f-116">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="1e75f-117">[Планирование голосовой почты облачных служб](hybrid/plan-cloud-voicemail.md) и [Планирование Скайп для Business Server и миграция Exchange Server](hybrid/plan-um-migration.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="1e75f-117">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="1e75f-118">Вызов мониторинга: подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="1e75f-118">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="1e75f-119">Подключения к данным вызова существенно упрощает вызов мониторинга в гибридной среде, так как больше не требуется для использования различных наборов локальной и online средства для наблюдения за всеми качество звонка пользователей.</span><span class="sxs-lookup"><span data-stu-id="1e75f-119">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="1e75f-120">Пользователи, размещенные локально или через Интернет, ли можно выбрать для просмотра качества звонка для всей организации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1e75f-120">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="1e75f-121">С помощью вызова подключения к данным с помощью одного набора инструментов можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1e75f-121">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="1e75f-122">Мониторинг вам группами Майкрософт, Скайп для бизнеса в Интернет и Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e75f-122">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="1e75f-123">Просмотр и устранение неполадок в сети</span><span class="sxs-lookup"><span data-stu-id="1e75f-123">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="1e75f-124">Назначение роли администратора и служба технической поддержки для вызова анализа, позволяют сотрудникам служба технической поддержки для просмотра и устранения неполадок их области ответственности.</span><span class="sxs-lookup"><span data-stu-id="1e75f-124">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="1e75f-125">Для получения дополнительных сведений в разделе [Планирование вызова подключения к данным](hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="1e75f-125">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>
  


## <a name="installation-and-upgrade-side-by-side-migration"></a><span data-ttu-id="1e75f-126">Установка и обновление: рядом друг с другом миграции</span><span class="sxs-lookup"><span data-stu-id="1e75f-126">Installation and Upgrade: Side-by-side migration</span></span>

<span data-ttu-id="1e75f-127">При переносе рядом друг с другом можно развернуть на новый сервер Скайп для Business Server 2019 наряду с соответствующему серверу, на котором работает предыдущей версии (Скайп Business Server 2015 и Lync Server 2013), а затем переключите операций на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="1e75f-127">In a side-by-side migration, you deploy a new server running Skype for Business Server 2019 alongside a corresponding server that is running a previous version (Skype for Business Server 2015 or Lync Server 2013), and then transfer operations to the new server.</span></span> <span data-ttu-id="1e75f-128">Если необходимо восстановить его предыдущую версию, необходимо только сдвиг операции исходные серверы.</span><span class="sxs-lookup"><span data-stu-id="1e75f-128">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> 

<span data-ttu-id="1e75f-129">Для получения подробных сведений см [перехода на Скайп для Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span><span class="sxs-lookup"><span data-stu-id="1e75f-129">For complete details, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="1e75f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1e75f-130">See also</span></span>

[<span data-ttu-id="1e75f-131">Что, удаленные из Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1e75f-131">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)