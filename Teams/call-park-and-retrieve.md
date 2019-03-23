---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Используйте парковки вызовов и извлекать для совершения звонка на удержание в службе группами в облаке.
ms.openlocfilehash: 416458b1f7c134fca3294107bd82bbd0f2300abc
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747656"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="0d9d7-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d9d7-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="0d9d7-104">Парковка вызовов и получение — это функциональная возможность, которая позволяет пользователю удержание звонка в службу группами в облаке.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="0d9d7-105">При приостановке звонка службу создает уникальный код для извлечения звонок.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="0d9d7-106">Выберите пользователя, который приостанавливать звонок или другому пользователю можно использовать кода и поддерживаемые приложение или устройство для возврата звонка.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="0d9d7-107">Ниже указаны некоторые общие сценарии для использования парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="0d9d7-108">Для кого-либо работа в фабрике секретарю parks звонка.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="0d9d7-109">Секретари нажмите сигнал вызова и номер кода через общедоступный адрес системы.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="0d9d7-110">Пользователь, для вызова можно трубку телефона группами в рабочей среде и введите код для возврата звонка.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="0d9d7-111">Пользователь parks звонка на мобильном устройстве, так как батарей устройства, недостаточно питания.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="0d9d7-112">Пользователь может ввести затем примеры кода для возврата звонка из группы стационарный телефон.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="0d9d7-113">Пример парков поддержки клиента вызова и отправляет оповещения по каналу группами для expert возврата звонка и помощь в клиента.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="0d9d7-114">Эксперт вводит код в клиентах группами для возврата звонка</span><span class="sxs-lookup"><span data-stu-id="0d9d7-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d9d7-115">Эта функция доступна только в режиме только группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="0d9d7-116">Для получения дополнительных сведений о режимах развертывания групп видеть [понять группами Майкрософт и Скайп для бизнеса сосуществования и взаимодействия](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="0d9d7-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="0d9d7-117">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="0d9d7-117">License required</span></span>

<span data-ttu-id="0d9d7-118">Чтобы приостановить и извлечение вызовов, пользователь должен быть пользователем корпоративной голосовой связи и администратор должен предоставить пользователю политику парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="0d9d7-119">Дополнительные сведения о модели лицензирования в разделе [Лицензирование Office 365 для групп Майкрософт](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0d9d7-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="0d9d7-120">Парковка вызовов и получить доступность функций</span><span class="sxs-lookup"><span data-stu-id="0d9d7-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="0d9d7-121">Парковка вызовов и извлекать в настоящее время поддерживается следующие клиенты и устройства.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="0d9d7-122">(Поддерживается только группы режиме или без подключения к ТСОП.)</span><span class="sxs-lookup"><span data-stu-id="0d9d7-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="0d9d7-123">Возможность</span><span class="sxs-lookup"><span data-stu-id="0d9d7-123">Capability</span></span> | <span data-ttu-id="0d9d7-124">Рабочий стол групп</span><span class="sxs-lookup"><span data-stu-id="0d9d7-124">Teams Desktop</span></span> | <span data-ttu-id="0d9d7-125">Приложение Mac групп</span><span class="sxs-lookup"><span data-stu-id="0d9d7-125">Teams Mac App</span></span> | <span data-ttu-id="0d9d7-126">Команды Web App (пограничный сервер)</span><span class="sxs-lookup"><span data-stu-id="0d9d7-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="0d9d7-127">Группы мобильных операций ввода-вывода/Android приложения</span><span class="sxs-lookup"><span data-stu-id="0d9d7-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="0d9d7-128">Команды IP-телефона</span><span class="sxs-lookup"><span data-stu-id="0d9d7-128">Teams IP phone</span></span> | <span data-ttu-id="0d9d7-129">Скайп для бизнеса IP-телефона</span><span class="sxs-lookup"><span data-stu-id="0d9d7-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="0d9d7-130">Приостановка звонка</span><span class="sxs-lookup"><span data-stu-id="0d9d7-130">Park a call</span></span> | <span data-ttu-id="0d9d7-131">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-131">Yes</span></span> | <span data-ttu-id="0d9d7-132">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-132">Yes</span></span> | <span data-ttu-id="0d9d7-133">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-133">Yes</span></span> | <span data-ttu-id="0d9d7-134">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-134">Yes</span></span> | <span data-ttu-id="0d9d7-135">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="0d9d7-135">Coming soon</span></span>| <span data-ttu-id="0d9d7-136">Нет</span><span class="sxs-lookup"><span data-stu-id="0d9d7-136">No</span></span> |
| <span data-ttu-id="0d9d7-137">Восстановление приостановленного звонка</span><span class="sxs-lookup"><span data-stu-id="0d9d7-137">Retrieve a parked call</span></span> | <span data-ttu-id="0d9d7-138">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-138">Yes</span></span> | <span data-ttu-id="0d9d7-139">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-139">Yes</span></span> | <span data-ttu-id="0d9d7-140">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-140">Yes</span></span> | <span data-ttu-id="0d9d7-141">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-141">Yes</span></span> | <span data-ttu-id="0d9d7-142">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="0d9d7-142">Coming soon</span></span>| <span data-ttu-id="0d9d7-143">Нет</span><span class="sxs-lookup"><span data-stu-id="0d9d7-143">No</span></span> |
| <span data-ttu-id="0d9d7-144">Назад без извлеченных звонок</span><span class="sxs-lookup"><span data-stu-id="0d9d7-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="0d9d7-145">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-145">Yes</span></span> | <span data-ttu-id="0d9d7-146">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-146">Yes</span></span> | <span data-ttu-id="0d9d7-147">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-147">Yes</span></span> | <span data-ttu-id="0d9d7-148">Да</span><span class="sxs-lookup"><span data-stu-id="0d9d7-148">Yes</span></span> | <span data-ttu-id="0d9d7-149">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="0d9d7-149">Coming soon</span></span>| <span data-ttu-id="0d9d7-150">Нет</span><span class="sxs-lookup"><span data-stu-id="0d9d7-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="0d9d7-151">Настройка парковки вызовов и извлечения</span><span class="sxs-lookup"><span data-stu-id="0d9d7-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="0d9d7-152">Необходимо иметь права администратора для настройки парковки вызовов и получения, и эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="0d9d7-153">Можно включить для пользователей и создание групп пользователей, с помощью политики парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="0d9d7-154">В случае применения та же политика для группы пользователей, они смогут парковку и извлечение вызовов друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="0d9d7-155">Для настройки парковки вызовов для пользователей и создание групп пользователей парковки вызовов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="0d9d7-156">Сведения о том, как использовать парковки вызовов и получить возможность видеть [парковки вызовов в группах](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0d9d7-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="0d9d7-157">Назначение политики парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="0d9d7-157">Assign a call park policy</span></span>

<span data-ttu-id="0d9d7-158">Выполните следующие действия, чтобы назначить политику парковки вызовов для одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-158">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="0d9d7-159">Перейдите в **Центр администрирования группами Майкрософт** > **голосовой связи** > **политик парковки вызовов**.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0d9d7-160">Выберите политику, нажав кнопку слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-160">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="0d9d7-161">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-161">Select **Manage users**.</span></span>
4. <span data-ttu-id="0d9d7-162">В области **Управление пользователями** поиска для пользователя по отображаемому имени или по имени пользователя, выберите имя и выберите команду **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-162">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="0d9d7-163">Повторите этот шаг для каждого пользователя, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-163">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="0d9d7-164">Завершив добавление пользователей, выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-164">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="0d9d7-165">Настройка парковки вызовов и получить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d9d7-165">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="0d9d7-166">Командлет [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell для создания политики парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-166">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="0d9d7-167">Командлет [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell для предоставления политику парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-167">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="0d9d7-168">По умолчанию можно изменить с помощью [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0d9d7-168">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="0d9d7-169">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="0d9d7-169">Troubleshooting</span></span>

<span data-ttu-id="0d9d7-170">Если пользователи не могут видеть парковки и получить кнопки:</span><span class="sxs-lookup"><span data-stu-id="0d9d7-170">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="0d9d7-171">Убедитесь, что пользователь имеет политикой парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-171">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="0d9d7-172">Если пользователь пытается получить вызов, а не выполняется, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="0d9d7-172">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="0d9d7-173">Убедитесь, что пользователь использует клиент групп или с поддержкой групп устройств/телефона</span><span class="sxs-lookup"><span data-stu-id="0d9d7-173">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="0d9d7-174">Группирование — — пользователь, должна быть членом группы парковки вызовов?</span><span class="sxs-lookup"><span data-stu-id="0d9d7-174">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="0d9d7-175">Остров режим – парковки вызовов и извлекать недоступны в режиме остров группами.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-175">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="0d9d7-176">Вызов уже извлечен или завершен.</span><span class="sxs-lookup"><span data-stu-id="0d9d7-176">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="0d9d7-177">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0d9d7-177">More information</span></span>

<span data-ttu-id="0d9d7-178">[Парковка вызовов в группах](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0d9d7-178">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>