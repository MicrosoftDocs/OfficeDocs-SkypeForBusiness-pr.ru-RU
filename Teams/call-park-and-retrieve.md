---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 1fddc7acb6d670515fd5903731fab7cacd319f80
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255542"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="cf55f-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf55f-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="cf55f-104">Метод парковки и извлечения звонков — это функция, с помощью которой пользователь может помещать Звонок на удержание в службе Teams в облаке.</span><span class="sxs-lookup"><span data-stu-id="cf55f-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="cf55f-105">При приостановке звонка служба генерирует уникальный код для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="cf55f-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="cf55f-106">Пользователь, который приприпаркован звонок или другой пользователь может затем использовать этот код и поддерживаемое приложение или устройство для получения вызова.</span><span class="sxs-lookup"><span data-stu-id="cf55f-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="cf55f-107">Ниже приведены некоторые распространенные сценарии использования функции приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="cf55f-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="cf55f-108">Receptionist парки вызов для того, чтобы кто-то работал в фабрике.</span><span class="sxs-lookup"><span data-stu-id="cf55f-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="cf55f-109">Затем receptionist объявляет звонок и номер кода в системе общедоступной адресной системы.</span><span class="sxs-lookup"><span data-stu-id="cf55f-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="cf55f-110">Пользователь, для которого выполняется звонок, может затем выбрать телефон на телефоне в фабричном цехе и ввести код для получения звонка.</span><span class="sxs-lookup"><span data-stu-id="cf55f-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="cf55f-111">Пользователь парки Звонок на мобильном устройстве из-за отсутствия питания на батарее устройства.</span><span class="sxs-lookup"><span data-stu-id="cf55f-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="cf55f-112">Пользователь может ввести этот код, чтобы получить звонок с телефонного рабочего стола Teams.</span><span class="sxs-lookup"><span data-stu-id="cf55f-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="cf55f-113">Представитель службы поддержки парки звонок абоненту и отправляет извещение в канале Teams для эксперта по получению звонка и помогать клиенту.</span><span class="sxs-lookup"><span data-stu-id="cf55f-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="cf55f-114">Эксперт вводит код в клиентские группы, чтобы получить звонок.</span><span class="sxs-lookup"><span data-stu-id="cf55f-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf55f-115">Эта функция доступна только в режиме развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="cf55f-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="cf55f-116">Для получения дополнительных сведений о режимах развертывания Teams ознакомьтесь со статьей общие сведения о [сосуществовании и взаимодействии в Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="cf55f-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="cf55f-117">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="cf55f-117">License required</span></span>

<span data-ttu-id="cf55f-118">Чтобы приостановить и получить звонки, пользователь должен быть вашим корпоративным голосом, а администратор должен предоставить пользователю политику парковки для приема звонков.</span><span class="sxs-lookup"><span data-stu-id="cf55f-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="cf55f-119">Дополнительные сведения о модели лицензирования можно найти в [описании службы Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="cf55f-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="cf55f-120">Приостановка звонков и получение сведений о доступности компонентов</span><span class="sxs-lookup"><span data-stu-id="cf55f-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="cf55f-121">Метод парковки и извлечения в настоящее время поддерживается следующими клиентами и устройствами.</span><span class="sxs-lookup"><span data-stu-id="cf55f-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="cf55f-122">(Поддерживается только в режиме "только в Teams", с подключением и без поддержки PSTN.)</span><span class="sxs-lookup"><span data-stu-id="cf55f-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="cf55f-123">Возможность</span><span class="sxs-lookup"><span data-stu-id="cf55f-123">Capability</span></span> | <span data-ttu-id="cf55f-124">Классическое приложение Teams</span><span class="sxs-lookup"><span data-stu-id="cf55f-124">Teams Desktop</span></span> | <span data-ttu-id="cf55f-125">Приложение Teams для Mac</span><span class="sxs-lookup"><span data-stu-id="cf55f-125">Teams Mac App</span></span> | <span data-ttu-id="cf55f-126">Teams Web App (EDGE)</span><span class="sxs-lookup"><span data-stu-id="cf55f-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="cf55f-127">Приложение Teams Mobile для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="cf55f-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="cf55f-128">IP-телефон для Teams</span><span class="sxs-lookup"><span data-stu-id="cf55f-128">Teams IP phone</span></span> | <span data-ttu-id="cf55f-129">IP-телефон Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cf55f-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="cf55f-130">Приостановка звонка</span><span class="sxs-lookup"><span data-stu-id="cf55f-130">Park a call</span></span> | <span data-ttu-id="cf55f-131">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-131">Yes</span></span> | <span data-ttu-id="cf55f-132">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-132">Yes</span></span> | <span data-ttu-id="cf55f-133">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-133">Yes</span></span> | <span data-ttu-id="cf55f-134">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-134">Yes</span></span> | <span data-ttu-id="cf55f-135">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-135">Yes</span></span> | <span data-ttu-id="cf55f-136">Нет</span><span class="sxs-lookup"><span data-stu-id="cf55f-136">No</span></span> |
| <span data-ttu-id="cf55f-137">Получение приостановленного звонка</span><span class="sxs-lookup"><span data-stu-id="cf55f-137">Retrieve a parked call</span></span> | <span data-ttu-id="cf55f-138">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-138">Yes</span></span> | <span data-ttu-id="cf55f-139">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-139">Yes</span></span> | <span data-ttu-id="cf55f-140">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-140">Yes</span></span> | <span data-ttu-id="cf55f-141">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-141">Yes</span></span> | <span data-ttu-id="cf55f-142">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-142">Yes</span></span> | <span data-ttu-id="cf55f-143">Нет</span><span class="sxs-lookup"><span data-stu-id="cf55f-143">No</span></span> |
| <span data-ttu-id="cf55f-144">Неизвлеченный ответный звонок</span><span class="sxs-lookup"><span data-stu-id="cf55f-144">Unretrieved call ring back</span></span> | <span data-ttu-id="cf55f-145">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-145">Yes</span></span> | <span data-ttu-id="cf55f-146">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-146">Yes</span></span> | <span data-ttu-id="cf55f-147">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-147">Yes</span></span> | <span data-ttu-id="cf55f-148">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-148">Yes</span></span> | <span data-ttu-id="cf55f-149">Да</span><span class="sxs-lookup"><span data-stu-id="cf55f-149">Yes</span></span> | <span data-ttu-id="cf55f-150">Нет</span><span class="sxs-lookup"><span data-stu-id="cf55f-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="cf55f-151">Настройка парковки и извлечение звонков</span><span class="sxs-lookup"><span data-stu-id="cf55f-151">Configure call park and retrieve</span></span>

