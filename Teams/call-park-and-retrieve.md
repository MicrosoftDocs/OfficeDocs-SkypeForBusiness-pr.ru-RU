---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
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
description: Узнайте о том, как использовать функцию парковки и извлечь, чтобы позвонить на удержание в службе Teams в облаке.
ms.openlocfilehash: 2420652fc908a943e798ac1acade53eca4c5b55f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905041"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="cd243-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd243-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="cd243-104">Метод парковки и извлечения звонков — это функция, с помощью которой пользователь может помещать Звонок на удержание в службе Teams в облаке.</span><span class="sxs-lookup"><span data-stu-id="cd243-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="cd243-105">При приостановке звонка служба генерирует уникальный код для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="cd243-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="cd243-106">Пользователь, который приприпаркован звонок или другой пользователь может затем использовать этот код и поддерживаемое приложение или устройство для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="cd243-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="cd243-107">Ниже приведены некоторые распространенные сценарии использования функции приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="cd243-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="cd243-108">Receptionist парки вызов для того, чтобы кто-то работал в фабрике.</span><span class="sxs-lookup"><span data-stu-id="cd243-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="cd243-109">Затем receptionist объявляет звонок и номер кода в системе общедоступной адресной системы.</span><span class="sxs-lookup"><span data-stu-id="cd243-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="cd243-110">Пользователь, для которого выполняется звонок, может затем выбрать телефон на телефоне в фабричном цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="cd243-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="cd243-111">Пользователь парки Звонок на мобильном устройстве из-за отсутствия питания на батарее устройства.</span><span class="sxs-lookup"><span data-stu-id="cd243-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="cd243-112">Пользователь может ввести этот код, чтобы получить звонок с телефонного рабочего стола Teams.</span><span class="sxs-lookup"><span data-stu-id="cd243-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="cd243-113">Представитель службы поддержки парки звонок абоненту и отправляет извещение в канале Teams для эксперта по получению звонка и помогать клиенту.</span><span class="sxs-lookup"><span data-stu-id="cd243-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="cd243-114">Эксперт вводит код в клиентские группы, чтобы получить звонок.</span><span class="sxs-lookup"><span data-stu-id="cd243-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd243-115">Эта функция доступна только в режиме развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="cd243-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="cd243-116">Для получения дополнительных сведений о режимах развертывания Teams ознакомьтесь со статьей общие сведения о [сосуществовании и взаимодействии в Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="cd243-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="cd243-117">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="cd243-117">License required</span></span>

