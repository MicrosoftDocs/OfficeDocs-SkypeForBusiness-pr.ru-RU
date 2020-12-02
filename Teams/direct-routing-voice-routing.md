---
title: Настройка маршрутизации голосовой связи для прямой маршрутизации
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
description: Научитесь настраивать маршрутизацию голосовой связи с помощью прямой маршрутизации Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530996"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="28779-103">Настройка маршрутизации голосовой связи для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="28779-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="28779-104">В этой статье описано, как настроить маршрутизацию голосовой связи для прямой маршрутизации телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="28779-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="28779-105">Это действие 3 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="28779-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="28779-106">Step 1.</span></span> [<span data-ttu-id="28779-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="28779-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="28779-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="28779-108">Step 2.</span></span> [<span data-ttu-id="28779-109">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="28779-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="28779-110">**Шаг 3. Настройка голосовой маршрутизации** (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="28779-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="28779-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="28779-111">Step 4.</span></span> [<span data-ttu-id="28779-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="28779-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="28779-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="28779-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="28779-114">Общие сведения о маршрутизации голосовой почты</span><span class="sxs-lookup"><span data-stu-id="28779-114">Voice routing overview</span></span>

<span data-ttu-id="28779-115">В телефонной системе Microsoft есть механизм маршрутизации, позволяющий отправлять звонки на определенный контроллер границ сеанса (SBC), основанный на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="28779-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="28779-116">Вызываемый шаблон номера</span><span class="sxs-lookup"><span data-stu-id="28779-116">The called number pattern</span></span> 
- <span data-ttu-id="28779-117">Вызываемый шаблон номера и конкретный пользователь, который совершает звонок;</span><span class="sxs-lookup"><span data-stu-id="28779-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="28779-118">SBCs можно назначить активными и архивировать.</span><span class="sxs-lookup"><span data-stu-id="28779-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="28779-119">Если объект SBC, настроенный как активный, недоступен для определенного маршрута вызова, этот звонок будет перенаправлен на одноэлементный объект SBC.</span><span class="sxs-lookup"><span data-stu-id="28779-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="28779-120">Маршрутизация голосовой связи состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="28779-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="28779-121">**Политика маршрутизации голосовой связи** — контейнер использования PSTN, который можно назначить пользователю или нескольким пользователям.</span><span class="sxs-lookup"><span data-stu-id="28779-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="28779-122">**Использование PSTN** — контейнер для голосовых маршрутов и использование PSTN, которые можно использовать в разных политиках голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="28779-123">**Голосовые маршруты** — шаблон номера и набор сетевых шлюзов, используемых для звонков, где номер звонка соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="28779-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="28779-124">**Сетевой шлюз PSTN** — указатель на объект SBC, который также хранит конфигурацию, которая применяется при размещении вызова через SBC, например переадресация (PAI) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты.</span><span class="sxs-lookup"><span data-stu-id="28779-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="28779-125">Рекомендации по политике голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="28779-125">Voice routing policy considerations</span></span>

<span data-ttu-id="28779-126">Если у пользователя есть лицензия на план звонков, исходящие звонки пользователя автоматически пересылаются по плану КОММУТИРУЕМого вызова Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28779-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="28779-127">Если вы настраиваете и назначаете политику сетевой маршрутизации для абонента абонентского плана, исходящие звонки пользователя проверяются, чтобы определить, соответствует ли номер шаблону, определенному в политике голосовой маршрутизации в сети.</span><span class="sxs-lookup"><span data-stu-id="28779-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="28779-128">Если совпадение найдено, Звонок направляется по прямой магистрали маршрута.</span><span class="sxs-lookup"><span data-stu-id="28779-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="28779-129">Если совпадение не найдено, Звонок направляется по инфраструктуре КОММУТИРУЕМого тарифного плана.</span><span class="sxs-lookup"><span data-stu-id="28779-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="28779-130">Если вы настроили и применяете глобальную политику сетевой маршрутизации по умолчанию, то все пользователи, поддерживающие голосовую почту в вашей организации, будут наследовать эту политику, что может привести к непреднамеренному перенаправлению звонков из плана КОММУТИРУЕМых пользователей на прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="28779-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="28779-131">Если вы не хотите, чтобы все пользователи использовали глобальную политику сетевой маршрутизации, настройте специальную политику голосовой связи и назначьте ее отдельным пользователям, поддерживающим голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="28779-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="28779-132">Пример 1: Маршрутизация голосовой связи с использованием одной PSTN</span><span class="sxs-lookup"><span data-stu-id="28779-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="28779-133">На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="28779-134">**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="28779-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="28779-135">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="28779-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="28779-136">**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="28779-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="28779-137">Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="28779-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="28779-138">Если ни одна из этих SBCs недоступна, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="28779-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="28779-140">В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="28779-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="28779-141">При настройке двух SBC-данных в одном маршруте сетевой трафик должен поддерживать маршрутизацию между обоими и носителями SBC, так как это может привести к отправке нового приглашения на передачу другому SBC в маршруте.</span><span class="sxs-lookup"><span data-stu-id="28779-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="28779-142">Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются.</span><span class="sxs-lookup"><span data-stu-id="28779-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="28779-143">Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28779-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="28779-144">План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="28779-145">В примере, показанном на приведенной ниже схеме, маршрут голосовой связи добавляется для отправки звонков на все остальные номера США и Канады (звонки, находящиеся под названием "шаблон номера" + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="28779-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="28779-147">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="28779-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="28779-148">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, этот звонок направляется через план звонков по Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28779-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="28779-149">Если у пользователя есть только телефонная система Microsoft, вызов отбрасывается из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="28779-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="28779-150">Значение приоритета для маршрута "Other + 1" не имеет значения в этом случае, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="28779-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="28779-151">Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="28779-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="28779-152">В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="28779-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="28779-153">В этом примере все три маршрута относятся к одной и той же использованию PSTN, а именно "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="28779-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="28779-154">Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только для США".</span><span class="sxs-lookup"><span data-stu-id="28779-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="28779-155">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="28779-155">**PSTN usage**</span></span>|<span data-ttu-id="28779-156">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="28779-156">**Voice route**</span></span>|<span data-ttu-id="28779-157">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="28779-157">**Number pattern**</span></span>|<span data-ttu-id="28779-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="28779-158">**Priority**</span></span>|<span data-ttu-id="28779-159">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="28779-159">**SBC**</span></span>|<span data-ttu-id="28779-160">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28779-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28779-161">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-161">US and Canada</span></span>|<span data-ttu-id="28779-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="28779-162">"Redmond 1"</span></span>|<span data-ttu-id="28779-163">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="28779-164">1</span><span class="sxs-lookup"><span data-stu-id="28779-164">1</span></span>|<span data-ttu-id="28779-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="28779-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="28779-167">Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="28779-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="28779-168">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-168">US and Canada</span></span>|<span data-ttu-id="28779-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="28779-169">"Redmond 2"</span></span>|<span data-ttu-id="28779-170">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="28779-171">2</span><span class="sxs-lookup"><span data-stu-id="28779-171">2</span></span>|<span data-ttu-id="28779-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="28779-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="28779-174">Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="28779-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="28779-175">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-175">US and Canada</span></span>|<span data-ttu-id="28779-176">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="28779-176">"Other +1"</span></span>|<span data-ttu-id="28779-177">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="28779-178">3</span><span class="sxs-lookup"><span data-stu-id="28779-178">3</span></span>|<span data-ttu-id="28779-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="28779-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="28779-181">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="28779-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="28779-182">Пример 1: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="28779-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="28779-183">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="28779-183">The following example shows how to:</span></span>

1. <span data-ttu-id="28779-184">Создание единственной неиспользуемой PSTN.</span><span class="sxs-lookup"><span data-stu-id="28779-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="28779-185">Настройте три голосовых маршрута.</span><span class="sxs-lookup"><span data-stu-id="28779-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="28779-186">Создание политики голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="28779-187">Назначьте политику пользователю с именем Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="28779-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="28779-188">Вы можете выполнить эти действия с помощью [центра администрирования Microsoft Teams](#admincenterexample1) или [PowerShell](#powershellexample1) .</span><span class="sxs-lookup"><span data-stu-id="28779-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="28779-189">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28779-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="28779-190">Действие 1: создание КОММУТИРУЕМого использования "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="28779-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="28779-191">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем в правом верхнем углу выберите **Управление записями использование PSTN**.</span><span class="sxs-lookup"><span data-stu-id="28779-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="28779-192">Нажмите кнопку **Добавить**, введите **US и Канада**, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="28779-193">Действие 2: создание трех голосовых маршрутов (Redmond 1, Redmond 2 и другие + 1)</span><span class="sxs-lookup"><span data-stu-id="28779-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="28779-194">Ниже описана процедура создания голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="28779-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="28779-195">Выполните указанные ниже действия, чтобы создать три Голосовые маршруты с названием Redmond 1, Redmond 2 и другие + 1 для этого примера с использованием параметров, описанных в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="28779-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="28779-196">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем откройте вкладку **Голосовые маршруты** .</span><span class="sxs-lookup"><span data-stu-id="28779-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="28779-197">Нажмите кнопку **Добавить**, а затем введите имя и описание для голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="28779-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="28779-198">Задайте приоритет и укажите шаблон номера для набора номера.</span><span class="sxs-lookup"><span data-stu-id="28779-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="28779-199">Чтобы зарегистрировать SBC с голосовым маршрутом, в разделе **Регистрация голоса (необязательно)** выберите команду **Добавить SBCS**, выберите однобайтовую запись, которую вы хотите зарегистрировать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="28779-200">Чтобы добавить записи об использовании PSTN, в разделе **записи использования PSTN (необязательно)** нажмите кнопку **Добавить использование PSTN**, выберите записи PSTN, которые вы хотите добавить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="28779-201">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="28779-202">Шаг 3: Создание политики голосовой маршрутизации с именем "только США" и добавление в политику использования PSTN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="28779-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="28779-203">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28779-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="28779-204">Введите **US только** в качестве имени и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="28779-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="28779-205">В разделе **записи использования PSTN** выберите **Добавить использование PSTN**, выберите запись использование PSTN, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="28779-206">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-206">Click **Save**.</span></span>

<span data-ttu-id="28779-207">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28779-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="28779-208">Шаг 4: назначение политики маршрутизации голосовой связи пользователю с именем Spencer Low</span><span class="sxs-lookup"><span data-stu-id="28779-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="28779-209">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="28779-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="28779-210">Нажмите **политики**, а затем рядом с пунктом **назначенные политики** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="28779-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="28779-211">В разделе **Политика маршрутизации голосовой связи** выберите политику "только США", а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="28779-212">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28779-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="28779-213">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="28779-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="28779-214">Действие 1: создание КОММУТИРУЕМого использования "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="28779-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="28779-215">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="28779-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="28779-216">Убедитесь в том, что использование было создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="28779-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="28779-217">Возвращающий список имен, которые могут быть усечены:</span><span class="sxs-lookup"><span data-stu-id="28779-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="28779-218">В следующем примере показан результат выполнения `(Get-CSOnlinePSTNUsage).usage` команды PowerShell для отображения полных имен (не усеченных):</span><span class="sxs-lookup"><span data-stu-id="28779-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="28779-219">Действие 2: создание трех голосовых маршрутов (Redmond 1, Redmond 2 и другие + 1)</span><span class="sxs-lookup"><span data-stu-id="28779-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="28779-220">Чтобы создать маршрут "Redmond 1" в сеансе PowerShell в Skype для бизнеса Online, введите:</span><span class="sxs-lookup"><span data-stu-id="28779-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="28779-221">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="28779-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="28779-222">Чтобы создать маршрут на 2 Redmond, введите:</span><span class="sxs-lookup"><span data-stu-id="28779-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="28779-223">Чтобы создать другой маршрут + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="28779-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="28779-224">Убедитесь, что регулярное выражение в атрибуте NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="28779-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="28779-225">Вы можете протестировать его с помощью этого веб-сайта: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="28779-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="28779-226">В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Используйте-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="28779-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="28779-227">Перенаправлять все вызовы на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="28779-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="28779-228">Убедитесь, что маршрут настроен правильно, выполнив `Get-CSOnlineVoiceRoute` команду PowerShell, используя указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="28779-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="28779-229">Что должно вернуть:</span><span class="sxs-lookup"><span data-stu-id="28779-229">Which should return:</span></span>
<pre>
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
</pre>

<span data-ttu-id="28779-230">В примере для маршрута "Other + 1" автоматически назначается приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="28779-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="28779-231">Шаг 3: Создание политики голосовой маршрутизации с именем "только США" и добавление в политику использования PSTN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="28779-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="28779-232">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="28779-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="28779-233">Результат показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="28779-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="28779-234">Шаг 4: назначение политики маршрутизации голосовой связи пользователю с именем Spencer Low</span><span class="sxs-lookup"><span data-stu-id="28779-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="28779-235">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="28779-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="28779-236">Чтобы проверить назначение политики, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28779-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="28779-237">Команда возвращает следующее:</span><span class="sxs-lookup"><span data-stu-id="28779-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="28779-238">Пример 2: Маршрутизация голосовой связи с несколькими использованием PSTN</span><span class="sxs-lookup"><span data-stu-id="28779-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="28779-239">Политика маршрутизации голосовой связи, созданная в примере 1, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).</span><span class="sxs-lookup"><span data-stu-id="28779-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="28779-240">В приведенном ниже примере вы можете создать политику голосовой маршрутизации "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="28779-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="28779-241">Политика повторно использует использование PSTN в США и Канаде, созданное в примере 1, а также новое использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="28779-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="28779-242">Эта политика маршрутизирует все другие вызовы на SBCs sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="28779-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="28779-243">Приведенные примеры применяют политику "только для США" для пользователей Spencer Low и политики "нет ограничений" для пользователя Джон лесу таким образом, чтобы маршрутизация была показана ниже.</span><span class="sxs-lookup"><span data-stu-id="28779-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="28779-244">Spencer низкий – только политика США.</span><span class="sxs-lookup"><span data-stu-id="28779-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="28779-245">Звонки разрешены только в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="28779-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="28779-246">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="28779-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="28779-247">Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="28779-248">Джон лесу – Международная политика.</span><span class="sxs-lookup"><span data-stu-id="28779-248">John Woods – International policy.</span></span>  <span data-ttu-id="28779-249">Звонки разрешены любому числу.</span><span class="sxs-lookup"><span data-stu-id="28779-249">Calls are allowed to any number.</span></span> <span data-ttu-id="28779-250">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="28779-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="28779-251">Номера, не относящиеся к США, будут маршрутизироваться с помощью sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="28779-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю Spencer низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="28779-253">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="28779-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="28779-254">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, вызов осуществляется с помощью плана звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28779-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="28779-255">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="28779-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="28779-257">В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="28779-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="28779-258">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="28779-258">**PSTN usage**</span></span>|<span data-ttu-id="28779-259">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="28779-259">**Voice route**</span></span>|<span data-ttu-id="28779-260">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="28779-260">**Number pattern**</span></span>|<span data-ttu-id="28779-261">**Priority**</span><span class="sxs-lookup"><span data-stu-id="28779-261">**Priority**</span></span>|<span data-ttu-id="28779-262">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="28779-262">**SBC**</span></span>|<span data-ttu-id="28779-263">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28779-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28779-264">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-264">US and Canada</span></span>|<span data-ttu-id="28779-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="28779-265">"Redmond 1"</span></span>|<span data-ttu-id="28779-266">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="28779-267">1</span><span class="sxs-lookup"><span data-stu-id="28779-267">1</span></span>|<span data-ttu-id="28779-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="28779-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="28779-270">Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="28779-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="28779-271">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-271">US and Canada</span></span>|<span data-ttu-id="28779-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="28779-272">"Redmond 2"</span></span>|<span data-ttu-id="28779-273">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="28779-274">2</span><span class="sxs-lookup"><span data-stu-id="28779-274">2</span></span>|<span data-ttu-id="28779-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="28779-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="28779-277">Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="28779-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="28779-278">США и Канада</span><span class="sxs-lookup"><span data-stu-id="28779-278">US and Canada</span></span>|<span data-ttu-id="28779-279">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="28779-279">"Other +1"</span></span>|<span data-ttu-id="28779-280">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="28779-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="28779-281">3</span><span class="sxs-lookup"><span data-stu-id="28779-281">3</span></span>|<span data-ttu-id="28779-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="28779-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="28779-284">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="28779-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="28779-285">International</span><span class="sxs-lookup"><span data-stu-id="28779-285">International</span></span>|<span data-ttu-id="28779-286">International</span><span class="sxs-lookup"><span data-stu-id="28779-286">International</span></span>|<span data-ttu-id="28779-287">\d +</span><span class="sxs-lookup"><span data-stu-id="28779-287">\d+</span></span>|<span data-ttu-id="28779-288">4</span><span class="sxs-lookup"><span data-stu-id="28779-288">4</span></span>|<span data-ttu-id="28779-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="28779-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="28779-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="28779-291">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="28779-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="28779-292">Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен.</span><span class="sxs-lookup"><span data-stu-id="28779-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="28779-293">Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="28779-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="28779-294">Использование КТСОП в международной сети по коммутируемой телефонной сети должно быть включено после использования КТСОП в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="28779-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="28779-295">Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="28779-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="28779-296">Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="28779-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="28779-297">Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="28779-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="28779-298">Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="28779-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="28779-299">Пример 2: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="28779-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="28779-300">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="28779-300">The following example shows how to:</span></span>

1. <span data-ttu-id="28779-301">Создайте новую использование PSTN, именуемое международным.</span><span class="sxs-lookup"><span data-stu-id="28779-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="28779-302">Создайте новый голосовой маршрут с именем International.</span><span class="sxs-lookup"><span data-stu-id="28779-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="28779-303">Создание политики голосовой маршрутизации с именем "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="28779-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="28779-304">Назначьте политику пользователю John лесу.</span><span class="sxs-lookup"><span data-stu-id="28779-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="28779-305">Вы можете выполнить эти действия с помощью [центра администрирования Microsoft Teams](#admincenterexample2) или [PowerShell](#powershellexample2) .</span><span class="sxs-lookup"><span data-stu-id="28779-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="28779-306">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28779-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="28779-307">Действие 1: создание "международные" использования PSTN</span><span class="sxs-lookup"><span data-stu-id="28779-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="28779-308">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем в правом верхнем углу выберите **Управление записями использование PSTN**.</span><span class="sxs-lookup"><span data-stu-id="28779-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="28779-309">Нажмите кнопку **Добавить**, введите **международные** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="28779-310">Действие 2: Создание голосового маршрута "международные"</span><span class="sxs-lookup"><span data-stu-id="28779-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="28779-311">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем откройте вкладку **Голосовые маршруты** .</span><span class="sxs-lookup"><span data-stu-id="28779-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="28779-312">Нажмите кнопку **Добавить**, введите в качестве имени слово "международные" и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="28779-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="28779-313">Установите для приоритета значение 4, а затем установите для номера шаблона номер \d +.</span><span class="sxs-lookup"><span data-stu-id="28779-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="28779-314">В разделе **зарегистрированный SBCS (необязательно)** выберите команду **Добавить SBCs**, выберите sbc2.contoso.biz и Sbc5.contoso.biz и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="28779-315">В разделе **записи использования PSTN (необязательно)** нажмите кнопку **Добавить использование PSTN**, выберите запись "Международная связь по использованию PSTN", а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="28779-316">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="28779-317">Шаг 3: Создание политики маршрутизации голосовой связи с именем "без ограничений" и добавление в политику параметров использования PSTN "США и Канада" и "международные"</span><span class="sxs-lookup"><span data-stu-id="28779-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="28779-318">Использование PSTN "США и Канада" используется в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="28779-319">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28779-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="28779-320">Введите в качестве имени и добавьте описание **ограничения** .</span><span class="sxs-lookup"><span data-stu-id="28779-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="28779-321">В разделе **записи использования PSTN** выберите команду **Добавить использование PSTN**, выберите запись использование PSTN, а затем выберите "Международная" запись об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="28779-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="28779-322">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="28779-322">Click **Apply**.</span></span>

    <span data-ttu-id="28779-323">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="28779-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="28779-324">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, в этом примере используется маршрут, установленный в США и Канаде, и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="28779-325">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="28779-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="28779-326">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="28779-327">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-327">Click **Save**.</span></span>

<span data-ttu-id="28779-328">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28779-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="28779-329">Шаг 4: назначение политики маршрутизации голосовой связи пользователю Джон лесу</span><span class="sxs-lookup"><span data-stu-id="28779-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="28779-330">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="28779-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="28779-331">Нажмите **политики**, а затем рядом с пунктом **назначенные политики** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="28779-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="28779-332">В разделе **Политика маршрутизации голосовой связи** выберите политику "нет ограничений", а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28779-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="28779-333">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков в США, Канаде и международных звонках.</span><span class="sxs-lookup"><span data-stu-id="28779-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="28779-334">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="28779-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="28779-335">Действие 1: создание "международные" использования PSTN</span><span class="sxs-lookup"><span data-stu-id="28779-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="28779-336">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="28779-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="28779-337">Действие 2: создание нового маршрута голосовой связи с именем "Международная"</span><span class="sxs-lookup"><span data-stu-id="28779-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="28779-338">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="28779-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="28779-339">Шаг 3: Создание политики маршрутизации голосовой связи с именем "без ограничений"</span><span class="sxs-lookup"><span data-stu-id="28779-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="28779-340">Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="28779-341">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="28779-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="28779-342">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, вызов проходит по маршруту, заданному в разделе "США и Канада", и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="28779-343">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="28779-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="28779-344">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="28779-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="28779-345">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="28779-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="28779-346">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="28779-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="28779-347">Шаг 4: назначение политики маршрутизации голосовой связи пользователю Джон лесу</span><span class="sxs-lookup"><span data-stu-id="28779-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="28779-348">Затем проверьте назначение с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="28779-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="28779-349">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="28779-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="28779-350">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="28779-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="28779-351">См. также</span><span class="sxs-lookup"><span data-stu-id="28779-351">See also</span></span>

[<span data-ttu-id="28779-352">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="28779-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="28779-353">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="28779-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
