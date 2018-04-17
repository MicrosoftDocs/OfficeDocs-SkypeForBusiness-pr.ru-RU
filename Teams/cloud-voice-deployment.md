---
title: Развертывание облачной системы голосовой связи
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="5e8c2-103">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5e8c2-103">Cloud voice deployment</span></span>

<span data-ttu-id="5e8c2-104">Группами Майкрософт, сервер-концентратор для работы и коммуникации в Office 365, теперь предоставляет звук конференц-связи и телефонной системой с возможностями вызов планы в соответствии с путем расширение собрания групп и вызова интерфейса должна включать дополнительные бизнес-требований внешние стороны подключается с помощью телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="5e8c2-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="5e8c2-105">Со временем мы будем обновлять эту страницу по мере выпуска в Microsoft Teams новых функций облачной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="5e8c2-106">Аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e8c2-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="5e8c2-107">Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="5e8c2-108">Ниже указано, что именно вы получаете вместе с [Аудиоконференциями](https://go.microsoft.com/fwlink/?linkid=858992) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="5e8c2-109">Система телефон с Тарифные планы в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e8c2-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="5e8c2-110">Телефонная система — это компонент Office 365, позволяющий управлять маршрутизацией звонков, политиками и подготовкой пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="5e8c2-111">В него входит система управления телефонными звонками, маршрутизация звонков и настройка отдельных звонков.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="5e8c2-112">Планы звонков Office 365 представляют собой дополнительный компонент для службы телефонной системы, поставляемый с приложениями Teams и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="5e8c2-113">Тарифные планы предоставления людей в бизнеса с помощью основного телефонного номера и позволяет их выполнение и прием телефонных звонков за пределами вашей организации по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="5e8c2-114">Дополнительные сведения см. в разделах [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) (Возможности телефонной системы в Office 365) и [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429) (Общие сведения о планах звонков в Office 365).</span><span class="sxs-lookup"><span data-stu-id="5e8c2-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="5e8c2-115">Практическое руководство по конференц-связи звук и телефон системы с помощью вызова планы в группах Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e8c2-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="5e8c2-116">С помощью платформы реализация клиента Office 365 эту организован этого практического руководства и его три этапы&mdash;Предвидения, встроенный и значение диска.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="5e8c2-117">Его своей целью помогут спланировать, доставки и использовать успешные аудиоконференции или телефонной системой с реализацией вызов планы.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="5e8c2-118">Выработка концепции</span><span class="sxs-lookup"><span data-stu-id="5e8c2-118">Envision</span></span>  |<span data-ttu-id="5e8c2-119">Адаптация</span><span class="sxs-lookup"><span data-stu-id="5e8c2-119">Onboard</span></span>  |<span data-ttu-id="5e8c2-120">Извлечение выгоды</span><span class="sxs-lookup"><span data-stu-id="5e8c2-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5e8c2-121">Определение Мой success</span><span class="sxs-lookup"><span data-stu-id="5e8c2-121">Define my success</span></span> <br> <span data-ttu-id="5e8c2-122">Мои проведения службы</span><span class="sxs-lookup"><span data-stu-id="5e8c2-122">Make my service decisions</span></span> <br> <span data-ttu-id="5e8c2-123">Оценка моей среды</span><span class="sxs-lookup"><span data-stu-id="5e8c2-123">Evaluate my environment</span></span> <br> <span data-ttu-id="5e8c2-124">Планирование управления Мои службы</span><span class="sxs-lookup"><span data-stu-id="5e8c2-124">Plan my service management</span></span> <br> <span data-ttu-id="5e8c2-125">Планирование взаимодействия пользователя Мои пользователи</span><span class="sxs-lookup"><span data-stu-id="5e8c2-125">Plan my users' experience</span></span> <br> <span data-ttu-id="5e8c2-126">Документ успешно план</span><span class="sxs-lookup"><span data-stu-id="5e8c2-126">Document my success plan</span></span>    | <span data-ttu-id="5e8c2-127">Подготовка Мои службы</span><span class="sxs-lookup"><span data-stu-id="5e8c2-127">Prepare my service</span></span> <br> <span data-ttu-id="5e8c2-128">Подготовка Мои пользователи</span><span class="sxs-lookup"><span data-stu-id="5e8c2-128">Prepare my users</span></span> <br> <span data-ttu-id="5e8c2-129">Развернуть службу</span><span class="sxs-lookup"><span data-stu-id="5e8c2-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="5e8c2-130">Мои службы</span><span class="sxs-lookup"><span data-stu-id="5e8c2-130">Operate my service</span></span> <br> <span data-ttu-id="5e8c2-131">Улучшите Мои службы</span><span class="sxs-lookup"><span data-stu-id="5e8c2-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="5e8c2-132">Контент в упорядоченном виде и предназначен для ознакомления реализация-сквозного развертывания от начала до конца.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="5e8c2-133">Если вы уже активно выполняется развертывание, по-прежнему рекомендуется для ссылки применимых области контента.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="5e8c2-134">В этом практического руководства мы предлагаем что выводится для каждого действия и ключевые обсуждений.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="5e8c2-135">Примеры в данном документе заключаются внутри выносок подсказки, и они могут использоваться в качестве шаблона, который можно повторно использовать.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="5e8c2-136">Вы увидите сообщение "Подлежит добавлению" на месте информации, которую вам нужно указать в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="5e8c2-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>