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
ms.openlocfilehash: fb60e09148f2b96ce9b4d059d7d112c817239822
ms.sourcegitcommit: 355c7858b98518f6a922110390c51eb7e2cd6690
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2021
ms.locfileid: "53147187"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="db4b8-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db4b8-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="db4b8-104">Парк вызовов и извлечение — это функция, которая позволяет пользователю удержание звонка.</span><span class="sxs-lookup"><span data-stu-id="db4b8-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="db4b8-105">При этом служба создает уникальный код для искомого звонка.</span><span class="sxs-lookup"><span data-stu-id="db4b8-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="db4b8-106">Пользователь, который приоовал звонок, или кто-то другой может использовать этот код с поддерживаемой программой или устройством для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="db4b8-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="db4b8-107">(Подробные [сведения см.](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) в Teams.)</span><span class="sxs-lookup"><span data-stu-id="db4b8-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="db4b8-108">Некоторые распространенные сценарии использования парка вызовов:</span><span class="sxs-lookup"><span data-stu-id="db4b8-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="db4b8-109">Администратор регистратора позвонит человеку, который работает на заводе.</span><span class="sxs-lookup"><span data-stu-id="db4b8-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="db4b8-110">После этого регистратор озвучит звонок и номер кода по общедоступным адресным системам.</span><span class="sxs-lookup"><span data-stu-id="db4b8-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="db4b8-111">Пользователь, которому будет звонить, может забрать телефон Teams на заводском цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="db4b8-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="db4b8-112">Пользователь перезаряжает звонок на мобильном устройстве, так как аккумулятор устройства не работает.</span><span class="sxs-lookup"><span data-stu-id="db4b8-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="db4b8-113">Затем пользователь может ввести код, чтобы получить звонок с Teams телефоне.</span><span class="sxs-lookup"><span data-stu-id="db4b8-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="db4b8-114">Представитель службы поддержки отправляет в канале Teams объявление о том, что специалист может получить звонок и помочь клиенту.</span><span class="sxs-lookup"><span data-stu-id="db4b8-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="db4b8-115">Эксперт вводит код в клиенты Teams, чтобы получить звонок</span><span class="sxs-lookup"><span data-stu-id="db4b8-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="db4b8-116">Для приозвать и получить звонки пользователь должен быть Корпоративная голосовая связь и должен быть включен в политику парк звонков.</span><span class="sxs-lookup"><span data-stu-id="db4b8-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="db4b8-117">Парк вызовов и извлечение доступны только Teams [режиме](teams-and-skypeforbusiness-coexistence-and-interoperability.md) развертывания и не поддерживаются Skype для бизнеса IP-телефонах.</span><span class="sxs-lookup"><span data-stu-id="db4b8-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="db4b8-118">Настройка парка вызовов и извлечение</span><span class="sxs-lookup"><span data-stu-id="db4b8-118">Configure call park and retrieve</span></span>

