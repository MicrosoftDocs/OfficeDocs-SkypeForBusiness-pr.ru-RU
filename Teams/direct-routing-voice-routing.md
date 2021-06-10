---
title: Настройка голосовой маршрутии для прямой маршрутии
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить голосовую маршрутику с Телефон (Майкрософт) System Direct Routing.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383983"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="857fe-103">Настройка голосовой маршрутии для прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="857fe-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="857fe-104">В этой статье описано, как настроить голосовую маршрутику для телефонная система прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="857fe-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="857fe-105">Это шаг 3 из следующих действий по настройке прямой маршрутии:</span><span class="sxs-lookup"><span data-stu-id="857fe-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="857fe-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="857fe-106">Step 1.</span></span> [<span data-ttu-id="857fe-107">Подключение SBC с Телефон (Майкрософт) и проверьте подключение</span><span class="sxs-lookup"><span data-stu-id="857fe-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="857fe-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="857fe-108">Step 2.</span></span> [<span data-ttu-id="857fe-109">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="857fe-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="857fe-110">**Шаг 3. Настройка перенастройки голосовой** связи (эта статья)</span><span class="sxs-lookup"><span data-stu-id="857fe-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="857fe-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="857fe-111">Step 4.</span></span> [<span data-ttu-id="857fe-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="857fe-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="857fe-113">Сведения о всех действиях, необходимых для настройки прямой маршрутистики, см. в этой [ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="857fe-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="857fe-114">Обзор маршрутии голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="857fe-114">Voice routing overview</span></span>

<span data-ttu-id="857fe-115">Телефон (Майкрософт) В системе есть механизм маршрутации, который позволяет перенаправить звонок на определенный контроллер границы сеанса на основе:</span><span class="sxs-lookup"><span data-stu-id="857fe-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="857fe-116">The called number pattern</span><span class="sxs-lookup"><span data-stu-id="857fe-116">The called number pattern</span></span> 
- <span data-ttu-id="857fe-117">Шаблон вызываемого номера, а также конкретный пользователь, который совершает звонок</span><span class="sxs-lookup"><span data-stu-id="857fe-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="857fe-118">SBCs можно сделать активными и резервными.</span><span class="sxs-lookup"><span data-stu-id="857fe-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="857fe-119">Если SBC, настроенный как активный, не доступен для определенного маршрута звонка, звонок будет перенанаться на резервную копию SBC.</span><span class="sxs-lookup"><span data-stu-id="857fe-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="857fe-120">Маршрутия голосовой почты состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="857fe-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="857fe-121">**Политика маршрутинга голосовой** почты — контейнер для использования услуг STN, который можно на назначении пользователю или нескольким пользователям.</span><span class="sxs-lookup"><span data-stu-id="857fe-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="857fe-122">**Использование услуг STN** — контейнер для голосовых маршрутов и использования услуг STN, который можно использовать в различных политиках маршрутинга голосовой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="857fe-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="857fe-123">**Голосовые маршруты** — шаблон номера и набор сетевых шлюзов ЗВОНКОВ, которые используются для звонков, где номер звонка соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="857fe-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="857fe-124">Сетевой шлюз **STN** — указатель на SBC, который также сохраняет конфигурацию, применяемую при размещении звонка через SBC, например перенапорядующий P-Наядерный-identity (PAI) или Preferred Codecs; могут быть добавлены в голосовые маршруты.</span><span class="sxs-lookup"><span data-stu-id="857fe-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="857fe-125">Аспекты политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="857fe-125">Voice routing policy considerations</span></span>

<span data-ttu-id="857fe-126">Если у пользователя есть лицензия на план звонков, исходяющие звонки этого пользователя автоматически маршрутируются через инфраструктуру ЗВОНКОВ плана ЗВОНКОВ Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="857fe-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="857fe-127">Если вы настроили и назначили политику переназначения голосовой почты пользователю плана звонков, то исходяющие звонки этого пользователя проверяются на то, соответствует ли номер шаблону номера, определенному в политике маршрутинга голосовой почты в Интернете.</span><span class="sxs-lookup"><span data-stu-id="857fe-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="857fe-128">Если есть совпадение, звонок будет перенаправиться через линию прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="857fe-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="857fe-129">Если совпадения не совпадают, звонок передается через инфраструктуру ЗВОНКОВ по плану ЗВОНКОВ.</span><span class="sxs-lookup"><span data-stu-id="857fe-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="857fe-130">Если вы настроите и примените глобальную (по умолчанию в организации) политику маршрутизации голосовой связи в Интернете, все пользователи с голосовой связью в организации наследуют эту политику, что может привести к непреднамеренной маршрутизации звонков от пользователей плана звонков к линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="857fe-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="857fe-131">Если вы не хотите, чтобы все пользователи использовали глобальную политику маршрутинга голосовой почты в Интернете, настройте настраиваемую политику маршрутинга голосовой почты в Интернете и назначьте ее отдельным пользователям с поддержкой голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="857fe-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="857fe-132">Пример 1. Маршрутная маршрутия голосовой связи с использованием одного ПСN</span><span class="sxs-lookup"><span data-stu-id="857fe-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="857fe-133">На следующей схеме показаны два примера политик маршрутизов голосовой маршрутики в потоке зовов.</span><span class="sxs-lookup"><span data-stu-id="857fe-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="857fe-134">**Звонок Flow 1 (слева):** Если пользователь звонит на +1 425 XXX XX или +1 206 XXX XX XX, звонок перенанося в SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="857fe-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="857fe-135">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, звонок будет отброшен.</span><span class="sxs-lookup"><span data-stu-id="857fe-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="857fe-136">**Звонок Flow 2 (справа):** Если пользователь звонит на +1 425 XXX XX или +1 206 XXX XX XX, звонок сначала перенанося в SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="857fe-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="857fe-137">Если ни один из SBC не доступен, будет опробовен маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="857fe-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="857fe-138">Если ни один из SBCs не доступен, звонок будет сброшен.</span><span class="sxs-lookup"><span data-stu-id="857fe-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политик маршрутии голосовой маршрутии](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="857fe-140">В обоих примерах при присвоении голосовой маршруту приоритетов SBCs в маршрутах попытались в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="857fe-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="857fe-141">Если у пользователя нет лицензии на план звонков Майкрософт, звонки на любые номера, кроме номеров, которые соответствуют шаблонам +1 425 XXX XX XX или +1 206 XXX XX XX в конфигурации примера, будут сброшены.</span><span class="sxs-lookup"><span data-stu-id="857fe-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="857fe-142">Если у пользователя есть лицензия на план звонков, звонок автоматически передается в соответствии с политиками плана звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="857fe-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="857fe-143">План звонков (Майкрософт) применяется автоматически как последний маршрут для всех пользователей с лицензией на план звонков Майкрософт и не требует дополнительной настройки маршрутизов звонков.</span><span class="sxs-lookup"><span data-stu-id="857fe-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="857fe-144">В приведенной ниже схеме для отправки звонков на другие номера в США и Канаде (для звонков по шаблону номера +1 XXX XXX XX XX) добавляется голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="857fe-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутинга голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="857fe-146">Для всех остальных звонков, если у пользователя есть обе лицензии (Телефон (Майкрософт) Система и План звонков Майкрософт), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="857fe-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="857fe-147">Если ничего не соответствует шаблонам номеров в сетевых голосовых маршрутах, созданных администратором, звонок передается по плану звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="857fe-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="857fe-148">Если у пользователя только Телефон (Майкрософт) система, звонок будет отброшен, так как не доступны правила.</span><span class="sxs-lookup"><span data-stu-id="857fe-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="857fe-149">Значение priority для маршрута "Other +1" в данном случае не имеет значения, так как существует только один маршрут, который соответствует шаблону +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="857fe-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="857fe-150">Если пользователь звонит на +1 324 567 89 89 и sbc5.contoso.biz и sbc6.contoso.biz недоступны, звонок будет отброшен.</span><span class="sxs-lookup"><span data-stu-id="857fe-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="857fe-151">В следующей таблице подводятся итоги конфигурации с использованием трех голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="857fe-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="857fe-152">В этом примере все три маршрута являются частью одного и того же использования ДНР (США и Канада).</span><span class="sxs-lookup"><span data-stu-id="857fe-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="857fe-153">Все маршруты связаны с использованием ОКП "США и Канада", а использование ПСП — с политикой голосовой маршрутистики "Только в США".</span><span class="sxs-lookup"><span data-stu-id="857fe-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="857fe-154">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="857fe-154">**PSTN usage**</span></span>|<span data-ttu-id="857fe-155">**Голосовой маршрут**</span><span class="sxs-lookup"><span data-stu-id="857fe-155">**Voice route**</span></span>|<span data-ttu-id="857fe-156">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="857fe-156">**Number pattern**</span></span>|<span data-ttu-id="857fe-157">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="857fe-157">**Priority**</span></span>|<span data-ttu-id="857fe-158">**Sbc**</span><span class="sxs-lookup"><span data-stu-id="857fe-158">**SBC**</span></span>|<span data-ttu-id="857fe-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="857fe-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="857fe-160">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-160">US and Canada</span></span>|<span data-ttu-id="857fe-161">"Редмонд 1"</span><span class="sxs-lookup"><span data-stu-id="857fe-161">"Redmond 1"</span></span>|<span data-ttu-id="857fe-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="857fe-163">1</span><span class="sxs-lookup"><span data-stu-id="857fe-163">1</span></span>|<span data-ttu-id="857fe-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="857fe-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="857fe-166">Активный маршрут для номеров + 1 425 XXX XX XX или +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="857fe-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="857fe-167">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-167">US and Canada</span></span>|<span data-ttu-id="857fe-168">"Редмонд 2"</span><span class="sxs-lookup"><span data-stu-id="857fe-168">"Redmond 2"</span></span>|<span data-ttu-id="857fe-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="857fe-170">2</span><span class="sxs-lookup"><span data-stu-id="857fe-170">2</span></span>|<span data-ttu-id="857fe-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="857fe-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="857fe-173">Резервное копирование маршрута для номеров +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="857fe-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="857fe-174">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-174">US and Canada</span></span>|<span data-ttu-id="857fe-175">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="857fe-175">"Other +1"</span></span>|<span data-ttu-id="857fe-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="857fe-177">3</span><span class="sxs-lookup"><span data-stu-id="857fe-177">3</span></span>|<span data-ttu-id="857fe-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="857fe-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="857fe-180">Маршрут по номерам +1 XXX XXX XX XX (за исключением +1 425 XXX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="857fe-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="857fe-181">Пример 1. Шаги настройки</span><span class="sxs-lookup"><span data-stu-id="857fe-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="857fe-182">В следующем примере показано, как:</span><span class="sxs-lookup"><span data-stu-id="857fe-182">The following example shows how to:</span></span>

1. <span data-ttu-id="857fe-183">Создание единого использования ДНР.</span><span class="sxs-lookup"><span data-stu-id="857fe-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="857fe-184">Настройте три голосовых маршрута.</span><span class="sxs-lookup"><span data-stu-id="857fe-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="857fe-185">Создайте политику маршрутинга голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="857fe-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="857fe-186">Назначьте политику пользователю с именем Низкий уровень.</span><span class="sxs-lookup"><span data-stu-id="857fe-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="857fe-187">Для выполнения этих [действий Microsoft Teams центр администрирования](#admincenterexample1) или [PowerShell.](#powershellexample1)</span><span class="sxs-lookup"><span data-stu-id="857fe-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="857fe-188">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="857fe-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="857fe-189">Шаг 1. Создание ОКП "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="857fe-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="857fe-190">В левой области навигации Центра администрирования Microsoft Teams перейдите в voice  >  **Direct Routing**, а затем в правом верхнем углу выберите Управление записями использования **STN**.</span><span class="sxs-lookup"><span data-stu-id="857fe-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="857fe-191">Нажмите **кнопку Добавить**, **введите США и Канада** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="857fe-192">Шаг 2. Создание трех голосовых маршрутов (Redmond 1, Redmond 2 и Other +1)</span><span class="sxs-lookup"><span data-stu-id="857fe-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="857fe-193">Ниже описано, как создать голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="857fe-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="857fe-194">С помощью этих действий можно создать три голосовые маршруты с именами Redmond 1, Redmond 2 и Other +1 в данном примере с помощью параметров, описанных в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="857fe-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="857fe-195">В левой области навигации центра администрирования Microsoft Teams перейдите в voice  >  **Direct Routing**, а затем выберите **вкладку Голосовые маршруты.**</span><span class="sxs-lookup"><span data-stu-id="857fe-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="857fe-196">Нажмите **кнопку** Добавить и введите имя и описание голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="857fe-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="857fe-197">Закажите приоритет и шаблон набора номера.</span><span class="sxs-lookup"><span data-stu-id="857fe-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="857fe-198">Чтобы зарегистрировать SBC с помощью голосового маршрута, в области Зарегистрированные **SBCs (необязательно)** щелкните Добавить SBCs , выберите **SBCs,** которые вы хотите зарегистрировать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="857fe-199">Чтобы добавить записи использования ННР, в области Записи использования ННР **(необязательно)** щелкните Добавить использование **ННР**, выберите записи ННП, которые вы хотите добавить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="857fe-200">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="857fe-201">Шаг 3. Создание политики голосовой маршрутизовки с именем "Только для США" и добавление в нее использования STN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="857fe-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="857fe-202">В левой области навигации Центра администрирования Microsoft Teams перейдите к политике маршрутации голосовой голосовой почты  >  и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="857fe-203">Введите **в** качестве имени только US и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="857fe-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="857fe-204">В **области Записи использования** ННР щелкните Добавить использование **ОКП**, выберите запись использования ННП "США и Канада" и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="857fe-205">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-205">Click **Save**.</span></span>

<span data-ttu-id="857fe-206">Дополнительные узнать см. в [управлении политиками маршрутии голосовой маршрутии.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="857fe-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="857fe-207">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем Низкий уровень</span><span class="sxs-lookup"><span data-stu-id="857fe-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="857fe-208">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="857fe-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="857fe-209">Щелкните **Политики**, а затем рядом с **кнопкой Назначенные политики** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="857fe-210">В **области Политика маршрутинга голосовой** почты выберите политику "Только для США" и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="857fe-211">Дополнительные узнать см. в [управлении политиками маршрутии голосовой маршрутии.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="857fe-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="857fe-212">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="857fe-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="857fe-213">Шаг 1. Создание ННП "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="857fe-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="857fe-214">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="857fe-215">Убедитесь, что использование создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="857fe-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="857fe-216">Возвращает список усеченных имен.</span><span class="sxs-lookup"><span data-stu-id="857fe-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="857fe-217">В следующем примере показан результат запуска команды PowerShell для отображения полных имен `(Get-CSOnlinePSTNUsage).usage` (без усеченных):</span><span class="sxs-lookup"><span data-stu-id="857fe-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="857fe-218">Шаг 2. Создание трех голосовых маршрутов (Redmond 1, Redmond 2 и Other +1)</span><span class="sxs-lookup"><span data-stu-id="857fe-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="857fe-219">Чтобы создать маршрут Redmond 1, в сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="857fe-220">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="857fe-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="857fe-221">Чтобы создать маршрут Redmond 2, введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="857fe-222">Чтобы создать маршрут Другой +1, введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="857fe-223">Убедитесь, что регулярное выражение в атрибуте NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="857fe-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="857fe-224">Вы можете проверить это на этом веб-сайте: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="857fe-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="857fe-225">В некоторых случаях необходимо перена маршрутизовать все звонки на один и тот же SBC. use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="857fe-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="857fe-226">Перена маршрутизовы всех звонков на один SBC.</span><span class="sxs-lookup"><span data-stu-id="857fe-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="857fe-227">Убедитесь, что вы правильно настроили маршрут, за запуском команды `Get-CSOnlineVoiceRoute` PowerShell с помощью параметров, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="857fe-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="857fe-228">Возвращаемая</span><span class="sxs-lookup"><span data-stu-id="857fe-228">Which should return:</span></span>

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

<span data-ttu-id="857fe-229">В этом примере маршруту "Другие +1" автоматически назначен приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="857fe-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="857fe-230">Шаг 3. Создание политики голосовой маршрутизовки с именем "Только для США" и добавление в нее использования STN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="857fe-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="857fe-231">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="857fe-232">В этом примере показан результат:</span><span class="sxs-lookup"><span data-stu-id="857fe-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="857fe-233">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем Низкий уровень</span><span class="sxs-lookup"><span data-stu-id="857fe-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="857fe-234">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="857fe-235">Чтобы проверить назначение политики, введите эту команду:</span><span class="sxs-lookup"><span data-stu-id="857fe-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="857fe-236">Команда возвращает следующую команду:</span><span class="sxs-lookup"><span data-stu-id="857fe-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="857fe-237">Пример 2. Маршрутная маршрутия голосовой связи с несколькими использованием услуг ПСО</span><span class="sxs-lookup"><span data-stu-id="857fe-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="857fe-238">Политика маршрутинга голосовой связи, созданная в примере 1, позволяет звонить только на номера телефонов в США и Канаде, если пользователю не назначена лицензия на план звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="857fe-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="857fe-239">В этом примере можно создать политику маршрутинга голосовой маршрутии "Без ограничений".</span><span class="sxs-lookup"><span data-stu-id="857fe-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="857fe-240">Политика повторно будет использовать использование ПСС "США и Канада", созданное в примере 1, а также новое "международное" использование ОКП.</span><span class="sxs-lookup"><span data-stu-id="857fe-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="857fe-241">Эта политика перенананола все остальные звонки на sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="857fe-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="857fe-242">В показанных примерах политика "Только в США" назначается пользователю Low, а политика без ограничений — пользователю Ивану Иванову, чтобы маршрутия велись следующим образом:</span><span class="sxs-lookup"><span data-stu-id="857fe-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="857fe-243">Low — политика только для США.</span><span class="sxs-lookup"><span data-stu-id="857fe-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="857fe-244">Звонки разрешены только на номера в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="857fe-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="857fe-245">При вызове в диапазон номеров Редмонда необходимо использовать определенный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="857fe-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="857fe-246">Номера, не в том числе номера для США, не будут маршрутизовы, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="857fe-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="857fe-247">John John John — международная политика.</span><span class="sxs-lookup"><span data-stu-id="857fe-247">John Woods – International policy.</span></span>  <span data-ttu-id="857fe-248">Звонки разрешены на любой номер.</span><span class="sxs-lookup"><span data-stu-id="857fe-248">Calls are allowed to any number.</span></span> <span data-ttu-id="857fe-249">При вызове в диапазон номеров Редмонда необходимо использовать определенный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="857fe-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="857fe-250">Номера, не в том числе сша, будут маршрутиться с sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="857fe-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутинга голосовой почты, назначенная пользователю Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="857fe-252">Для всех остальных звонков, если у пользователя есть обе лицензии (Телефон (Майкрософт) Система и План звонков Майкрософт), автоматический маршрут используется.</span><span class="sxs-lookup"><span data-stu-id="857fe-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="857fe-253">Если ничего не соответствует шаблонам номеров в сетевых голосовых маршрутах, созданных администратором, звонок перенаправлен с помощью плана звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="857fe-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="857fe-254">Если у пользователя только Телефон (Майкрософт) система, звонок будет отброшен, так как не доступны правила.</span><span class="sxs-lookup"><span data-stu-id="857fe-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутинга голосовой почты, назначенная пользователю John John](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="857fe-256">В следующей таблице 2010 2010 2016 2016 2016 2016 2016 2016 2016 2016 2016 2016 2013 2</span><span class="sxs-lookup"><span data-stu-id="857fe-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="857fe-257">Использование ТСОП</span><span class="sxs-lookup"><span data-stu-id="857fe-257">PSTN usage</span></span> | <span data-ttu-id="857fe-258">Голосовой маршрут</span><span class="sxs-lookup"><span data-stu-id="857fe-258">Voice route</span></span> | <span data-ttu-id="857fe-259">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="857fe-259">Number pattern</span></span> | <span data-ttu-id="857fe-260">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="857fe-260">Priority</span></span> | <span data-ttu-id="857fe-261">Sbc</span><span class="sxs-lookup"><span data-stu-id="857fe-261">SBC</span></span> | <span data-ttu-id="857fe-262">Описание</span><span class="sxs-lookup"><span data-stu-id="857fe-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="857fe-263">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-263">US and Canada</span></span>|<span data-ttu-id="857fe-264">"Редмонд 1"</span><span class="sxs-lookup"><span data-stu-id="857fe-264">"Redmond 1"</span></span>|<span data-ttu-id="857fe-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="857fe-266">1</span><span class="sxs-lookup"><span data-stu-id="857fe-266">1</span></span>|<span data-ttu-id="857fe-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="857fe-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="857fe-269">Активный маршрут для номеров звонит +1 425 XXX XX XX или +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="857fe-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="857fe-270">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-270">US and Canada</span></span>|<span data-ttu-id="857fe-271">"Редмонд 2"</span><span class="sxs-lookup"><span data-stu-id="857fe-271">"Redmond 2"</span></span>|<span data-ttu-id="857fe-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="857fe-273">2</span><span class="sxs-lookup"><span data-stu-id="857fe-273">2</span></span>|<span data-ttu-id="857fe-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="857fe-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="857fe-276">Резервное копирование маршрута для номеров звонит +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="857fe-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="857fe-277">США и Канада</span><span class="sxs-lookup"><span data-stu-id="857fe-277">US and Canada</span></span>|<span data-ttu-id="857fe-278">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="857fe-278">"Other +1"</span></span>|<span data-ttu-id="857fe-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="857fe-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="857fe-280">3</span><span class="sxs-lookup"><span data-stu-id="857fe-280">3</span></span>|<span data-ttu-id="857fe-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="857fe-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="857fe-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="857fe-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="857fe-284">International</span><span class="sxs-lookup"><span data-stu-id="857fe-284">International</span></span>|<span data-ttu-id="857fe-285">International</span><span class="sxs-lookup"><span data-stu-id="857fe-285">International</span></span>|<span data-ttu-id="857fe-286">\d+</span><span class="sxs-lookup"><span data-stu-id="857fe-286">\d+</span></span>|<span data-ttu-id="857fe-287">4</span><span class="sxs-lookup"><span data-stu-id="857fe-287">4</span></span>|<span data-ttu-id="857fe-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="857fe-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="857fe-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="857fe-290">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="857fe-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="857fe-291">Очень важно порядок использования услуг ОКП в политиках маршрутиза голосовой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="857fe-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="857fe-292">Использование применяется по порядку, и если совпадение найдено в первом использовании, то другие использования никогда не вычисляются.</span><span class="sxs-lookup"><span data-stu-id="857fe-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="857fe-293">После использования ОКП "США" и "Канада" необходимо использовать "Международные" ДНР.</span><span class="sxs-lookup"><span data-stu-id="857fe-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="857fe-294">Чтобы изменить порядок использования ОКП, запустите `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="857fe-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="857fe-295">Например, чтобы изменить порядок с "США и Канада" первым, а второй — с "Международный", на обратный порядок:</span><span class="sxs-lookup"><span data-stu-id="857fe-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="857fe-296">Приоритет для голосовых маршрутов "Другие +1" и "Международные" назначен автоматически.</span><span class="sxs-lookup"><span data-stu-id="857fe-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="857fe-297">Они имеют более низкий приоритет, чем "Редмонд 1" и "Редмонд 2".</span><span class="sxs-lookup"><span data-stu-id="857fe-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="857fe-298">Пример 2. Шаги настройки</span><span class="sxs-lookup"><span data-stu-id="857fe-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="857fe-299">В следующем примере показано, как:</span><span class="sxs-lookup"><span data-stu-id="857fe-299">The following example shows how to:</span></span>

1. <span data-ttu-id="857fe-300">Создайте новое использование ОКП под названием "Международные".</span><span class="sxs-lookup"><span data-stu-id="857fe-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="857fe-301">Создайте новый голосовой маршрут под названием "Международные".</span><span class="sxs-lookup"><span data-stu-id="857fe-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="857fe-302">Создайте политику маршрутинга голосовой почты под названием "Нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="857fe-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="857fe-303">Назначьте политику пользователю John John John.</span><span class="sxs-lookup"><span data-stu-id="857fe-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="857fe-304">Для выполнения этих [действий Microsoft Teams центр администрирования](#admincenterexample2) или [PowerShell.](#powershellexample2)</span><span class="sxs-lookup"><span data-stu-id="857fe-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="857fe-305">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="857fe-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="857fe-306">Шаг 1. Создание международного использования ОКП</span><span class="sxs-lookup"><span data-stu-id="857fe-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="857fe-307">В левой области навигации Центра администрирования Microsoft Teams перейдите в voice  >  **Direct Routing**, а затем в правом верхнем углу выберите Управление записями использования **STN**.</span><span class="sxs-lookup"><span data-stu-id="857fe-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="857fe-308">Нажмите **кнопку Добавить,** **введите Международные** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="857fe-309">Шаг 2. Создание "международного" голосового маршрута</span><span class="sxs-lookup"><span data-stu-id="857fe-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="857fe-310">В левой области навигации центра администрирования Microsoft Teams перейдите в voice  >  **Direct Routing**, а затем выберите **вкладку Голосовые маршруты.**</span><span class="sxs-lookup"><span data-stu-id="857fe-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="857fe-311">Нажмите **кнопку** Добавить, введите в качестве имени название "Международные" и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="857fe-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="857fe-312">Установите для приоритета значение 4, а затем за установите для шаблона набора номера значение \d+.</span><span class="sxs-lookup"><span data-stu-id="857fe-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="857fe-313">В **области Зарегистрированные SBCs (необязательно)** щелкните Добавить **SBCs**, выберите sbc2.contoso.biz и sbc5.contoso.biz и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="857fe-314">В области Записи использования ННР **(необязательно)** щелкните Добавить использование **ННР**, выберите запись "Международные" записи использования ННР и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="857fe-315">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="857fe-316">Шаг 3. Создание политики голосовой маршрутизовки с именами "Без ограничений" и добавление в нее имен "США и Канада" и "Международные" службы STN</span><span class="sxs-lookup"><span data-stu-id="857fe-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="857fe-317">В этой политике перенаправки голосовой маршрутии повторно за счет использования ОКП "США и Канада" сохраняется специальная обработка звонков на номера "+1 425 XXX XX XX" и "+1 206 XXX XX XX" как локальные и локальные звонки.</span><span class="sxs-lookup"><span data-stu-id="857fe-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="857fe-318">В левой области навигации Центра администрирования Microsoft Teams перейдите к политике маршрутации голосовой голосовой почты  >  и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="857fe-319">Введите **в качестве** имени без ограничений и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="857fe-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="857fe-320">В **области Записи** использования ННР щелкните Добавить использование **ОКП**, выберите запись использования ННП "США и Канада", а затем выберите запись "Международные" записи использования ПСП.</span><span class="sxs-lookup"><span data-stu-id="857fe-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="857fe-321">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-321">Click **Apply**.</span></span>

    <span data-ttu-id="857fe-322">Обратите внимание на порядок использования услуг STN:</span><span class="sxs-lookup"><span data-stu-id="857fe-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="857fe-323">Если звонок на номер "+1 425 XXX XX XX" с использованием, настроенным в данном примере, звонок будет проходить по маршруту, заданной в примере использования "США и Канада", и будет применена специальная логика маршрутации.</span><span class="sxs-lookup"><span data-stu-id="857fe-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="857fe-324">Это значит, что звонок сначала sbc1.contoso.biz sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве запасных маршрутов.</span><span class="sxs-lookup"><span data-stu-id="857fe-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="857fe-325">Если "международные" звонки по ОКП находятся до "США и Канада", звонки на номер +1 425 XXX XX перенанося в sbc2.contoso.biz и sbc5.contoso.biz в рамках логики маршрутизки.</span><span class="sxs-lookup"><span data-stu-id="857fe-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="857fe-326">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-326">Click **Save**.</span></span>

<span data-ttu-id="857fe-327">Дополнительные узнать см. в [управлении политиками маршрутинга голосовой почты.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="857fe-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="857fe-328">Шаг 4. Назначение политики маршрутизов голосовой почты пользователю с именем Иван Иванов</span><span class="sxs-lookup"><span data-stu-id="857fe-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="857fe-329">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="857fe-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="857fe-330">Щелкните **Политики**, а затем рядом с **кнопкой Назначенные политики** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="857fe-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="857fe-331">В **области Политика маршрутинга голосовой** почты выберите политику "Без ограничений" и нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="857fe-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="857fe-332">В результате голосовая политика, применяемая к звонкам Джона Конюха, не имеет ограничений и будет следовать логике маршрутизазвонков, доступной в США, Канаде и международных звонках.</span><span class="sxs-lookup"><span data-stu-id="857fe-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="857fe-333">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="857fe-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="857fe-334">Шаг 1. Создание международного использования ОКП</span><span class="sxs-lookup"><span data-stu-id="857fe-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="857fe-335">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="857fe-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="857fe-336">Шаг 2. Создание нового голосового маршрута с именем "Международные"</span><span class="sxs-lookup"><span data-stu-id="857fe-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="857fe-337">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="857fe-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="857fe-338">Шаг 3. Создание политики маршрутизов голосовой почты с именем "Без ограничений"</span><span class="sxs-lookup"><span data-stu-id="857fe-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="857fe-339">В этой политике перенаправки повторно сохраняются специальные правила обработки звонков на номера "+1 425 XXX XX XX" и "+1 206 XXX XX XX XX" в качестве локальных или локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="857fe-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="857fe-340">Обратите внимание на порядок использования услуг STN:</span><span class="sxs-lookup"><span data-stu-id="857fe-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="857fe-341">Если звонок с номером "+1 425 XXX XX XX" с использованием, настроенным в следующем примере, звонок будет проходить по маршруту, заехав на номер "США и Канада", и будет применена специальная логика маршрутации.</span><span class="sxs-lookup"><span data-stu-id="857fe-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="857fe-342">Это значит, что звонок сначала sbc1.contoso.biz sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве запасных маршрутов.</span><span class="sxs-lookup"><span data-stu-id="857fe-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="857fe-343">Если "международные" звонки по ОКП находятся до "США и Канада", звонки на номер +1 425 XXX XX перенанося в sbc2.contoso.biz и sbc5.contoso.biz в рамках логики маршрутизки.</span><span class="sxs-lookup"><span data-stu-id="857fe-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="857fe-344">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="857fe-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="857fe-345">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="857fe-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="857fe-346">Шаг 4. Назначение политики маршрутизов голосовой почты пользователю с именем Джон Поузер</span><span class="sxs-lookup"><span data-stu-id="857fe-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="857fe-347">Затем проверьте задание с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="857fe-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="857fe-348">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="857fe-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="857fe-349">В результате голосовая политика, применяемая к звонкам Джона Конюха, не имеет ограничений и будет следовать логике маршрутизазвонков, доступной для звонков в США, Канаде и международных звонках.</span><span class="sxs-lookup"><span data-stu-id="857fe-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="857fe-350">См. также</span><span class="sxs-lookup"><span data-stu-id="857fe-350">See also</span></span>

[<span data-ttu-id="857fe-351">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="857fe-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="857fe-352">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="857fe-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
