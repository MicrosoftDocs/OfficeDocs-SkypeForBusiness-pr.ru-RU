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
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197584"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="1b763-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b763-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="1b763-104">Парк вызовов и извлечение — это функция, которая позволяет пользователю удержание звонка.</span><span class="sxs-lookup"><span data-stu-id="1b763-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="1b763-105">При этом служба создает уникальный код для искомого звонка.</span><span class="sxs-lookup"><span data-stu-id="1b763-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="1b763-106">Пользователь, который приоовал звонок, или кто-то другой может использовать этот код с поддерживаемой программой или устройством для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="1b763-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="1b763-107">(Подробные [сведения см.](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) в Teams.)</span><span class="sxs-lookup"><span data-stu-id="1b763-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="1b763-108">Некоторые распространенные сценарии использования парка вызовов:</span><span class="sxs-lookup"><span data-stu-id="1b763-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="1b763-109">Администратор регистратора позвонит человеку, который работает на заводе.</span><span class="sxs-lookup"><span data-stu-id="1b763-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="1b763-110">После этого регистратор озвучит звонок и номер кода по общедоступным адресным системам.</span><span class="sxs-lookup"><span data-stu-id="1b763-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="1b763-111">Пользователь, которому будет звонить, может забрать телефон Teams на заводском цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="1b763-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="1b763-112">Пользователь перезаряжает звонок на мобильном устройстве, так как аккумулятор устройства не работает.</span><span class="sxs-lookup"><span data-stu-id="1b763-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="1b763-113">Затем пользователь может ввести код, чтобы получить звонок с Teams телефоне.</span><span class="sxs-lookup"><span data-stu-id="1b763-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="1b763-114">Представитель службы поддержки отправляет в канале Teams объявление, чтобы специалисту было необходимо получить звонок и помочь клиенту.</span><span class="sxs-lookup"><span data-stu-id="1b763-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="1b763-115">Эксперт вводит код в клиенты Teams, чтобы получить звонок</span><span class="sxs-lookup"><span data-stu-id="1b763-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="1b763-116">Для приозвать и получить звонки пользователь должен быть Корпоративная голосовая связь и должен быть включен в политику парков звонков.</span><span class="sxs-lookup"><span data-stu-id="1b763-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="1b763-117">Парк вызовов и извлечение доступны только Teams [режиме](teams-and-skypeforbusiness-coexistence-and-interoperability.md) развертывания и не поддерживаются Skype для бизнеса IP-телефонах.</span><span class="sxs-lookup"><span data-stu-id="1b763-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="1b763-118">Настройка парка вызовов и извлечение</span><span class="sxs-lookup"><span data-stu-id="1b763-118">Configure call park and retrieve</span></span>

<span data-ttu-id="1b763-119">Чтобы настроить парк Teams и восстановить его, необходимо быть администратором.</span><span class="sxs-lookup"><span data-stu-id="1b763-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="1b763-120">По умолчанию она отключена.</span><span class="sxs-lookup"><span data-stu-id="1b763-120">It is disabled by default.</span></span> <span data-ttu-id="1b763-121">Вы можете включить ее для пользователей и создать группы пользователей с помощью политики парков вызовов.</span><span class="sxs-lookup"><span data-stu-id="1b763-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="1b763-122">При применении одной и той же политики к набору пользователей они могут припарковать и получать звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="1b763-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="1b763-123">Чтобы включить политику парк вызовов</span><span class="sxs-lookup"><span data-stu-id="1b763-123">To enable a call park policy</span></span>

1. <span data-ttu-id="1b763-124">В левой области навигации центра администрирования Microsoft Teams политики парков  >  **голосовых зовов.**</span><span class="sxs-lookup"><span data-stu-id="1b763-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="1b763-125">На **вкладке Управление политиками** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1b763-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="1b763-126">Придайте политике имя, а затем переключение в переключатель **Разрешить парк вызовов** **включит**.</span><span class="sxs-lookup"><span data-stu-id="1b763-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Снимок экрана: параметры политики в парке вызовов](media/call-park-add-policy.png)

4. <span data-ttu-id="1b763-128">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1b763-128">Select **Save**.</span></span>

<span data-ttu-id="1b763-129">Чтобы изменить политику, выберите ее в списке и нажмите кнопку **Изменить.**</span><span class="sxs-lookup"><span data-stu-id="1b763-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="1b763-130">Чтобы политика работала, ее необходимо наказать пользователям.</span><span class="sxs-lookup"><span data-stu-id="1b763-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="1b763-131">Политику [можно назначить пользователям](assign-policies.md) по отдельности или группе.</span><span class="sxs-lookup"><span data-stu-id="1b763-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="1b763-132">Назначение группы политики парков вызовов</span><span class="sxs-lookup"><span data-stu-id="1b763-132">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="1b763-133">На странице **Политики в парке** вызовов на **вкладке Назначение** групповой политики нажмите **кнопку Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="1b763-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="1b763-134">Найдите группу, которую вы хотите использовать, и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="1b763-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="1b763-135">Выберите ранг по сравнению с другими заданиями группы.</span><span class="sxs-lookup"><span data-stu-id="1b763-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="1b763-136">В **группе Выберите политику** выберите политику, для которую вы хотите назначить эту группу.</span><span class="sxs-lookup"><span data-stu-id="1b763-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Park policies image](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="1b763-138">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="1b763-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b763-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1b763-139">Related topics</span></span>

[<span data-ttu-id="1b763-140">Приозвать звонок в Teams</span><span class="sxs-lookup"><span data-stu-id="1b763-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="1b763-141">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="1b763-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="1b763-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1b763-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="1b763-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1b763-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="1b763-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="1b763-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)