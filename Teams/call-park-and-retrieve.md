---
title: Парковка и восстановление звонков в Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Используйте парковки вызовов и извлекать для совершения звонка на удержание в службе группами в облаке.
ms.openlocfilehash: 2433a8836a037b530fbd895f7a37567f24d63b50
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328311"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="17b43-103">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17b43-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="17b43-104">Парковка вызовов и получение — это функциональная возможность, которая позволяет пользователю удержание звонка в службу группами в облаке.</span><span class="sxs-lookup"><span data-stu-id="17b43-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="17b43-105">При приостановке звонка службу создает уникальный код для извлечения звонок.</span><span class="sxs-lookup"><span data-stu-id="17b43-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="17b43-106">Выберите пользователя, который приостанавливать звонок или другому пользователю можно использовать кода и поддерживаемые приложение или устройство для возврата звонка.</span><span class="sxs-lookup"><span data-stu-id="17b43-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="17b43-107">Ниже указаны некоторые общие сценарии для использования парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="17b43-108">Для кого-либо работа в фабрике секретарю parks звонка.</span><span class="sxs-lookup"><span data-stu-id="17b43-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="17b43-109">Секретари нажмите сигнал вызова и номер кода через общедоступный адрес системы.</span><span class="sxs-lookup"><span data-stu-id="17b43-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="17b43-110">Пользователь, для вызова можно трубку телефона группами в рабочей среде и введите код для возврата звонка.</span><span class="sxs-lookup"><span data-stu-id="17b43-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="17b43-111">Пользователь parks звонка на мобильном устройстве, так как батарей устройства, недостаточно питания.</span><span class="sxs-lookup"><span data-stu-id="17b43-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="17b43-112">Пользователь может ввести затем примеры кода для возврата звонка из группы стационарный телефон.</span><span class="sxs-lookup"><span data-stu-id="17b43-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="17b43-113">Пример парков поддержки клиента вызова и отправляет оповещения по каналу группами для expert возврата звонка и помощь в клиента.</span><span class="sxs-lookup"><span data-stu-id="17b43-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="17b43-114">Эксперт вводит код в клиентах группами для возврата звонка</span><span class="sxs-lookup"><span data-stu-id="17b43-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17b43-115">Эта функция доступна только в режиме только группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="17b43-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="17b43-116">Для получения дополнительных сведений о режимах развертывания групп видеть [понять группами Майкрософт и Скайп для бизнеса сосуществования и взаимодействия](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="17b43-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="17b43-117">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="17b43-117">License required</span></span>

