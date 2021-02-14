---
title: Новые возможности Skype для бизнеса Server 2019 | Функции
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Эти функции являются новыми в Skype для бизнеса Server 2019.
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812589"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="95aa7-103">Что такое Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="95aa7-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="95aa7-104">**Сводка:** В этом разделе представлены новые возможности Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="95aa7-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="95aa7-105">К новым функциям Skype для бизнеса Server 2019 относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="95aa7-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="95aa7-106">Облачная голосовая почта</span><span class="sxs-lookup"><span data-stu-id="95aa7-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="95aa7-107">Соединитель данных звонка</span><span class="sxs-lookup"><span data-stu-id="95aa7-107">Call Data Connector</span></span>
- <span data-ttu-id="95aa7-108">Боковая миграция</span><span class="sxs-lookup"><span data-stu-id="95aa7-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="95aa7-109">Службы единой системы обмена сообщениями: облачная голосовая почта</span><span class="sxs-lookup"><span data-stu-id="95aa7-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="95aa7-110">При интеграции Skype для бизнеса 2019 с Exchange 2013 или Exchange 2016 в Skype для бизнеса Server 2019 остается доступной um exchange.</span><span class="sxs-lookup"><span data-stu-id="95aa7-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="95aa7-111">Из-за изменений в поддержке в Exchange 2019 интеграция с exchange UM будет отостановка в пользу функций облачной голосовой почты и облачных автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="95aa7-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="95aa7-112">Облачная голосовая почта позволяет всем пользователям Skype для бизнеса 2019&#x2014;как в локальной, так и в сетевой&#x2014;иметь доступ к одной службе голосовой почты в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="95aa7-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="95aa7-113">Облачная голосовая почта предоставляет следующие преимущества как для пользователей локальной, так и для интернет-службы:</span><span class="sxs-lookup"><span data-stu-id="95aa7-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="95aa7-114">Доступ к голосовой почте в почтовом ящике Exchange с помощью клиентов Skype для бизнеса Online, Teams или Outlook</span><span class="sxs-lookup"><span data-stu-id="95aa7-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="95aa7-115">Возможность использования веб-портала для управления вариантами голосовой почты</span><span class="sxs-lookup"><span data-stu-id="95aa7-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="95aa7-116">Дополнительные [сведения см.](../sfbhybrid/hybrid/plan-cloud-voicemail.md) в сведениях о планировании службы облачной голосовой почты и планировании для Skype для бизнеса [Server Exchange Server миграции.](../sfbhybrid/hybrid/plan-um-migration.md)</span><span class="sxs-lookup"><span data-stu-id="95aa7-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="95aa7-117">Мониторинг вызовов: соединители данных зовов</span><span class="sxs-lookup"><span data-stu-id="95aa7-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="95aa7-118">Соединителю обработки данных вызовов значительно упрощается мониторинг вызовов в гибридной среде, так как вам больше не нужно использовать различные наборы средств локальной и сетевой среды для отслеживания качества вызовов всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="95aa7-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="95aa7-119">Независимо от того, где находятся пользователи : локально или через Интернет, вы можете просмотреть качество вызовов для всей организации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="95aa7-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="95aa7-120">С помощью call Data Connector можно выполнять следующие задачи с помощью одного набор инструментов:</span><span class="sxs-lookup"><span data-stu-id="95aa7-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="95aa7-121">Отслеживайте пользовательский интерфейс в Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="95aa7-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="95aa7-122">Просмотр и устранение неполадок в сети</span><span class="sxs-lookup"><span data-stu-id="95aa7-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="95aa7-123">Назначьте роли службы справки и администратора для службы аналитики вызовов, чтобы сотрудники службы могли просматривать и устранять неполадки в их областях ответственности.</span><span class="sxs-lookup"><span data-stu-id="95aa7-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="95aa7-124">Дополнительные сведения см. в подключении [plan Call Data Connector.](../sfbhybrid/hybrid/plan-call-data-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95aa7-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="95aa7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="95aa7-125">See also</span></span>

[<span data-ttu-id="95aa7-126">What's deprecated from Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="95aa7-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