<span data-ttu-id="db4b8-119">Настроить парк вызовов и восстановить Teams может только администратор.</span><span class="sxs-lookup"><span data-stu-id="db4b8-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="db4b8-120">По умолчанию она отключена.</span><span class="sxs-lookup"><span data-stu-id="db4b8-120">It is disabled by default.</span></span> <span data-ttu-id="db4b8-121">Вы можете включить ее для пользователей и создать группы пользователей с помощью политики парков вызовов.</span><span class="sxs-lookup"><span data-stu-id="db4b8-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="db4b8-122">При применении одной и той же политики к набору пользователей они могут припарковать и получать звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="db4b8-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="db4b8-123">Диапазон номеров для звонка предопределен на 10–99 и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="db4b8-123">The range of call pickup numbers is predefined to be from 10-99 and cannot be modified.</span></span> <span data-ttu-id="db4b8-124">Первый приопаркованный звонок будет отрисовлен с кодом 10, следующий приозвать звонок будет отрисовлен с кодом 11 и т. д.</span><span class="sxs-lookup"><span data-stu-id="db4b8-124">The first parked call will be rendered a pickup code of 10, the next parked call will be rendered a pickup code of 11, etc.</span></span> <span data-ttu-id="db4b8-125">до тех пор, пока не будет отрисовка 99 в качестве кода купюпа.</span><span class="sxs-lookup"><span data-stu-id="db4b8-125">until 99 is rendered as a pickup code.</span></span> <span data-ttu-id="db4b8-126">После этого отрисовка кодов pickup еще раз начинается с 10.</span><span class="sxs-lookup"><span data-stu-id="db4b8-126">After which, the rendered pickup codes start over from 10 once again.</span></span>  <span data-ttu-id="db4b8-127">Если имеется более 89 активных звонков, которые находятся в приоплате, отрисованные коды приозвать будут продолжать с приращением после 99 таким образом, что 90-й активный припаркованный звонок будет отрисовлен на 100 для кода получения, то 91-й активный припаркованный звонок будет отрисовован с кодом 101.</span><span class="sxs-lookup"><span data-stu-id="db4b8-127">If there are more than 89 active parked calls, the rendered pickup codes will keep incrementing beyond 99 such that the 90th active parked call would be rendered 100 for a pickup code, the 91st active parked call would be rendered a pickup code of 101.</span></span>

<span data-ttu-id="db4b8-128">Чтобы включить политику парк вызовов</span><span class="sxs-lookup"><span data-stu-id="db4b8-128">To enable a call park policy</span></span>

1. <span data-ttu-id="db4b8-129">В левой области навигации Центра Microsoft Teams перейти **к** политикам парков  >  **голосовых зовов.**</span><span class="sxs-lookup"><span data-stu-id="db4b8-129">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="db4b8-130">На **вкладке Управление политиками** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="db4b8-130">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="db4b8-131">Придайте политике имя, а затем переключение в переключатель **Разрешить парк вызовов** в **переключатель Включит**.</span><span class="sxs-lookup"><span data-stu-id="db4b8-131">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Снимок экрана: параметры политики в парке вызовов](media/call-park-add-policy.png)

4. <span data-ttu-id="db4b8-133">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="db4b8-133">Select **Save**.</span></span>

<span data-ttu-id="db4b8-134">Чтобы изменить политику, выберите ее в списке и нажмите кнопку **Изменить.**</span><span class="sxs-lookup"><span data-stu-id="db4b8-134">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="db4b8-135">Чтобы политика работала, ее необходимо наказать пользователям.</span><span class="sxs-lookup"><span data-stu-id="db4b8-135">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="db4b8-136">Политику [можно назначить пользователям](assign-policies.md) по отдельности или группе.</span><span class="sxs-lookup"><span data-stu-id="db4b8-136">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="db4b8-137">Назначение группы политики парков вызовов</span><span class="sxs-lookup"><span data-stu-id="db4b8-137">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="db4b8-138">На странице **Политики в парке** вызовов на **вкладке Назначение** групповой политики нажмите **кнопку Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="db4b8-138">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="db4b8-139">Найдите группу, которую вы хотите использовать, и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="db4b8-139">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="db4b8-140">Выберите ранг по сравнению с другими заданиями группы.</span><span class="sxs-lookup"><span data-stu-id="db4b8-140">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="db4b8-141">В **группе Выберите политику** выберите политику, для которую вы хотите назначить эту группу.</span><span class="sxs-lookup"><span data-stu-id="db4b8-141">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Park policies image](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="db4b8-143">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="db4b8-143">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db4b8-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="db4b8-144">Related topics</span></span>

[<span data-ttu-id="db4b8-145">Приозвать звонок в Teams</span><span class="sxs-lookup"><span data-stu-id="db4b8-145">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="db4b8-146">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="db4b8-146">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="db4b8-147">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="db4b8-147">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="db4b8-148">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="db4b8-148">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="db4b8-149">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="db4b8-149">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
