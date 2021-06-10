---
title: Оператор Подключение
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Узнайте больше об операторе Подключение, например о требованиях и планировании развертывания.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694544"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="37104-103">Планирование операторов Подключение</span><span class="sxs-lookup"><span data-stu-id="37104-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="37104-104">Оператор Подключение в настоящее время доступен только в **режиме предварительной версии.**</span><span class="sxs-lookup"><span data-stu-id="37104-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="37104-105">Общедоступный предварительный просмотр позволяет протестировать предстоящие возможности и предоставить отзывы.</span><span class="sxs-lookup"><span data-stu-id="37104-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="37104-106">Функции, включенные в общедоступный предварительный просмотр, могут быть не завершены, могут быть внесены изменения и не поддерживаются в Office 365 для государственных организаций Cloud.</span><span class="sxs-lookup"><span data-stu-id="37104-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="37104-107">Оператор Подключение также обеспечивает подключение к телефонной сети общего перейти на Teams и телефонная система.</span><span class="sxs-lookup"><span data-stu-id="37104-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="37104-108">В этой статье описаны преимущества и требования, а также перечислены операторы, участвующие в программе Подключение операторов.</span><span class="sxs-lookup"><span data-stu-id="37104-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="37104-109">Если вы решили, Подключение — это правильное решение для вашей организации, прочитав эту статью, см. статью [Настройка](operator-connect-configure.md)Подключение.</span><span class="sxs-lookup"><span data-stu-id="37104-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="37104-110">Преимущества</span><span class="sxs-lookup"><span data-stu-id="37104-110">Benefits</span></span>

