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
ms.openlocfilehash: 37343ad177e3408f94103296509e4b9bfc8ea759
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359415"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="a152c-103">Настройка маршрутизации голосовой связи для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a152c-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="a152c-104">В этой статье описано, как настроить маршрутизацию голосовой связи для прямой маршрутизации телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="a152c-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="a152c-105">Это действие 3 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="a152c-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="a152c-106">Step 1.</span></span> [<span data-ttu-id="a152c-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="a152c-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="a152c-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="a152c-108">Step 2.</span></span> [<span data-ttu-id="a152c-109">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a152c-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="a152c-110">**Шаг 3. Настройка голосовой маршрутизации** (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="a152c-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="a152c-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="a152c-111">Step 4.</span></span> [<span data-ttu-id="a152c-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="a152c-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="a152c-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a152c-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="a152c-114">Общие сведения о маршрутизации голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a152c-114">Voice routing overview</span></span>

<span data-ttu-id="a152c-115">В телефонной системе Microsoft есть механизм маршрутизации, позволяющий отправлять звонки на определенный контроллер границ сеанса (SBC), основанный на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="a152c-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="a152c-116">Вызываемый шаблон номера</span><span class="sxs-lookup"><span data-stu-id="a152c-116">The called number pattern</span></span> 
- <span data-ttu-id="a152c-117">Вызываемый шаблон номера и конкретный пользователь, который совершает звонок;</span><span class="sxs-lookup"><span data-stu-id="a152c-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="a152c-118">SBCs можно назначить активными и архивировать.</span><span class="sxs-lookup"><span data-stu-id="a152c-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="a152c-119">Если объект SBC, настроенный как активный, недоступен для определенного маршрута вызова, этот звонок будет перенаправлен на одноэлементный объект SBC.</span><span class="sxs-lookup"><span data-stu-id="a152c-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="a152c-120">Маршрутизация голосовой связи состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="a152c-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="a152c-121">**Политика маршрутизации голосовой связи** — контейнер использования PSTN, который можно назначить пользователю или нескольким пользователям.</span><span class="sxs-lookup"><span data-stu-id="a152c-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="a152c-122">**Использование PSTN** — контейнер для голосовых маршрутов и использование PSTN, которые можно использовать в разных политиках голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="a152c-123">**Голосовые маршруты** — шаблон номера и набор сетевых шлюзов, используемых для звонков, где номер звонка соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a152c-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="a152c-124">**Сетевой шлюз PSTN** — указатель на объект SBC, который также хранит конфигурацию, которая применяется при размещении вызова через SBC, например переадресация (PAI) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты.</span><span class="sxs-lookup"><span data-stu-id="a152c-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="a152c-125">Рекомендации по политике голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a152c-125">Voice routing policy considerations</span></span>

<span data-ttu-id="a152c-126">Если у пользователя есть лицензия на план звонков, исходящие звонки пользователя автоматически пересылаются по плану КОММУТИРУЕМого вызова Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a152c-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="a152c-127">Если вы настраиваете и назначаете политику сетевой маршрутизации для абонента абонентского плана, исходящие звонки пользователя проверяются, чтобы определить, соответствует ли номер шаблону, определенному в политике голосовой маршрутизации в сети.</span><span class="sxs-lookup"><span data-stu-id="a152c-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="a152c-128">Если совпадение найдено, Звонок направляется по прямой магистрали маршрута.</span><span class="sxs-lookup"><span data-stu-id="a152c-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="a152c-129">Если совпадение не найдено, Звонок направляется по инфраструктуре КОММУТИРУЕМого тарифного плана.</span><span class="sxs-lookup"><span data-stu-id="a152c-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="a152c-130">Если вы настроили и применяете глобальную политику сетевой маршрутизации по умолчанию, то все пользователи, поддерживающие голосовую почту в вашей организации, будут наследовать эту политику, что может привести к непреднамеренному перенаправлению звонков из плана КОММУТИРУЕМых пользователей на прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="a152c-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="a152c-131">Если вы не хотите, чтобы все пользователи использовали глобальную политику сетевой маршрутизации, настройте специальную политику голосовой связи и назначьте ее отдельным пользователям, поддерживающим голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a152c-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="a152c-132">Пример 1: Маршрутизация голосовой связи с использованием одной PSTN</span><span class="sxs-lookup"><span data-stu-id="a152c-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="a152c-133">На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="a152c-134">**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a152c-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a152c-135">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="a152c-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="a152c-136">**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a152c-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a152c-137">Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="a152c-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="a152c-138">Если ни одна из этих SBCs недоступна, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="a152c-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="a152c-140">В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="a152c-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a152c-141">Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются.</span><span class="sxs-lookup"><span data-stu-id="a152c-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="a152c-142">Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a152c-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="a152c-143">План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="a152c-144">В примере, показанном на приведенной ниже схеме, маршрут голосовой связи добавляется для отправки звонков на все остальные номера США и Канады (звонки, находящиеся под названием "шаблон номера" + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="a152c-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="a152c-146">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="a152c-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="a152c-147">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, этот звонок направляется через план звонков по Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a152c-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="a152c-148">Если у пользователя есть только телефонная система Microsoft, вызов отбрасывается из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="a152c-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a152c-149">Значение приоритета для маршрута "Other + 1" не имеет значения в этом случае, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="a152c-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="a152c-150">Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="a152c-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="a152c-151">В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="a152c-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="a152c-152">В этом примере все три маршрута относятся к одной и той же использованию PSTN, а именно "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="a152c-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="a152c-153">Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только для США".</span><span class="sxs-lookup"><span data-stu-id="a152c-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="a152c-154">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="a152c-154">**PSTN usage**</span></span>|<span data-ttu-id="a152c-155">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="a152c-155">**Voice route**</span></span>|<span data-ttu-id="a152c-156">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="a152c-156">**Number pattern**</span></span>|<span data-ttu-id="a152c-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a152c-157">**Priority**</span></span>|<span data-ttu-id="a152c-158">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="a152c-158">**SBC**</span></span>|<span data-ttu-id="a152c-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a152c-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a152c-160">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-160">US and Canada</span></span>|<span data-ttu-id="a152c-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a152c-161">"Redmond 1"</span></span>|<span data-ttu-id="a152c-162">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a152c-163">1</span><span class="sxs-lookup"><span data-stu-id="a152c-163">1</span></span>|<span data-ttu-id="a152c-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a152c-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="a152c-166">Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a152c-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a152c-167">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-167">US and Canada</span></span>|<span data-ttu-id="a152c-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a152c-168">"Redmond 2"</span></span>|<span data-ttu-id="a152c-169">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a152c-170">2</span><span class="sxs-lookup"><span data-stu-id="a152c-170">2</span></span>|<span data-ttu-id="a152c-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a152c-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="a152c-173">Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a152c-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a152c-174">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-174">US and Canada</span></span>|<span data-ttu-id="a152c-175">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="a152c-175">"Other +1"</span></span>|<span data-ttu-id="a152c-176">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a152c-177">3</span><span class="sxs-lookup"><span data-stu-id="a152c-177">3</span></span>|<span data-ttu-id="a152c-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a152c-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="a152c-180">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a152c-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="a152c-181">Пример 1: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="a152c-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="a152c-182">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a152c-182">The following example shows how to:</span></span>

1. <span data-ttu-id="a152c-183">Создание единственной неиспользуемой PSTN.</span><span class="sxs-lookup"><span data-stu-id="a152c-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="a152c-184">Настройте три голосовых маршрута.</span><span class="sxs-lookup"><span data-stu-id="a152c-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="a152c-185">Создание политики голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="a152c-186">Назначьте политику пользователю с именем Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="a152c-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="a152c-187">Вы можете выполнить эти действия с помощью [центра администрирования Microsoft Teams](#admincenterexample1) или [PowerShell](#powershellexample1) .</span><span class="sxs-lookup"><span data-stu-id="a152c-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a152c-188">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a152c-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="a152c-189">Действие 1: создание КОММУТИРУЕМого использования "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="a152c-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="a152c-190">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем в правом верхнем углу выберите **Управление записями использование PSTN**.</span><span class="sxs-lookup"><span data-stu-id="a152c-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="a152c-191">Нажмите кнопку **Добавить**, введите **US и Канада**, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="a152c-192">Действие 2: создание трех голосовых маршрутов (Redmond 1, Redmond 2 и другие + 1)</span><span class="sxs-lookup"><span data-stu-id="a152c-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="a152c-193">Ниже описана процедура создания голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="a152c-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="a152c-194">Выполните указанные ниже действия, чтобы создать три Голосовые маршруты с названием Redmond 1, Redmond 2 и другие + 1 для этого примера с использованием параметров, описанных в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="a152c-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="a152c-195">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем откройте вкладку **Голосовые маршруты** .</span><span class="sxs-lookup"><span data-stu-id="a152c-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="a152c-196">Нажмите кнопку **Добавить**, а затем введите имя и описание для голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="a152c-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="a152c-197">Задайте приоритет и укажите шаблон номера для набора номера.</span><span class="sxs-lookup"><span data-stu-id="a152c-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="a152c-198">Чтобы зарегистрировать SBC с голосовым маршрутом, в разделе **Регистрация голоса (необязательно)** выберите команду **Добавить SBCS**, выберите однобайтовую запись, которую вы хотите зарегистрировать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="a152c-199">Чтобы добавить записи об использовании PSTN, в разделе **записи использования PSTN (необязательно)** нажмите кнопку **Добавить использование PSTN**, выберите записи PSTN, которые вы хотите добавить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="a152c-200">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="a152c-201">Шаг 3: Создание политики голосовой маршрутизации с именем "только США" и добавление в политику использования PSTN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="a152c-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="a152c-202">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="a152c-203">Введите **US только** в качестве имени и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="a152c-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="a152c-204">В разделе **записи использования PSTN**выберите **Добавить использование PSTN**, выберите запись использование PSTN, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="a152c-205">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-205">Click **Save**.</span></span>

<span data-ttu-id="a152c-206">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a152c-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="a152c-207">Шаг 4: назначение политики маршрутизации голосовой связи пользователю с именем Spencer Low</span><span class="sxs-lookup"><span data-stu-id="a152c-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="a152c-208">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="a152c-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a152c-209">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="a152c-210">В разделе **Политика маршрутизации голосовой связи**выберите политику "только США", а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="a152c-211">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a152c-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a152c-212">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="a152c-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="a152c-213">Действие 1: создание КОММУТИРУЕМого использования "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="a152c-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="a152c-214">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="a152c-215">Убедитесь в том, что использование было создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="a152c-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="a152c-216">Возвращающий список имен, которые могут быть усечены:</span><span class="sxs-lookup"><span data-stu-id="a152c-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="a152c-217">В следующем примере показан результат выполнения `(Get-CSOnlinePSTNUsage).usage` команды PowerShell для отображения полных имен (не усеченных):</span><span class="sxs-lookup"><span data-stu-id="a152c-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="a152c-218">Действие 2: создание трех голосовых маршрутов (Redmond 1, Redmond 2 и другие + 1)</span><span class="sxs-lookup"><span data-stu-id="a152c-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="a152c-219">Чтобы создать маршрут "Redmond 1" в сеансе PowerShell в Skype для бизнеса Online, введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a152c-220">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a152c-220">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="a152c-221">Чтобы создать маршрут на 2 Redmond, введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a152c-222">Чтобы создать другой маршрут + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="a152c-223">Убедитесь, что регулярное выражение в атрибуте NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="a152c-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="a152c-224">Вы можете протестировать его с помощью этого веб-сайта: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="a152c-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="a152c-225">В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Используйте-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="a152c-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="a152c-226">Перенаправлять все вызовы на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="a152c-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="a152c-227">Убедитесь, что маршрут настроен правильно, выполнив `Get-CSOnlineVoiceRoute` команду PowerShell, используя указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="a152c-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="a152c-228">Что должно вернуть:</span><span class="sxs-lookup"><span data-stu-id="a152c-228">Which should return:</span></span>
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

<span data-ttu-id="a152c-229">В примере для маршрута "Other + 1" автоматически назначается приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="a152c-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="a152c-230">Шаг 3: Создание политики голосовой маршрутизации с именем "только США" и добавление в политику использования PSTN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="a152c-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="a152c-231">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a152c-232">Результат показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="a152c-232">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="a152c-233">Шаг 4: назначение политики маршрутизации голосовой связи пользователю с именем Spencer Low</span><span class="sxs-lookup"><span data-stu-id="a152c-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="a152c-234">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="a152c-235">Чтобы проверить назначение политики, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a152c-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a152c-236">Команда возвращает следующее:</span><span class="sxs-lookup"><span data-stu-id="a152c-236">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="a152c-237">Пример 2: Маршрутизация голосовой связи с несколькими использованием PSTN</span><span class="sxs-lookup"><span data-stu-id="a152c-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="a152c-238">Политика маршрутизации голосовой связи, созданная в примере 1, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).</span><span class="sxs-lookup"><span data-stu-id="a152c-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="a152c-239">В приведенном ниже примере вы можете создать политику голосовой маршрутизации "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="a152c-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="a152c-240">Политика повторно использует использование PSTN в США и Канаде, созданное в примере 1, а также новое использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="a152c-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="a152c-241">Эта политика маршрутизирует все другие вызовы на SBCs sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a152c-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="a152c-242">Приведенные примеры применяют политику "только для США" для пользователей Spencer Low и политики "нет ограничений" для пользователя Джон лесу таким образом, чтобы маршрутизация была показана ниже.</span><span class="sxs-lookup"><span data-stu-id="a152c-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="a152c-243">Spencer низкий – только политика США.</span><span class="sxs-lookup"><span data-stu-id="a152c-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="a152c-244">Звонки разрешены только в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="a152c-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="a152c-245">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="a152c-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a152c-246">Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="a152c-247">Джон лесу – Международная политика.</span><span class="sxs-lookup"><span data-stu-id="a152c-247">John Woods – International policy.</span></span>  <span data-ttu-id="a152c-248">Звонки разрешены любому числу.</span><span class="sxs-lookup"><span data-stu-id="a152c-248">Calls are allowed to any number.</span></span> <span data-ttu-id="a152c-249">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="a152c-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a152c-250">Номера, не относящиеся к США, будут маршрутизироваться с помощью sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a152c-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю Spencer низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="a152c-252">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="a152c-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="a152c-253">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, вызов осуществляется с помощью плана звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a152c-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="a152c-254">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="a152c-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="a152c-256">В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="a152c-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="a152c-257">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="a152c-257">**PSTN usage**</span></span>|<span data-ttu-id="a152c-258">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="a152c-258">**Voice route**</span></span>|<span data-ttu-id="a152c-259">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="a152c-259">**Number pattern**</span></span>|<span data-ttu-id="a152c-260">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a152c-260">**Priority**</span></span>|<span data-ttu-id="a152c-261">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="a152c-261">**SBC**</span></span>|<span data-ttu-id="a152c-262">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a152c-262">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a152c-263">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-263">US and Canada</span></span>|<span data-ttu-id="a152c-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a152c-264">"Redmond 1"</span></span>|<span data-ttu-id="a152c-265">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a152c-266">1</span><span class="sxs-lookup"><span data-stu-id="a152c-266">1</span></span>|<span data-ttu-id="a152c-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a152c-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="a152c-269">Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a152c-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a152c-270">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-270">US and Canada</span></span>|<span data-ttu-id="a152c-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a152c-271">"Redmond 2"</span></span>|<span data-ttu-id="a152c-272">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a152c-273">2</span><span class="sxs-lookup"><span data-stu-id="a152c-273">2</span></span>|<span data-ttu-id="a152c-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a152c-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="a152c-276">Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a152c-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a152c-277">США и Канада</span><span class="sxs-lookup"><span data-stu-id="a152c-277">US and Canada</span></span>|<span data-ttu-id="a152c-278">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="a152c-278">"Other +1"</span></span>|<span data-ttu-id="a152c-279">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="a152c-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a152c-280">3</span><span class="sxs-lookup"><span data-stu-id="a152c-280">3</span></span>|<span data-ttu-id="a152c-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a152c-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="a152c-283">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a152c-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="a152c-284">International</span><span class="sxs-lookup"><span data-stu-id="a152c-284">International</span></span>|<span data-ttu-id="a152c-285">International</span><span class="sxs-lookup"><span data-stu-id="a152c-285">International</span></span>|<span data-ttu-id="a152c-286">\d +</span><span class="sxs-lookup"><span data-stu-id="a152c-286">\d+</span></span>|<span data-ttu-id="a152c-287">4</span><span class="sxs-lookup"><span data-stu-id="a152c-287">4</span></span>|<span data-ttu-id="a152c-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="a152c-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a152c-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="a152c-290">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="a152c-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="a152c-291">Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен.</span><span class="sxs-lookup"><span data-stu-id="a152c-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="a152c-292">Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="a152c-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="a152c-293">Использование КТСОП в международной сети по коммутируемой телефонной сети должно быть включено после использования КТСОП в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="a152c-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="a152c-294">Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="a152c-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="a152c-295">Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a152c-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="a152c-296">Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="a152c-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="a152c-297">Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="a152c-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="a152c-298">Пример 2: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="a152c-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="a152c-299">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a152c-299">The following example shows how to:</span></span>

1. <span data-ttu-id="a152c-300">Создайте новую использование PSTN, именуемое международным.</span><span class="sxs-lookup"><span data-stu-id="a152c-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="a152c-301">Создайте новый голосовой маршрут с именем International.</span><span class="sxs-lookup"><span data-stu-id="a152c-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="a152c-302">Создание политики голосовой маршрутизации с именем "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="a152c-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="a152c-303">Назначьте политику пользователю John лесу.</span><span class="sxs-lookup"><span data-stu-id="a152c-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="a152c-304">Вы можете выполнить эти действия с помощью [центра администрирования Microsoft Teams](#admincenterexample2) или [PowerShell](#powershellexample2) .</span><span class="sxs-lookup"><span data-stu-id="a152c-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a152c-305">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a152c-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="a152c-306">Действие 1: создание "международные" использования PSTN</span><span class="sxs-lookup"><span data-stu-id="a152c-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="a152c-307">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем в правом верхнем углу выберите **Управление записями использование PSTN**.</span><span class="sxs-lookup"><span data-stu-id="a152c-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="a152c-308">Нажмите кнопку **Добавить**, введите **международные**и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="a152c-309">Действие 2: Создание голосового маршрута "международные"</span><span class="sxs-lookup"><span data-stu-id="a152c-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="a152c-310">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел Переадресация **голосовых сообщений**  >  **Direct Routing**, а затем откройте вкладку **Голосовые маршруты** .</span><span class="sxs-lookup"><span data-stu-id="a152c-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="a152c-311">Нажмите кнопку **Добавить**, введите в качестве имени слово "международные" и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="a152c-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="a152c-312">Установите для приоритета значение 4, а затем установите для номера шаблона номер \d +.</span><span class="sxs-lookup"><span data-stu-id="a152c-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="a152c-313">В разделе **зарегистрированный SBCS (необязательно)** выберите команду **Добавить SBCs**, выберите sbc2.contoso.biz и Sbc5.contoso.biz и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="a152c-314">В разделе **записи использования PSTN (необязательно)** нажмите кнопку **Добавить использование PSTN**, выберите запись "Международная связь по использованию PSTN", а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="a152c-315">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="a152c-316">Шаг 3: Создание политики маршрутизации голосовой связи с именем "без ограничений" и добавление в политику параметров использования PSTN "США и Канада" и "международные"</span><span class="sxs-lookup"><span data-stu-id="a152c-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="a152c-317">Использование PSTN "США и Канада" используется в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="a152c-318">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="a152c-319">Введите в качестве имени и добавьте описание **ограничения** .</span><span class="sxs-lookup"><span data-stu-id="a152c-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="a152c-320">В разделе **записи использования PSTN**выберите команду **Добавить использование PSTN**, выберите запись использование PSTN, а затем выберите "Международная" запись об использовании PSTN.</span><span class="sxs-lookup"><span data-stu-id="a152c-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="a152c-321">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-321">Click **Apply**.</span></span>

    <span data-ttu-id="a152c-322">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="a152c-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="a152c-323">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, в этом примере используется маршрут, установленный в США и Канаде, и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a152c-324">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a152c-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="a152c-325">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="a152c-326">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-326">Click **Save**.</span></span>

<span data-ttu-id="a152c-327">Дополнительные сведения можно найти в статье [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a152c-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="a152c-328">Шаг 4: назначение политики маршрутизации голосовой связи пользователю Джон лесу</span><span class="sxs-lookup"><span data-stu-id="a152c-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="a152c-329">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="a152c-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a152c-330">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="a152c-331">В разделе **Политика маршрутизации голосовой связи**выберите политику "нет ограничений", а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a152c-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="a152c-332">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков в США, Канаде и международных звонках.</span><span class="sxs-lookup"><span data-stu-id="a152c-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a152c-333">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="a152c-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="a152c-334">Действие 1: создание "международные" использования PSTN</span><span class="sxs-lookup"><span data-stu-id="a152c-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="a152c-335">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="a152c-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="a152c-336">Действие 2: создание нового маршрута голосовой связи с именем "Международная"</span><span class="sxs-lookup"><span data-stu-id="a152c-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="a152c-337">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a152c-337">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="a152c-338">Шаг 3: Создание политики маршрутизации голосовой связи с именем "без ограничений"</span><span class="sxs-lookup"><span data-stu-id="a152c-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="a152c-339">Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a152c-340">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="a152c-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="a152c-341">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, вызов проходит по маршруту, заданному в разделе "США и Канада", и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a152c-342">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a152c-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="a152c-343">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a152c-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="a152c-344">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="a152c-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a152c-345">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a152c-345">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="a152c-346">Шаг 4: назначение политики маршрутизации голосовой связи пользователю Джон лесу</span><span class="sxs-lookup"><span data-stu-id="a152c-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="a152c-347">Затем проверьте назначение с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="a152c-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a152c-348">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a152c-348">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="a152c-349">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="a152c-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="a152c-350">См. также</span><span class="sxs-lookup"><span data-stu-id="a152c-350">See also</span></span>

[<span data-ttu-id="a152c-351">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a152c-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="a152c-352">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a152c-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
