---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Узнайте, как использовать парк вызовов и восстановить для удержания звонка в Microsoft Teams.
ms.openlocfilehash: efc36a2bc90b64abf2e886c5e768a26704bd6550
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102805"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="7da82-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7da82-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="7da82-104">Парк вызовов и его извлечение — это функция, которая позволяет пользователю удержание звонка.</span><span class="sxs-lookup"><span data-stu-id="7da82-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="7da82-105">При приостровке звонка служба создает уникальный код для искомого звонка.</span><span class="sxs-lookup"><span data-stu-id="7da82-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="7da82-106">Пользователь, приодервший звонок, или кто-то другой может использовать этот код с поддерживаемой программой или устройством для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="7da82-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="7da82-107">(Подробные [сведения см. в теме "Приозвать звонок в](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) Teams".)</span><span class="sxs-lookup"><span data-stu-id="7da82-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="7da82-108">Некоторые распространенные сценарии использования парка вызовов:</span><span class="sxs-lookup"><span data-stu-id="7da82-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="7da82-109">Регистратор звонит кому-то, кто работает на заводе.</span><span class="sxs-lookup"><span data-stu-id="7da82-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="7da82-110">После этого регистратор озвучит звонок и номер кода по адресной системе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="7da82-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="7da82-111">Пользователь, которому необходимо позвонить, может забрать телефон Teams на заводском цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="7da82-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="7da82-112">Пользователь перезазовет звонок на мобильном устройстве, так как аккумулятор устройства не работает.</span><span class="sxs-lookup"><span data-stu-id="7da82-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="7da82-113">Затем пользователь может ввести код, чтобы получить звонок с рабочего телефона Teams.</span><span class="sxs-lookup"><span data-stu-id="7da82-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="7da82-114">Представитель службы поддержки отмечает звонок клиента и отправляет в канале Teams объявление эксперту, чтобы получить звонок и помочь клиенту.</span><span class="sxs-lookup"><span data-stu-id="7da82-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="7da82-115">Эксперт вводит код в клиентах Teams для получения звонка</span><span class="sxs-lookup"><span data-stu-id="7da82-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="7da82-116">Чтобы приозвать и восстановить вызовы, пользователь должен быть Корпоративная голосовая связь и быть включен в политику парка вызовов.</span><span class="sxs-lookup"><span data-stu-id="7da82-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="7da82-117">Парк звонков и извлечение доступны только в режиме развертывания [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) и не поддерживаются в IP-телефонах Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7da82-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="7da82-118">Настройка парка вызовов и извлечение</span><span class="sxs-lookup"><span data-stu-id="7da82-118">Configure call park and retrieve</span></span>

<span data-ttu-id="7da82-119">Настроить парк вызовов и восстановить их может только администратор Teams.</span><span class="sxs-lookup"><span data-stu-id="7da82-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="7da82-120">По умолчанию она отключена.</span><span class="sxs-lookup"><span data-stu-id="7da82-120">It is disabled by default.</span></span> <span data-ttu-id="7da82-121">Вы можете включить ее для пользователей и создать группы пользователей с помощью политики парка вызовов.</span><span class="sxs-lookup"><span data-stu-id="7da82-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="7da82-122">После применения одной и той же политики к набору пользователей они могут приобирать и извлекать звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="7da82-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="7da82-123">Чтобы включить политику парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="7da82-123">To enable a call park policy</span></span>

1. <span data-ttu-id="7da82-124">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политикам в парке  >  **голосовых вызовов.**</span><span class="sxs-lookup"><span data-stu-id="7da82-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="7da82-125">На **вкладке "Управление политиками"** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="7da82-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="7da82-126">Придайте политике имя, а затем переключение в переключатель "Разрешить **парк вызовов"** в **"Включит".**</span><span class="sxs-lookup"><span data-stu-id="7da82-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Снимок экрана: параметры политики в парке вызовов](media/call-park-add-policy.png)

4. <span data-ttu-id="7da82-128">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="7da82-128">Select **Save**.</span></span>

<span data-ttu-id="7da82-129">Чтобы изменить политику, выберите ее в списке и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="7da82-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="7da82-130">Чтобы политика работала, она должна быть назначена пользователям.</span><span class="sxs-lookup"><span data-stu-id="7da82-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="7da82-131">Политику [можно назначить отдельным пользователям](assign-policies.md) или группе.</span><span class="sxs-lookup"><span data-stu-id="7da82-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="7da82-132">Назначение политики части звонка группе</span><span class="sxs-lookup"><span data-stu-id="7da82-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="7da82-133">На странице **"Политики парка вызовов"** на **вкладке** назначения групповой политики нажмите кнопку **"Добавить группу".**</span><span class="sxs-lookup"><span data-stu-id="7da82-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="7da82-134">Найдите группу, которую вы хотите использовать, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="7da82-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="7da82-135">Выбирайте ранг по сравнению с другими назначениями групп.</span><span class="sxs-lookup"><span data-stu-id="7da82-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="7da82-136">В **группе "Выберите политику"** выберите политику, которую вы хотите назначить этой группе.</span><span class="sxs-lookup"><span data-stu-id="7da82-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Park policies image](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="7da82-138">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="7da82-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7da82-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7da82-139">Related topics</span></span>

[<span data-ttu-id="7da82-140">Приозвать звонок в Teams</span><span class="sxs-lookup"><span data-stu-id="7da82-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="7da82-141">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="7da82-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="7da82-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="7da82-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="7da82-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="7da82-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="7da82-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="7da82-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)