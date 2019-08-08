---
title: Развертывание облачной системы голосовой связи
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236768"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="345ec-103">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="345ec-103">Cloud voice deployment</span></span>

<span data-ttu-id="345ec-104">Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также телефонную систему с планами звонков и прямую маршрутизацию телефонной системы, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности звонков и собраний платформы Teams позволяют подключать сторонних участников по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="345ec-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="345ec-105">Для ознакомления с телефонными системами ознакомьтесь со следующими семинарами: [Введение в телефонную систему в Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="345ec-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="345ec-106">Мы будем обновлять эту страницу как дополнительные функции голосовой связи по облаку для Teams с течением времени.</span><span class="sxs-lookup"><span data-stu-id="345ec-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="345ec-107">Аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="345ec-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="345ec-108">Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="345ec-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="345ec-109">Вот что можно сделать с помощью [голосовой конференции](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="345ec-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="345ec-110">Телефонная система с планами звонков (планы звонков) в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="345ec-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="345ec-111">Телефонная система — это функция Office 365, обеспечивающая возможность управления маршрутизацией звонков, политиками и пользователями.</span><span class="sxs-lookup"><span data-stu-id="345ec-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="345ec-112">Сюда входит система управления телефонным подключением, маршрутизация звонков и управление звонками.</span><span class="sxs-lookup"><span data-stu-id="345ec-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="345ec-113">Планы звонков — это надстройка для функции телефонной системы, предоставляемая в Teams и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="345ec-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="345ec-114">Для работы планов звонков в Skype для бизнеса Online требуется, чтобы пользователь был размещен в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="345ec-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="345ec-115">Планы звонков предоставляют сотрудникам компании номер основного номера и могут совершать и принимать телефонные звонки за пределами вашей организации по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="345ec-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="345ec-116">Чтобы узнать больше, ознакомьтесь [с возможностями, которые вы получаете в телефонной системе Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) и [телефонной системы и планов звонков](calling-plan-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="345ec-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [Phone System and Calling Plans](calling-plan-landing-page.md)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="345ec-117">Прямая маршрутизация на телефонную систему (прямая маршрутизация)</span><span class="sxs-lookup"><span data-stu-id="345ec-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="345ec-118">Прямая маршрутизация работает с функцией телефонной системы, чтобы дать сотрудникам вашей организации возможность совершать и принимать телефонные звонки за пределами Организации через сеть PSTN, в которой связь по протоколу PSTN обеспечивается с помощью сторонних поставщиков услуг.</span><span class="sxs-lookup"><span data-stu-id="345ec-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="345ec-119">Чтобы узнать больше, прочтите [маршрут на прямую маршрутизацию](direct-routing-plan.md) и [Настройте прямую маршрутизацию](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="345ec-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="345ec-120">Практические рекомендации по голосовой конференции, тарифные планы и прямую маршрутизацию в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="345ec-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="345ec-121">Это практическое руководство организовано с помощью инфраструктуры Office 365 FastTrack и ее трех фаз&mdash;, а также их значения.</span><span class="sxs-lookup"><span data-stu-id="345ec-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="345ec-122">Она предназначена для того, чтобы помочь вам планировать, добиваться и выполнять успешные видеоконференции, планы звонков или прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="345ec-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="345ec-123">Выработка концепции</span><span class="sxs-lookup"><span data-stu-id="345ec-123">Envision</span></span>  |<span data-ttu-id="345ec-124">Адаптация</span><span class="sxs-lookup"><span data-stu-id="345ec-124">Onboard</span></span>  |<span data-ttu-id="345ec-125">Извлечение выгоды</span><span class="sxs-lookup"><span data-stu-id="345ec-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="345ec-126">Определение показателей успеха</span><span class="sxs-lookup"><span data-stu-id="345ec-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="345ec-127">Принятие моих решений в службе</span><span class="sxs-lookup"><span data-stu-id="345ec-127">Make my service decisions for</span></span> <br><span data-ttu-id="345ec-128">&nbsp;&nbsp;[Голосовые конференции](2-envision-make-my-service-decisions-audio-conferencing.md),</span><span class="sxs-lookup"><span data-stu-id="345ec-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="345ec-129">&nbsp;&nbsp;[Планы звонков](2-envision-make-my-service-decisions-phone-system.md)или [Прямая маршрутизация](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="345ec-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="345ec-130">Оценка среды</span><span class="sxs-lookup"><span data-stu-id="345ec-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="345ec-131">Планирование управления службами</span><span class="sxs-lookup"><span data-stu-id="345ec-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="345ec-132">Планирование работы пользователей</span><span class="sxs-lookup"><span data-stu-id="345ec-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="345ec-133">Документирование плана по достижению успеха</span><span class="sxs-lookup"><span data-stu-id="345ec-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="345ec-134">Подготовка службы</span><span class="sxs-lookup"><span data-stu-id="345ec-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="345ec-135">Подготовка пользователей</span><span class="sxs-lookup"><span data-stu-id="345ec-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="345ec-136">Развертывание службы</span><span class="sxs-lookup"><span data-stu-id="345ec-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="345ec-137">Использование службы</span><span class="sxs-lookup"><span data-stu-id="345ec-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="345ec-138">Улучшение службы</span><span class="sxs-lookup"><span data-stu-id="345ec-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="345ec-139">Содержимое представлено в упорядоченном виде, и оно предназначено для создания сквозного развертывания с начала до конца.</span><span class="sxs-lookup"><span data-stu-id="345ec-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="345ec-140">Если вы уже активно развернут, мы по-прежнему рекомендуем вам ссылаться на нужные области контента.</span><span class="sxs-lookup"><span data-stu-id="345ec-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="345ec-141">В этом практическом руководстве мы предоставляем примеры выходных данных для каждого действия и ключевой дискуссии.</span><span class="sxs-lookup"><span data-stu-id="345ec-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="345ec-142">Примеры в этом документе заключены между выносками TIP и служат шаблоном, который можно использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="345ec-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="345ec-143">Вы увидите "Тба" (Добавить) для получения информации, которая должна быть выполнена в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="345ec-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