<span data-ttu-id="cf55f-152">Вы должны быть администратором, чтобы настроить приостановку и получение звонков, и эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf55f-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="cf55f-153">Вы можете включить ее для пользователей и создавать группы пользователей с помощью политики парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="cf55f-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="cf55f-154">Если вы применяете одну и ту же политику к набору пользователей, они могут приостановить и получить звонки между собой.</span><span class="sxs-lookup"><span data-stu-id="cf55f-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="cf55f-155">Чтобы настроить приостановку звонков для пользователей и создать группы пользователей для парковки на приостановке, следуйте инструкциям, приведенным в разделе [Назначение политики приостановки вызова](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="cf55f-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="cf55f-156">Сведения о том, как использовать функцию парковки и получения звонков, можно найти [в разделе Присоединение к звонку в Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="cf55f-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="cf55f-157">Включение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="cf55f-157">Enable a call park policy</span></span>

1. <span data-ttu-id="cf55f-158">В левой области навигации центра администрирования Microsoft Teams перейдите к **Voice**  >  **политикам парковки**для приема голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cf55f-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="cf55f-159">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-159">Select **Add**.</span></span>
3. <span data-ttu-id="cf55f-160">Присвойте политике имя, а затем установите переключатель **Разрешить приостановку звонка** **на включен**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="cf55f-161">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="cf55f-162">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf55f-162">Using PowerShell</span></span>

<span data-ttu-id="cf55f-163">Просмотреть раздел [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cf55f-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="cf55f-164">Изменение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="cf55f-164">Edit a call park policy</span></span>

1. <span data-ttu-id="cf55f-165">В левой области навигации центра администрирования Microsoft Teams перейдите к **Voice**  >  **политикам парковки**для приема голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cf55f-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="cf55f-166">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cf55f-167">Переключатель **Разрешить приостановку звонков** в **состояние "Выкл** **."**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="cf55f-168">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf55f-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="cf55f-169">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf55f-169">Using PowerShell</span></span>

<span data-ttu-id="cf55f-170">Смотрите раздел [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cf55f-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="cf55f-171">Например, чтобы изменить значение по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cf55f-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="cf55f-172">Назначение политики парковки звонков</span><span class="sxs-lookup"><span data-stu-id="cf55f-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="cf55f-173">Дополнительные сведения можно найти в разделе [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cf55f-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cf55f-174">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="cf55f-174">Troubleshooting</span></span>

<span data-ttu-id="cf55f-175">Если пользователи не видят кнопку "приостановить" или "получить":</span><span class="sxs-lookup"><span data-stu-id="cf55f-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="cf55f-176">Убедитесь в том, что у пользователя включена политика парковки на звонки.</span><span class="sxs-lookup"><span data-stu-id="cf55f-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="cf55f-177">Если пользователь попытается получить вызов и не прошел его, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="cf55f-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="cf55f-178">Убедитесь в том, что пользователь использует клиент Teams или устройство или телефон с поддержкой Teams.</span><span class="sxs-lookup"><span data-stu-id="cf55f-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="cf55f-179">Группировка — пользователь является членом группы "парковки звонков", на основе которой назначена та же политика приостановки вызова для групп.</span><span class="sxs-lookup"><span data-stu-id="cf55f-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="cf55f-180">Режим острова: метод парковки и извлечение недоступен в режиме островов Teams.</span><span class="sxs-lookup"><span data-stu-id="cf55f-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="cf55f-181">Звонок уже получен или прерван.</span><span class="sxs-lookup"><span data-stu-id="cf55f-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf55f-182">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cf55f-182">Related topics</span></span>

[<span data-ttu-id="cf55f-183">Приостановка звонка в Teams</span><span class="sxs-lookup"><span data-stu-id="cf55f-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="cf55f-184">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="cf55f-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
