---
title: Руководство для ИТ-администраторов по Reflect в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Руководство для ИТ-администраторов по Reflect в Microsoft Teams для образования.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fb7dc36dc08677d0f6dd1e849383b7e146c972b
ms.sourcegitcommit: bbf44378373668899d338d56cde4c92cc31202c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52070655"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a><span data-ttu-id="fcf20-103">Руководство для ИТ-администраторов по Reflect в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcf20-103">IT Admin Guide to Reflect in Microsoft Teams</span></span>

<span data-ttu-id="fcf20-104">Этот документ содержит сведения о [Reflect](https://aka.ms/reflect) — неотъемлемой части [Insights для образования в Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="fcf20-104">This document provides information concerning [Reflect](https://aka.ms/reflect) – an integral part of [Education Insights in Microsoft Teams](class-insights.md).</span></span> <span data-ttu-id="fcf20-105">Reflect помогает учащимся распознавать свои эмоции и управлять ими, предоставляя регулярные возможности поделиться ощущениями и быть услышанными.</span><span class="sxs-lookup"><span data-stu-id="fcf20-105">Reflect helps students recognize and navigate their emotions by providing regular opportunities to share and be heard.</span></span> <span data-ttu-id="fcf20-106">Reflect помогает расширить эмоциональный словарь учащихся и развить умение сочувствовать сверстникам, а также предоставляет педагогам ценную обратную связь для обеспечения здоровой атмосферы в школьном сообществе.</span><span class="sxs-lookup"><span data-stu-id="fcf20-106">Reflect can help broaden learners' emotional vocabulary and deepen empathy for their peers while also providing valuable feedback to educators for a healthy classroom community.</span></span>

<span data-ttu-id="fcf20-107">Это приложение для регистрации использует эмодзи и детализацию эмоций на основе результатов исследований, помогая преподавателям добавлять обучение социальным и эмоциональным навыкам в учебную программу, и без того перегруженную.</span><span class="sxs-lookup"><span data-stu-id="fcf20-107">This check-in app uses emojis and research-backed emotional granularity to support educators in adding social and emotional learning into their already busy routine.</span></span>


## <a name="privacy-and-security"></a><span data-ttu-id="fcf20-108">Конфиденциальность и безопасность</span><span class="sxs-lookup"><span data-stu-id="fcf20-108">Privacy and Security</span></span>
<span data-ttu-id="fcf20-109">Reflect отвечает тем же стандартам конфиденциальности и безопасности, что и Insights для образования, чтобы защитить конфиденциальную информацию учащихся.</span><span class="sxs-lookup"><span data-stu-id="fcf20-109">Reflect follows the same privacy and security standards as Education Insights to protect students' sensitive information.</span></span>

<span data-ttu-id="fcf20-110">Информация, собираемая и публикуемая в Reflect, отвечает требованиям [более чем 90 нормативных и отраслевых стандартов](/compliance/regulatory/offering-home), включая [GDPR](/compliance/regulatory/gdpr) и [Закон о правах семьи на образование и неприкосновенность частной жизни (FERPA)](/compliance/regulatory/offering-ferpa), обеспечивающих безопасность учащихся и детей, а также требованиям других подобных нормативных актов, регулирующих обеспечение конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="fcf20-110">The information collected and shown through Reflect meets [more than 90 regulatory and industry standards](/compliance/regulatory/offering-home), including [GDPR](/compliance/regulatory/gdpr) and the Family [Education Rights and Privacy Act (FERPA)](/compliance/regulatory/offering-ferpa) for students and children's security and other, similar, privacy-oriented regulations.</span></span>

<span data-ttu-id="fcf20-111">Учащиеся *никогда* не видят имена других учащихся — только их реакцию.</span><span class="sxs-lookup"><span data-stu-id="fcf20-111">Students *never* see the names of other students, only how they responded.</span></span> <span data-ttu-id="fcf20-112">Они могут видеть распределение ответов, но *не* имена, связанные с конкретным отражением.</span><span class="sxs-lookup"><span data-stu-id="fcf20-112">While they can see the distribution of responses, they *cannot* see names associated with each reflection.</span></span> 

> [!NOTE]
> <span data-ttu-id="fcf20-113">Если ответили менее пяти учащихся, данные ответа не демонстрируются другим учащимся.</span><span class="sxs-lookup"><span data-stu-id="fcf20-113">If less than five students respond, no data is shown to the students.</span></span> <span data-ttu-id="fcf20-114">Это позволяет свести к минимуму вероятность того, что учащиеся смогут определить, кто как ответил.</span><span class="sxs-lookup"><span data-stu-id="fcf20-114">This is to minimize the possibility of students identifying each other's responses.</span></span>

## <a name="data-collection-and-storage"></a><span data-ttu-id="fcf20-115">Сбор и хранение данных</span><span class="sxs-lookup"><span data-stu-id="fcf20-115">Data collection and storage</span></span>
<span data-ttu-id="fcf20-116">Данные принадлежат учебному заведению, и Майкрософт лишь собирает и хранит их.</span><span class="sxs-lookup"><span data-stu-id="fcf20-116">The data belongs to the educational institution, and Microsoft only collects the data and stores it.</span></span> <span data-ttu-id="fcf20-117">Сотрудники Майкрософт не имеют доступа к данным и не могут просматривать их, кроме как для доступа под наблюдением, осуществляемого для поддержания работы сервиса — например, для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="fcf20-117">Microsoft personnel cannot access the data or see it, except as allowed by compliance in an audited way to maintain the service, such as data recovery.</span></span>

<span data-ttu-id="fcf20-118">Данные хранятся в Insights для образования.</span><span class="sxs-lookup"><span data-stu-id="fcf20-118">The data is stored in Education Insights.</span></span> <span data-ttu-id="fcf20-119">По умолчанию компонент "Insights для образования" включен.</span><span class="sxs-lookup"><span data-stu-id="fcf20-119">By default, Education Insights is turned on.</span></span> <span data-ttu-id="fcf20-120">Если вы отказались от его использования, мы **удаляем все данные, собранные для Reflect**.</span><span class="sxs-lookup"><span data-stu-id="fcf20-120">When you opt-out, we **delete all the data collected for Reflect**.</span></span> <span data-ttu-id="fcf20-121">Если вы снова включите Insights для образования, мы начнем собирать данные с момента повторного включения.</span><span class="sxs-lookup"><span data-stu-id="fcf20-121">Turn Education Insights back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="fcf20-122">В [руководстве для ИТ-администраторов по Insights для образования](class-insights.md) вы можете узнать, как работает Insights для образования (в том числе где хранятся данные) и [как отключить или включить Insights для образования](class-insights.md#turn-insights-off-or-on), если вы хотите удалить данные или начать пользоваться этой службой.</span><span class="sxs-lookup"><span data-stu-id="fcf20-122">In the [IT Admin Guide to Education Insights](class-insights.md), you can read how Education Insights works (including storage locations) and [how to turn Education Insights off or on](class-insights.md#turn-insights-off-or-on) when you want to delete the data or enable the service.</span></span>

<span data-ttu-id="fcf20-123">Данные учащихся собираются системой Reflect, однако гостевая информация не собирается.</span><span class="sxs-lookup"><span data-stu-id="fcf20-123">Data is collected from student in Reflect, though guest data is not collected.</span></span> <span data-ttu-id="fcf20-124">**Если учащийся определен как гость, его данные не собираются.**</span><span class="sxs-lookup"><span data-stu-id="fcf20-124">**If a student is defined as a guest, their data is not collected.**</span></span> 

## <a name="enable-reflect"></a><span data-ttu-id="fcf20-125">Включить Reflect</span><span class="sxs-lookup"><span data-stu-id="fcf20-125">Enable Reflect</span></span>
<span data-ttu-id="fcf20-126">Если вы управляете политикой установки приложений для своего учреждения, убедитесь, что Reflect *разрешен* в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fcf20-126">If you manage the app setup policy for your institution, ensure that Reflect is *allowed* in your tenant.</span></span> <span data-ttu-id="fcf20-127">Можно также добавить Reflect в соответствующие классные команды в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf20-127">You can also add Reflect to the relevant class teams from the Teams admin center.</span></span>

<span data-ttu-id="fcf20-128">Чтобы разрешить пользователю устанавливать какое-либо приложение и взаимодействовать с ним, необходимо разрешить это приложение на уровне организации на странице **Управление приложениями** и **политики разрешений приложения**, назначенной пользователю.</span><span class="sxs-lookup"><span data-stu-id="fcf20-128">To enable a user to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and the **app permission policy** assigned to the user.</span></span>

<span data-ttu-id="fcf20-129">Если вы ранее определили, что каждое приложение должно быть разрешено, перейдите на страницу "Управление приложениями" и "разрешите" Reflect.</span><span class="sxs-lookup"><span data-stu-id="fcf20-129">If you have previously defined that each app needs to be allowed, please go to the Manage apps page and 'allow' Reflect.</span></span> <span data-ttu-id="fcf20-130">**Если вы заблокировали приложение, оно не появляется в Teams ни для каких пользователей в вашей организации.**</span><span class="sxs-lookup"><span data-stu-id="fcf20-130">**When you block an app, the app doesn't appear in Teams for any users in your organization.**</span></span>

> [!NOTE]
> <span data-ttu-id="fcf20-131">Чтобы получить доступ к приложению Reflect, вам потребуется лицензия A1, A3 или A5 для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fcf20-131">To have access to the Reflect app, you will need an A1, A3, or A5 license for Microsoft 365.</span></span>

> [!TIP]
> <span data-ttu-id="fcf20-132">Дополнительные сведения можно найти в статье о том, [как разрешить приложение или добавить его в команду класса](manage-apps.md#allow-and-block-apps).</span><span class="sxs-lookup"><span data-stu-id="fcf20-132">For more details, read [how to allow an app or to add it to a class team](manage-apps.md#allow-and-block-apps).</span></span>

## <a name="where-do-educators-find-reflect"></a><span data-ttu-id="fcf20-133">Где преподаватели берут Reflect?</span><span class="sxs-lookup"><span data-stu-id="fcf20-133">Where do educators find Reflect?</span></span>
<span data-ttu-id="fcf20-134">После включения Reflect преподаватели могут перейти в класс и выбрать **Новая беседа**.</span><span class="sxs-lookup"><span data-stu-id="fcf20-134">Once you have enabled Reflect, educators go to the class and select **New Conversation**.</span></span> <span data-ttu-id="fcf20-135">Затем нужно выбрать **...**, чтобы появились доступные расширения для обмена сообщениями, и ввести **Reflect** в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="fcf20-135">They then select '**…**' to bring up messaging extensions and enter **Reflect** in the search bar.</span></span> <span data-ttu-id="fcf20-136">Диалоговое окно предоставляет пошаговые инструкции, помогающие сформулировать вопрос и определить, кто из пользователей что может увидеть.</span><span class="sxs-lookup"><span data-stu-id="fcf20-136">The dialog box guides them through defining the question and who can see what.</span></span>

:::image type="content" source="media/reflect-add-app.png" alt-text="Добавить Reflect в команду класса":::

<span data-ttu-id="fcf20-138">Пользователи могут щелкнуть правой кнопкой мыши значок Reflect и выбрать **Закрепить** для удобства доступа.</span><span class="sxs-lookup"><span data-stu-id="fcf20-138">They can right-click on the Reflect icon and select **Pin** for easy access.</span></span>

:::image type="content" source="media/reflect-pin-app.png" alt-text="Закрепление приложения Reflect":::

> [!TIP]
> <span data-ttu-id="fcf20-140">Приложение Reflect можно также найти по этой ссылке: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span><span class="sxs-lookup"><span data-stu-id="fcf20-140">You can also locate the Reflect app through this link: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span></span>

> [!TIP]
> <span data-ttu-id="fcf20-141">Подробнее см. [страницу поддержки Reflect](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span><span class="sxs-lookup"><span data-stu-id="fcf20-141">For more details, visit [Reflect support page](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span></span> <span data-ttu-id="fcf20-142">На этой странице приводятся рекомендации для преподавателей и учащихся, а также инструкции, помогающие впервые зарегистрироваться в Reflect.</span><span class="sxs-lookup"><span data-stu-id="fcf20-142">This page provides guidelines for both educators and students and helps with how to create their first Reflect check-in.</span></span>