<span data-ttu-id="cd243-118">Чтобы приостановить и получить звонки, пользователь должен быть вашим корпоративным голосом, а администратор должен предоставить пользователю политику парковки для приема звонков.</span><span class="sxs-lookup"><span data-stu-id="cd243-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="cd243-119">Дополнительные сведения о модели лицензирования можно найти в разделе [Лицензирование Office 365 для Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="cd243-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="cd243-120">Приостановка звонков и получение сведений о доступности компонентов</span><span class="sxs-lookup"><span data-stu-id="cd243-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="cd243-121">Метод парковки и извлечения в настоящее время поддерживается следующими клиентами и устройствами.</span><span class="sxs-lookup"><span data-stu-id="cd243-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="cd243-122">(Поддерживается только в режиме "только в Teams", с подключением и без поддержки PSTN.)</span><span class="sxs-lookup"><span data-stu-id="cd243-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="cd243-123">Возможность</span><span class="sxs-lookup"><span data-stu-id="cd243-123">Capability</span></span> | <span data-ttu-id="cd243-124">Классическое приложение Teams</span><span class="sxs-lookup"><span data-stu-id="cd243-124">Teams Desktop</span></span> | <span data-ttu-id="cd243-125">Приложение Teams для Mac</span><span class="sxs-lookup"><span data-stu-id="cd243-125">Teams Mac App</span></span> | <span data-ttu-id="cd243-126">Teams Web App (EDGE)</span><span class="sxs-lookup"><span data-stu-id="cd243-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="cd243-127">Приложение Teams Mobile для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="cd243-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="cd243-128">IP-телефон для Teams</span><span class="sxs-lookup"><span data-stu-id="cd243-128">Teams IP phone</span></span> | <span data-ttu-id="cd243-129">IP-телефон Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cd243-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="cd243-130">Приостановка звонка</span><span class="sxs-lookup"><span data-stu-id="cd243-130">Park a call</span></span> | <span data-ttu-id="cd243-131">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-131">Yes</span></span> | <span data-ttu-id="cd243-132">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-132">Yes</span></span> | <span data-ttu-id="cd243-133">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-133">Yes</span></span> | <span data-ttu-id="cd243-134">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-134">Yes</span></span> | <span data-ttu-id="cd243-135">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="cd243-135">Coming soon</span></span>| <span data-ttu-id="cd243-136">Нет</span><span class="sxs-lookup"><span data-stu-id="cd243-136">No</span></span> |
| <span data-ttu-id="cd243-137">Получение приостановленного звонка</span><span class="sxs-lookup"><span data-stu-id="cd243-137">Retrieve a parked call</span></span> | <span data-ttu-id="cd243-138">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-138">Yes</span></span> | <span data-ttu-id="cd243-139">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-139">Yes</span></span> | <span data-ttu-id="cd243-140">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-140">Yes</span></span> | <span data-ttu-id="cd243-141">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-141">Yes</span></span> | <span data-ttu-id="cd243-142">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="cd243-142">Coming soon</span></span>| <span data-ttu-id="cd243-143">Нет</span><span class="sxs-lookup"><span data-stu-id="cd243-143">No</span></span> |
| <span data-ttu-id="cd243-144">Неизвлеченный ответный звонок</span><span class="sxs-lookup"><span data-stu-id="cd243-144">Unretrieved call ring back</span></span> | <span data-ttu-id="cd243-145">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-145">Yes</span></span> | <span data-ttu-id="cd243-146">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-146">Yes</span></span> | <span data-ttu-id="cd243-147">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-147">Yes</span></span> | <span data-ttu-id="cd243-148">Да</span><span class="sxs-lookup"><span data-stu-id="cd243-148">Yes</span></span> | <span data-ttu-id="cd243-149">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="cd243-149">Coming soon</span></span>| <span data-ttu-id="cd243-150">Нет</span><span class="sxs-lookup"><span data-stu-id="cd243-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="cd243-151">Настройка парковки и извлечение звонков</span><span class="sxs-lookup"><span data-stu-id="cd243-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="cd243-152">Вы должны быть администратором для настройки парковки и получения звонков, и эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd243-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="cd243-153">Вы можете включить ее для пользователей и создавать группы пользователей с помощью политики парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="cd243-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="cd243-154">Если вы применяете одну и ту же политику к набору пользователей, они могут приостановить и получить звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="cd243-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="cd243-155">Чтобы настроить приостановку звонков для пользователей и создать группы пользователей для парковки на приостановке, следуйте инструкциям, приведенным в разделе [Назначение политики приостановки вызова](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="cd243-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="cd243-156">Сведения о том, как использовать функцию парковки и получения звонков, можно найти [в разделе Присоединение к звонку в Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="cd243-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="cd243-157">Включение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="cd243-157">Enable a call park policy</span></span>

<span data-ttu-id="cd243-158">Чтобы включить политику парковки звонков, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cd243-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="cd243-159">Перейдите в раздел**политики**в >  **центре администрирования Microsoft Teams**для**голосовой** > связи.</span><span class="sxs-lookup"><span data-stu-id="cd243-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="cd243-160">Выберите пункт **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="cd243-160">Select **New policy**.</span></span>
3. <span data-ttu-id="cd243-161">Присвойте политике имя, а затем установите переключатель **Разрешить приостановку звонка** **на включен**.</span><span class="sxs-lookup"><span data-stu-id="cd243-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="cd243-162">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cd243-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="cd243-163">Назначение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="cd243-163">Assign a call park policy</span></span>

<span data-ttu-id="cd243-164">Выполните указанные ниже действия, чтобы назначить политику приостановки вызова для одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd243-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="cd243-165">Перейдите в раздел**политики**в >  **центре администрирования Microsoft Teams**для**голосовой** > связи.</span><span class="sxs-lookup"><span data-stu-id="cd243-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="cd243-166">Выберите политику, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="cd243-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cd243-167">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="cd243-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="cd243-168">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cd243-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cd243-169">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="cd243-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cd243-170">Закончив добавление пользователей, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cd243-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="cd243-171">Настройка парковки звонков и получение с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd243-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="cd243-172">Используйте командлет PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) , чтобы создать политику парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="cd243-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="cd243-173">С помощью командлета PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) можно предоставить политику парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="cd243-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="cd243-174">Вы можете изменить параметр по умолчанию, используя [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) , как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="cd243-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="cd243-175">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="cd243-175">Troubleshooting</span></span>

<span data-ttu-id="cd243-176">Если пользователи не видят кнопку "приостановить" или "получить":</span><span class="sxs-lookup"><span data-stu-id="cd243-176">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="cd243-177">Убедитесь в том, что у пользователя включена политика парковки на звонки.</span><span class="sxs-lookup"><span data-stu-id="cd243-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="cd243-178">Если пользователь попытается получить вызов и не прошел его, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="cd243-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="cd243-179">Убедитесь в том, что пользователь использует клиент Teams или устройство или телефон с поддержкой Teams.</span><span class="sxs-lookup"><span data-stu-id="cd243-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="cd243-180">Группировка — пользователь является членом группы "парковки звонков", на основе которой назначена та же политика приостановки вызова для групп.</span><span class="sxs-lookup"><span data-stu-id="cd243-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="cd243-181">Режим острова: метод парковки и извлечение недоступен в режиме островов Teams.</span><span class="sxs-lookup"><span data-stu-id="cd243-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="cd243-182">Звонок уже получен или прерван.</span><span class="sxs-lookup"><span data-stu-id="cd243-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="cd243-183">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="cd243-183">More information</span></span>

<span data-ttu-id="cd243-184">[Приостановить Звонок в Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="cd243-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