<span data-ttu-id="17b43-118">Чтобы приостановить и извлечение вызовов, пользователь должен быть пользователем корпоративной голосовой связи и администратор должен предоставить пользователю политику парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="17b43-119">Дополнительные сведения о модели лицензирования в разделе [Лицензирование Office 365 для групп Майкрософт](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="17b43-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="17b43-120">Парковка вызовов и получить доступность функций</span><span class="sxs-lookup"><span data-stu-id="17b43-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="17b43-121">Парковка вызовов и извлекать в настоящее время поддерживается следующие клиенты и устройства.</span><span class="sxs-lookup"><span data-stu-id="17b43-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="17b43-122">(Поддерживается только группы режиме или без подключения к ТСОП.)</span><span class="sxs-lookup"><span data-stu-id="17b43-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="17b43-123">Возможность</span><span class="sxs-lookup"><span data-stu-id="17b43-123">Capability</span></span> | <span data-ttu-id="17b43-124">Рабочий стол групп</span><span class="sxs-lookup"><span data-stu-id="17b43-124">Teams Desktop</span></span> | <span data-ttu-id="17b43-125">Приложение Mac групп</span><span class="sxs-lookup"><span data-stu-id="17b43-125">Teams Mac App</span></span> | <span data-ttu-id="17b43-126">Команды Web App (пограничный сервер)</span><span class="sxs-lookup"><span data-stu-id="17b43-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="17b43-127">Группы мобильных операций ввода-вывода/Android приложения</span><span class="sxs-lookup"><span data-stu-id="17b43-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="17b43-128">Команды IP-телефона</span><span class="sxs-lookup"><span data-stu-id="17b43-128">Teams IP phone</span></span> | <span data-ttu-id="17b43-129">Скайп для бизнеса IP-телефона</span><span class="sxs-lookup"><span data-stu-id="17b43-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="17b43-130">Приостановка звонка</span><span class="sxs-lookup"><span data-stu-id="17b43-130">Park a call</span></span> | <span data-ttu-id="17b43-131">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-131">Yes</span></span> | <span data-ttu-id="17b43-132">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-132">Yes</span></span> | <span data-ttu-id="17b43-133">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-133">Yes</span></span> | <span data-ttu-id="17b43-134">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-134">Yes</span></span> | <span data-ttu-id="17b43-135">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="17b43-135">Coming soon</span></span>| <span data-ttu-id="17b43-136">Нет</span><span class="sxs-lookup"><span data-stu-id="17b43-136">No</span></span> |
| <span data-ttu-id="17b43-137">Восстановление приостановленного звонка</span><span class="sxs-lookup"><span data-stu-id="17b43-137">Retrieve a parked call</span></span> | <span data-ttu-id="17b43-138">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-138">Yes</span></span> | <span data-ttu-id="17b43-139">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-139">Yes</span></span> | <span data-ttu-id="17b43-140">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-140">Yes</span></span> | <span data-ttu-id="17b43-141">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-141">Yes</span></span> | <span data-ttu-id="17b43-142">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="17b43-142">Coming soon</span></span>| <span data-ttu-id="17b43-143">Нет</span><span class="sxs-lookup"><span data-stu-id="17b43-143">No</span></span> |
| <span data-ttu-id="17b43-144">Назад без извлеченных звонок</span><span class="sxs-lookup"><span data-stu-id="17b43-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="17b43-145">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-145">Yes</span></span> | <span data-ttu-id="17b43-146">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-146">Yes</span></span> | <span data-ttu-id="17b43-147">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-147">Yes</span></span> | <span data-ttu-id="17b43-148">Да</span><span class="sxs-lookup"><span data-stu-id="17b43-148">Yes</span></span> | <span data-ttu-id="17b43-149">Ожидается в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="17b43-149">Coming soon</span></span>| <span data-ttu-id="17b43-150">Нет</span><span class="sxs-lookup"><span data-stu-id="17b43-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="17b43-151">Настройка парковки вызовов и извлечения</span><span class="sxs-lookup"><span data-stu-id="17b43-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="17b43-152">Необходимо иметь права администратора для настройки парковки вызовов и получения, и эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17b43-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="17b43-153">Можно включить для пользователей и создание групп пользователей, с помощью политики парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="17b43-154">В случае применения та же политика для группы пользователей, они смогут парковку и извлечение вызовов друг с другом.</span><span class="sxs-lookup"><span data-stu-id="17b43-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="17b43-155">Для настройки парковки вызовов для пользователей и создание групп пользователей парковки вызовов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="17b43-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="17b43-156">Сведения о том, как использовать парковки вызовов и получить возможность видеть [парковки вызовов в группах](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="17b43-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="17b43-157">Настройка парковки вызовов и получить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="17b43-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="17b43-158">Командлет [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell для создания политики парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="17b43-159">Командлет [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell для предоставления политику парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="17b43-160">По умолчанию можно изменить с помощью [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="17b43-160">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="17b43-161">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="17b43-161">Troubleshooting</span></span>

<span data-ttu-id="17b43-162">Если пользователи не могут видеть парковки и получить кнопки:</span><span class="sxs-lookup"><span data-stu-id="17b43-162">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="17b43-163">Убедитесь, что пользователь имеет политикой парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="17b43-163">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="17b43-164">Если пользователь пытается получить вызов, а не выполняется, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="17b43-164">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="17b43-165">Убедитесь, что пользователь использует клиент групп или с поддержкой групп устройств/телефона</span><span class="sxs-lookup"><span data-stu-id="17b43-165">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="17b43-166">Группирование — — пользователь, должна быть членом группы парковки вызовов?</span><span class="sxs-lookup"><span data-stu-id="17b43-166">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="17b43-167">Остров режим – парковки вызовов и извлекать недоступны в режиме остров группами.</span><span class="sxs-lookup"><span data-stu-id="17b43-167">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="17b43-168">Вызов уже извлечен или завершен.</span><span class="sxs-lookup"><span data-stu-id="17b43-168">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="17b43-169">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="17b43-169">More information</span></span>

<span data-ttu-id="17b43-170">[Парковка вызовов в группах](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="17b43-170">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>