<span data-ttu-id="37104-111">Оператор Подключение, если ваш оператор является участником программы Подключение Майкрософт, он может управлять службой для перенаправки звонков по ЗВОНКОВ по ПСОП Teams.</span><span class="sxs-lookup"><span data-stu-id="37104-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="37104-112">Программа Подключение операторов предоставляет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="37104-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="37104-113">**Используйте существующие контракты или найдите новый оператор.**</span><span class="sxs-lookup"><span data-stu-id="37104-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="37104-114">Вы храните предпочитаемый оператор и контракты или выбираете новый из выбора участвующих операторов в соответствии с потребностями вашей компании.</span><span class="sxs-lookup"><span data-stu-id="37104-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="37104-115">**Инфраструктура с управлением оператором.**</span><span class="sxs-lookup"><span data-stu-id="37104-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="37104-116">Ваш оператор управляет службами звонков по ПСОП и пограничными контроллерами сеансов( SBCs), позволяя экономить на приобретении оборудования и управлении им.</span><span class="sxs-lookup"><span data-stu-id="37104-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="37104-117">**Более быстрое и простое развертывание.**</span><span class="sxs-lookup"><span data-stu-id="37104-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="37104-118">Вы можете быстро подключиться к оператору и назначить номера телефонов пользователям из Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="37104-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="37104-119">**Улучшенная поддержка и надежность.**</span><span class="sxs-lookup"><span data-stu-id="37104-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="37104-120">Операторы предоставляют техническую поддержку и соглашения об общем уровне обслуживания для улучшения службы поддержки, а прямой пиринг, поддерживаемый Azure, создает одно-к-одному сетевое подключение для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="37104-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="37104-121">Требования</span><span class="sxs-lookup"><span data-stu-id="37104-121">Requirements</span></span>

 <span data-ttu-id="37104-122">Оператор Подключение может быть правильным решением для вашей организации, если:</span><span class="sxs-lookup"><span data-stu-id="37104-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="37104-123">План звонков Майкрософт не доступен в вашем географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="37104-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="37104-124">Вашим предпочтительным оператором является участник программы Подключение Microsoft.</span><span class="sxs-lookup"><span data-stu-id="37104-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="37104-125">Вы хотите найти новый оператор для звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="37104-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="37104-126">Чтобы включить назначение номеров телефонов с помощью оператора Подключение, убедитесь, что ваши пользователи:</span><span class="sxs-lookup"><span data-stu-id="37104-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="37104-127">Teams Телефон лицензированы.</span><span class="sxs-lookup"><span data-stu-id="37104-127">Teams Phone licensed.</span></span> <span data-ttu-id="37104-128">Подробнее см. в [телефонная система и](what-is-phone-system-in-office-365.md) Назначение пользователям Teams [надстройки.](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="37104-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="37104-129">В режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="37104-129">In TeamsOnly mode.</span></span> <span data-ttu-id="37104-130">Подробнее см. в Microsoft Teams и Skype для бизнеса сосуществования и [совместной работы.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="37104-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="37104-131">Доступные операторы</span><span class="sxs-lookup"><span data-stu-id="37104-131">Available Operators</span></span>

<span data-ttu-id="37104-132">Следующие операторы являются участниками программы microsoft Operator Подключение:</span><span class="sxs-lookup"><span data-stu-id="37104-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="37104-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="37104-133">Operator</span></span> | <span data-ttu-id="37104-134">Возможность</span><span class="sxs-lookup"><span data-stu-id="37104-134">Capability</span></span> | <span data-ttu-id="37104-135">Зона покрытия</span><span class="sxs-lookup"><span data-stu-id="37104-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="37104-136">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-136">Calling</span></span> | <span data-ttu-id="37104-137">Бельгия, Дания, Финляндия, Франция, Германия, Ирландия, Италия, Люксембург, Нидерланды, Норвегия, Польша, Южная Африка, Испания, Швеция, Швейцария, Соединенное Королевство</span><span class="sxs-lookup"><span data-stu-id="37104-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="37104-138">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-138">Calling</span></span> | <span data-ttu-id="37104-139">Бельгия, Канада, Дания, Франция, Германия, Ирландия, Люксембург, Нидерланды, Испания, Швеция, Соединенное Королевство, США</span><span class="sxs-lookup"><span data-stu-id="37104-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="37104-140">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-140">Calling</span></span> | <span data-ttu-id="37104-141">Австрия, Бельгия, Бразилия, Канада, Чешская Республика, Дания, Финляндия, Франция, Германия, Ирландия, Италия, Люксембург, Мексика, Нидерланды, Норвегия, Польша, Португалия, Пуэрто-Рико, Румыния, Южная Африка, Испания, Швеция, Швейцария, Соединенное Королевство, США</span><span class="sxs-lookup"><span data-stu-id="37104-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="37104-142">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-142">Calling</span></span> | <span data-ttu-id="37104-143">Австрия, Бельгия, Канада, Дания, Франция, Германия, Ирландия, Италия, Нидерланды, Португалия, Испания, Швеция, Швейцария, Соединенное Королевство, США</span><span class="sxs-lookup"><span data-stu-id="37104-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="37104-144">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-144">Calling</span></span> | <span data-ttu-id="37104-145">Австрия, Бельгия, Чешская Республика, Дания, Финляндия, Франция, Французская Гвиана, Германия, Гваделупа, Ирландия, Италия, Люксембург, Мартек, Майотта, Нидерланды, Норвегия, Польша, Португалия, Реюнион, Сен-Мартен, Испания, Svalbard, Sweden, Switzerland, United Kingdom</span><span class="sxs-lookup"><span data-stu-id="37104-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="37104-146">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-146">Calling</span></span> | <span data-ttu-id="37104-147">Австралия, Австрия, Бельгия, Бразилия, Болгария, Канада, Чили, Колумбия, Хорватия, Кипр, Чешская республика, Дания, Финляндия, Франция, Германия, Греция, Гонконг, Ирландия, Италия, Япония, Литва, Люксембург, Малайзия, Мексика, Нидерланды, Новая Зеландия, Норвегия, Португалия, Пуэрто-Рико, Румыния, Сингапур, Словакия, Словения, Испания, Швеция, Швейцария, Соединенное Королевство, США</span><span class="sxs-lookup"><span data-stu-id="37104-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="37104-148">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-148">Calling</span></span> | <span data-ttu-id="37104-149">Канада</span><span class="sxs-lookup"><span data-stu-id="37104-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="37104-150">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-150">Calling</span></span> | <span data-ttu-id="37104-151">Австралия, Австрия, Бельгия, Канада, Чешская Республика, Дания, Франция, Германия, Гонконг, Венгрия, Ирландия, Италия, Малайзия, Мексика, Нидерланды, Новая Зеландия, Польша, Португалия, Румыния, Сингапур, Южная Корея, Испания, Швеция, Швейцария, Таиланд, Соединенное Королевство, США</span><span class="sxs-lookup"><span data-stu-id="37104-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="37104-152">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-152">Calling</span></span> | <span data-ttu-id="37104-153">Германия</span><span class="sxs-lookup"><span data-stu-id="37104-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="37104-154">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-154">Calling</span></span> | <span data-ttu-id="37104-155">Дания, Финляндия, Норвегия, Швеция</span><span class="sxs-lookup"><span data-stu-id="37104-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="37104-156">Звонки</span><span class="sxs-lookup"><span data-stu-id="37104-156">Calling</span></span> | <span data-ttu-id="37104-157">Соединенные Штаты</span><span class="sxs-lookup"><span data-stu-id="37104-157">United States</span></span> |
