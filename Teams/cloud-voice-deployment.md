---
title: Развертывание облачной системы голосовой связи
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4089e0e9ff9ce0ecbff63e55a43d2dc9f2ca7d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194759"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="fe23c-103">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="fe23c-103">Cloud voice deployment</span></span>

<span data-ttu-id="fe23c-104">Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также телефонную систему с планами звонков и прямую маршрутизацию телефонной системы, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности звонков и собраний платформы Teams позволяют подключать сторонних участников по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="fe23c-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="fe23c-105">Просмотрите следующие сеанса основные сведения о телефонных систем: [Знакомство с телефонной системой в группах Майкрософт](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="fe23c-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="fe23c-106">На этой странице будут обновляться облачных дополнительные функции голосовой связи для групп будут выпущены по времени.</span><span class="sxs-lookup"><span data-stu-id="fe23c-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="fe23c-107">Аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe23c-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="fe23c-108">Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="fe23c-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="fe23c-109">Вот, вы получаете с [Аудио конференц-связи](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe23c-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="fe23c-110">Система телефон с Тарифные планы («Тарифные планы») в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fe23c-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="fe23c-111">Телефонной системой — это функция Office 365, которая предоставляет возможность управлять маршрутизации вызовов, политик и подготовке пользователей.</span><span class="sxs-lookup"><span data-stu-id="fe23c-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="fe23c-112">Этот компонент включает телефонного звонка система управления маршрутизации вызовов и управления звонками.</span><span class="sxs-lookup"><span data-stu-id="fe23c-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="fe23c-113">Тарифные планы является дополнительной службы для функции телефонной системой, доставленных через рабочих групп и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="fe23c-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="fe23c-114">Тарифные планы требуется, что пользователь быть размещен в Скайп для бизнеса в Интернет для работы в группах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe23c-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="fe23c-115">Тарифные планы обеспечивают для сотрудников в бизнесе с основной номер телефона, а также позволяет их выполнение и прием телефонных звонков за пределами вашей организации по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="fe23c-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="fe23c-116">Чтобы получить дополнительные сведения, ознакомиться с [вот вы получаете с телефонной системой в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) и [телефонной системой и вызов планов](calling-plan-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="fe23c-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [Phone System and Calling Plans](calling-plan-landing-page.md)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="fe23c-117">Телефон системы прямой маршрутизации («Прямая отправка»)</span><span class="sxs-lookup"><span data-stu-id="fe23c-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="fe23c-118">Прямое works маршрутизации с телефонной системой компонентом, позволяют сотрудникам вашей организации выполнение и прием телефонных звонков за пределами организации сети PSTN, где подключение к ТСОП предоставляется через поставщиков услуг сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="fe23c-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="fe23c-119">Дополнительные сведения, ознакомьтесь с [Планирование прямого](direct-routing-plan.md) и [Настроить прямое маршрутизации](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="fe23c-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="fe23c-120">Практическое руководство по конференц-связи звук, вызов планы и прямой маршрутизации в группах Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe23c-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="fe23c-121">С помощью платформы реализация клиента Office 365 эту организован этого практического руководства и его три этапы&mdash;Предвидения, встроенный и значение диска.</span><span class="sxs-lookup"><span data-stu-id="fe23c-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="fe23c-122">Он своей целью помогут спланировать, доставки и использовать успешной реализации звук, вызов планы и/или прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fe23c-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="fe23c-123">Выработка концепции</span><span class="sxs-lookup"><span data-stu-id="fe23c-123">Envision</span></span>  |<span data-ttu-id="fe23c-124">Адаптация</span><span class="sxs-lookup"><span data-stu-id="fe23c-124">Onboard</span></span>  |<span data-ttu-id="fe23c-125">Извлечение выгоды</span><span class="sxs-lookup"><span data-stu-id="fe23c-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="fe23c-126">Определение показателей успеха</span><span class="sxs-lookup"><span data-stu-id="fe23c-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="fe23c-127">Проведения Мои службы</span><span class="sxs-lookup"><span data-stu-id="fe23c-127">Make my service decisions for</span></span> <br><span data-ttu-id="fe23c-128">&nbsp;&nbsp;[Аудиоконференции](2-envision-make-my-service-decisions-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="fe23c-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="fe23c-129">&nbsp;&nbsp;[Тарифные планы](2-envision-make-my-service-decisions-phone-system.md)или [прямой маршрутизации](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="fe23c-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="fe23c-130">Оценка среды</span><span class="sxs-lookup"><span data-stu-id="fe23c-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="fe23c-131">Планирование управления службами</span><span class="sxs-lookup"><span data-stu-id="fe23c-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="fe23c-132">Планирование взаимодействия пользователя Мои пользователи</span><span class="sxs-lookup"><span data-stu-id="fe23c-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="fe23c-133">Документирование плана по достижению успеха</span><span class="sxs-lookup"><span data-stu-id="fe23c-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="fe23c-134">Подготовка службы</span><span class="sxs-lookup"><span data-stu-id="fe23c-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="fe23c-135">Подготовка пользователей</span><span class="sxs-lookup"><span data-stu-id="fe23c-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="fe23c-136">Развертывание службы</span><span class="sxs-lookup"><span data-stu-id="fe23c-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="fe23c-137">Использование службы</span><span class="sxs-lookup"><span data-stu-id="fe23c-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="fe23c-138">Улучшение службы</span><span class="sxs-lookup"><span data-stu-id="fe23c-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="fe23c-139">Контент в упорядоченном виде и предназначен для ознакомления реализация-сквозного развертывания от начала до конца.</span><span class="sxs-lookup"><span data-stu-id="fe23c-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="fe23c-140">Если вы уже активно выполняется развертывание, по-прежнему рекомендуется для ссылки применимых области контента.</span><span class="sxs-lookup"><span data-stu-id="fe23c-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="fe23c-141">В этом практического руководства мы предоставляем выводится для каждого действия и ключевые обсуждений.</span><span class="sxs-lookup"><span data-stu-id="fe23c-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="fe23c-142">Примеры в данном документе заключаются внутри выносок подсказки, и они могут использоваться в качестве шаблона, который можно повторно использовать.</span><span class="sxs-lookup"><span data-stu-id="fe23c-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="fe23c-143">Вы увидите «TBA» (для добавления) сведения, которые необходимо выполнить как часть процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="fe23c-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
