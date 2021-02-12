---
title: Настройка голосовой маршрутии для прямой маршрутинга
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
description: Узнайте, как настроить маршрутику голосовой связи с помощью прямой маршрутии microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530996"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="aa841-103">Настройка голосовой маршрутии для прямой маршрутинга</span><span class="sxs-lookup"><span data-stu-id="aa841-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="aa841-104">В этой статье описано, как настроить маршрутику голосовой связи для прямой маршрутии телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="aa841-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="aa841-105">Это шаг 3 из следующих действий по настройке прямой маршрутинга:</span><span class="sxs-lookup"><span data-stu-id="aa841-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="aa841-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="aa841-106">Step 1.</span></span> [<span data-ttu-id="aa841-107">Подключение SBC к телефонной системе Майкрософт и проверка подключения</span><span class="sxs-lookup"><span data-stu-id="aa841-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="aa841-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="aa841-108">Step 2.</span></span> [<span data-ttu-id="aa841-109">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="aa841-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="aa841-110">**Шаг 3. Настройка голосовой маршрутии** (эта статья)</span><span class="sxs-lookup"><span data-stu-id="aa841-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="aa841-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="aa841-111">Step 4.</span></span> [<span data-ttu-id="aa841-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="aa841-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="aa841-113">Сведения о всех шагах, необходимых для настройки прямой маршрутинга, см. в этой [ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="aa841-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="aa841-114">Общие сведения о маршрутике голосовой почты</span><span class="sxs-lookup"><span data-stu-id="aa841-114">Voice routing overview</span></span>

<span data-ttu-id="aa841-115">В телефонной системе Майкрософт есть механизм маршрутации, позволяющий перенаправить звонок на определенный пограничный контроллер сеанса на основе:</span><span class="sxs-lookup"><span data-stu-id="aa841-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="aa841-116">The called number pattern</span><span class="sxs-lookup"><span data-stu-id="aa841-116">The called number pattern</span></span> 
- <span data-ttu-id="aa841-117">Шаблон вызываемого номера, а также конкретный пользователь, который совершает звонок</span><span class="sxs-lookup"><span data-stu-id="aa841-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="aa841-118">SBCs можно сделать активными и резервными копиями.</span><span class="sxs-lookup"><span data-stu-id="aa841-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="aa841-119">Если SBC, настроенная как активная, недоступна для определенного маршрута звонка, звонок будет перенанотирован на резервную копию SBC.</span><span class="sxs-lookup"><span data-stu-id="aa841-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="aa841-120">Маршрутия голоса состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="aa841-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="aa841-121">**Политика маршрутинга голосовой почты** — это контейнер для использования услуг ННР, который можно на назначенное пользователю или нескольким пользователям.</span><span class="sxs-lookup"><span data-stu-id="aa841-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="aa841-122">**Использование услуг ННР** — контейнер для голосовых маршрутов и использования услуг ОКП, который можно использовать в различных политиках маршрутинга голосовой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="aa841-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="aa841-123">**Голосовые маршруты** — шаблон номера и набор сетевых шлюзов ОКП для использования для звонков, номер которых соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="aa841-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="aa841-124">Сетевой шлюз **ННР** — указатель на SBC, который также сохраняет конфигурацию, применяемую при звонке через SBC, например переадпоряцию P-ИТ(PAI) или предпочтительные кодеки; могут быть добавлены в голосовые маршруты.</span><span class="sxs-lookup"><span data-stu-id="aa841-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="aa841-125">Вопросы, которые необходимо учитывать в политике маршрутинга голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="aa841-125">Voice routing policy considerations</span></span>

<span data-ttu-id="aa841-126">Если у пользователя есть лицензия на план звонков, исходяющие звонки этого пользователя автоматически маршрутируются через инфраструктуру ННР плана звонков (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="aa841-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="aa841-127">Если настроить и назначить политику маршрутинга голосовой почты через Интернет пользователю плана звонков, исходяющие звонки будут проверяться на то, соответствует ли номер шаблону номера, определенному в политике маршрутинга голосовой почты в Интернете.</span><span class="sxs-lookup"><span data-stu-id="aa841-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="aa841-128">Если есть совпадение, звонок направляется по прямой линии маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="aa841-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="aa841-129">Если совпадений нет, звонок передается по инфраструктуре ЗВОНКОВ по плану ЗВОНКОВ.</span><span class="sxs-lookup"><span data-stu-id="aa841-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="aa841-130">Если вы настроите и примените глобальную (по умолчанию в организации) политику маршрутизации голосовой связи в Интернете, все пользователи в организации, которые будут использовать голосовую связь, унаследуют эту политику, что может привести к непреднамеренной маршрутизации звонков от пользователей плана звонков на прямую маршрутизовую линию.</span><span class="sxs-lookup"><span data-stu-id="aa841-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="aa841-131">Если вы не хотите, чтобы все пользователи использовали глобальную политику маршрутинга голосовой почты в Интернете, настройте настраиваемую политику маршрутинга голосовой почты в Интернете и назначьте ее отдельным пользователям с поддержкой голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="aa841-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="aa841-132">Пример 1. Маршрутия голосовой связи с одним использованием ННР</span><span class="sxs-lookup"><span data-stu-id="aa841-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="aa841-133">На следующей схеме показаны два примера политик маршрутинга голосовой маршрутии в потоке зовов.</span><span class="sxs-lookup"><span data-stu-id="aa841-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="aa841-134">**Поток 1 звонка (слева):** Если пользователь звонит на номер +1 425 XXX XX или +1 206 XXX XX XX, звонок будет перенанот в SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="aa841-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="aa841-135">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, звонок будет сброшен.</span><span class="sxs-lookup"><span data-stu-id="aa841-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="aa841-136">**Поток звонка 2 (справа):** Если пользователь звонит на номер +1 425 XXX XX или +1 206 XXX XX XX, звонок сначала перенанается на номер SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="aa841-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="aa841-137">Если ни одна из SBC недоступна, будет опробовен маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="aa841-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="aa841-138">Если ни один из SBCs не доступен, звонок будет сброшен.</span><span class="sxs-lookup"><span data-stu-id="aa841-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политик маршрутинга голоса](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="aa841-140">В обоих примерах, когда приоритеты голосового маршрута назначены, АСК в маршрутах будут отбираются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="aa841-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="aa841-141">Если два SBC настроены в одном маршруте, сетевой трафик должен быть маршрутизовым между SBC и мультимедиа не удастся установить для передачи, так как может быть отправлено новое приглашение для передачи на другой SBC в маршруте.</span><span class="sxs-lookup"><span data-stu-id="aa841-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aa841-142">Если у пользователя нет лицензии на план звонков Майкрософт, звонки будут звонить на любые номера, кроме номеров, которые соответствуют шаблонам +1 425 XXX XX XX или +1 206 XXX XX XX XX в примере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aa841-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="aa841-143">Если у пользователя есть лицензия на план звонков, звонок автоматически передается в соответствии с политиками плана звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa841-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="aa841-144">План звонков Майкрософт применяется автоматически в качестве последнего маршрута для всех пользователей с лицензией на план звонков Майкрософт и не требует дополнительной настройки маршрутинга звонков.</span><span class="sxs-lookup"><span data-stu-id="aa841-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="aa841-145">В приведеном ниже примере для отправки звонков на все остальные номера в США и Канаде добавляется голосовой маршрут (звонки по шаблону номера +1 XXX XXX XX XX XX).</span><span class="sxs-lookup"><span data-stu-id="aa841-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Отображает политику маршрутинга голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="aa841-147">Если у пользователя есть обе лицензии (microsoft Phone System и план звонков Майкрософт), для всех остальных звонков используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="aa841-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="aa841-148">Если ничего не соответствует шаблонам номеров в сетевых голосовых маршрутах, созданных администратором, звонок перенаправлен по плану звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa841-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="aa841-149">Если у пользователя только телефонная система Майкрософт, вызов перенабется, так как не доступны правила.</span><span class="sxs-lookup"><span data-stu-id="aa841-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aa841-150">Значение приоритета для маршрутов "Другие +1" в данном случае не имеет значения, так как существует только один маршрут, который соответствует шаблону +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="aa841-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="aa841-151">Если пользователь звонит на +1 324 567 89 89 и обе sbc5.contoso.biz и sbc6.contoso.biz недоступны, звонок перенабется.</span><span class="sxs-lookup"><span data-stu-id="aa841-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="aa841-152">В таблице ниже подытоживается конфигурация с использованием трех голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="aa841-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="aa841-153">В этом примере все три маршрута являются частью одного и того же использования ННП (США и Канада).</span><span class="sxs-lookup"><span data-stu-id="aa841-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="aa841-154">Все маршруты связаны с использованием ННР "США и Канада", а использование ПС — с политикой голосовой маршрутки "Только в США".</span><span class="sxs-lookup"><span data-stu-id="aa841-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="aa841-155">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="aa841-155">**PSTN usage**</span></span>|<span data-ttu-id="aa841-156">**Голосовой маршрут**</span><span class="sxs-lookup"><span data-stu-id="aa841-156">**Voice route**</span></span>|<span data-ttu-id="aa841-157">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="aa841-157">**Number pattern**</span></span>|<span data-ttu-id="aa841-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="aa841-158">**Priority**</span></span>|<span data-ttu-id="aa841-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="aa841-159">**SBC**</span></span>|<span data-ttu-id="aa841-160">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aa841-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa841-161">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-161">US and Canada</span></span>|<span data-ttu-id="aa841-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="aa841-162">"Redmond 1"</span></span>|<span data-ttu-id="aa841-163">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aa841-164">1</span><span class="sxs-lookup"><span data-stu-id="aa841-164">1</span></span>|<span data-ttu-id="aa841-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="aa841-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="aa841-167">Активный маршрут для номеров: +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aa841-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aa841-168">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-168">US and Canada</span></span>|<span data-ttu-id="aa841-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="aa841-169">"Redmond 2"</span></span>|<span data-ttu-id="aa841-170">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aa841-171">2</span><span class="sxs-lookup"><span data-stu-id="aa841-171">2</span></span>|<span data-ttu-id="aa841-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="aa841-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="aa841-174">Резервный маршрут для номеров: +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aa841-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aa841-175">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-175">US and Canada</span></span>|<span data-ttu-id="aa841-176">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="aa841-176">"Other +1"</span></span>|<span data-ttu-id="aa841-177">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="aa841-178">3</span><span class="sxs-lookup"><span data-stu-id="aa841-178">3</span></span>|<span data-ttu-id="aa841-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="aa841-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="aa841-181">Маршрут для номеров+ 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="aa841-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="aa841-182">Пример 1. Шаги настройки</span><span class="sxs-lookup"><span data-stu-id="aa841-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="aa841-183">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="aa841-183">The following example shows how to:</span></span>

1. <span data-ttu-id="aa841-184">Создание единого использования ННР.</span><span class="sxs-lookup"><span data-stu-id="aa841-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="aa841-185">Настройте три голосовых маршрута.</span><span class="sxs-lookup"><span data-stu-id="aa841-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="aa841-186">Создайте политику маршрутинга голоса.</span><span class="sxs-lookup"><span data-stu-id="aa841-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="aa841-187">Назначьте политику пользователю с именем "Низкий".</span><span class="sxs-lookup"><span data-stu-id="aa841-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="aa841-188">Для выполнения этих [действий можно использовать](#admincenterexample1) Центр администрирования Microsoft Teams или [PowerShell.](#powershellexample1)</span><span class="sxs-lookup"><span data-stu-id="aa841-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="aa841-189">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa841-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="aa841-190">Шаг 1. Создание ПОЛЬЗОВАНИЯ ННР "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="aa841-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="aa841-191">В левой области навигации Центра администрирования Microsoft Teams перейдите к маршруту **Voice** Direct Routing, а затем в правом верхнем углу выберите "Управление записями использования  >   **ННР".**</span><span class="sxs-lookup"><span data-stu-id="aa841-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="aa841-192">Нажмите **кнопку "Добавить",** **введите "США" и "Канада"** и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="aa841-193">Шаг 2. Создание трех голосовых маршрутов (Redmond 1, Redmond 2 и Other +1)</span><span class="sxs-lookup"><span data-stu-id="aa841-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="aa841-194">Ниже описано, как создать голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="aa841-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="aa841-195">Используйте эти шаги для создания трех голосовых маршрутов с именами Redmond 1, Redmond 2 и Other +1 в данном примере с помощью параметров, описанных в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="aa841-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="aa841-196">В левой области навигации Центра администрирования Microsoft Teams перейдите к маршруту **Voice** Direct Routing и выберите вкладку  >   **"Маршруты голосовой связи".**</span><span class="sxs-lookup"><span data-stu-id="aa841-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="aa841-197">Нажмите **кнопку**"Добавить" и введите имя и описание голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="aa841-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="aa841-198">Закажите приоритет и шаблон набора номера.</span><span class="sxs-lookup"><span data-stu-id="aa841-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="aa841-199">Чтобы зарегистрировать SBC с помощью голосового маршрута, в регистрациях **SBCs (необязательно)** нажмите кнопку "Добавить **SBCs", выберите SBCs,** которые вы хотите зарегистрировать, и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="aa841-200">Чтобы добавить записи использования ДНР, в записях использования ННР **(необязательно)** щелкните "Добавить использование ННР", выберите записи, которые нужно добавить, и нажмите кнопку "Применить". </span><span class="sxs-lookup"><span data-stu-id="aa841-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="aa841-201">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa841-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="aa841-202">Шаг 3. Создание политики голосовой маршрутки с именем "Только ДЛЯ США" и добавление в нее использования ННР "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="aa841-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="aa841-203">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутации голосовой голосовой почты и нажмите кнопку  >   **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="aa841-204">Введите **имя "США"** только в качестве имени и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="aa841-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="aa841-205">В **записях** использования ДНР щелкните "Добавить использование **ПС** ДНР", выберите запись использования ННР "США и Канада" и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="aa841-206">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa841-206">Click **Save**.</span></span>

<span data-ttu-id="aa841-207">Дополнительные узнать об этом см. в [управлении политиками маршрутинга голосовой почты.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="aa841-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="aa841-208">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем "Низкий уровень"</span><span class="sxs-lookup"><span data-stu-id="aa841-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="aa841-209">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa841-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="aa841-210">Щелкните **"Политики",** а затем рядом с **кнопкой "Назначенные политики"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="aa841-211">В **области "Политика маршрутинга голосовой** почты" выберите политику "Только для США" и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="aa841-212">Дополнительные узнать об этом см. в [управлении политиками маршрутинга голосовой почты.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="aa841-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aa841-213">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa841-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="aa841-214">Шаг 1. Создание ПОЛЬЗОВАНИЯ ННР "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="aa841-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="aa841-215">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="aa841-216">Убедитесь, что использование было создано, введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="aa841-217">Возвращает список усеченных имен.</span><span class="sxs-lookup"><span data-stu-id="aa841-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="aa841-218">В следующем примере показан результат запуска команды Powershell для отображения полных имен `(Get-CSOnlinePSTNUsage).usage` (без усеченных):</span><span class="sxs-lookup"><span data-stu-id="aa841-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="aa841-219">Шаг 2. Создание трех голосовых маршрутов (Redmond 1, Redmond 2 и Other +1)</span><span class="sxs-lookup"><span data-stu-id="aa841-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="aa841-220">Чтобы создать маршрут Redmond 1, в сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aa841-221">Возвращаемая возвращаемая</span><span class="sxs-lookup"><span data-stu-id="aa841-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="aa841-222">Чтобы создать маршрут Редмонда 2, введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aa841-223">Чтобы создать маршрут "Другие +1", введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="aa841-224">Убедитесь, что регулярное выражение в атрибуте NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="aa841-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="aa841-225">Вы можете проверить это с помощью этого веб-сайта: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="aa841-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="aa841-226">В некоторых случаях требуется перена должны перена должны перенанаться все звонки на один и тот же SBC; use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="aa841-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="aa841-227">Перена маршрутизовы всех звонков на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="aa841-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="aa841-228">Проверьте правильность настройки маршрута путем запуска команды PowerShell с использованием `Get-CSOnlineVoiceRoute` параметров, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="aa841-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="aa841-229">Возвращаемая</span><span class="sxs-lookup"><span data-stu-id="aa841-229">Which should return:</span></span>
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

<span data-ttu-id="aa841-230">В этом примере маршруту "Другие +1" автоматически был назначен приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="aa841-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="aa841-231">Шаг 3. Создание политики голосовой маршрутки с именем "Только ДЛЯ США" и добавление в нее использования ННР "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="aa841-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="aa841-232">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aa841-233">В этом примере показан результат:</span><span class="sxs-lookup"><span data-stu-id="aa841-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="aa841-234">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем "Низкий уровень"</span><span class="sxs-lookup"><span data-stu-id="aa841-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="aa841-235">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="aa841-236">Проверьте назначение политики, введите эту команду:</span><span class="sxs-lookup"><span data-stu-id="aa841-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="aa841-237">Команда возвращает следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aa841-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="aa841-238">Пример 2. Перенастройка голосовой связи с несколькими использованием услуг ННР</span><span class="sxs-lookup"><span data-stu-id="aa841-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="aa841-239">Политика маршрутинга голосовой связи, созданная в примере 1, позволяет звонить на телефонные номера только в США и Канаде, если пользователю не назначена лицензия на план звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa841-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="aa841-240">В примере, который вы видите в примере, можно создать политику маршрутки голоса "Нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="aa841-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="aa841-241">Политика повторно будет использовать использование ПС "США и Канада", созданное в примере 1, а также новое "международное" использование СТАНП.</span><span class="sxs-lookup"><span data-stu-id="aa841-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="aa841-242">Эта политика маршрутит все остальные вызовы на sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="aa841-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="aa841-243">В показанных примерах политика "Только в США" назначается пользователю "Низкий уровень" и политика "Нет ограничений" пользователю Ивану Ивану, чтобы маршрутная маршрутная маршрутия велись следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aa841-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="aa841-244">Неявная — политика только для США.</span><span class="sxs-lookup"><span data-stu-id="aa841-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="aa841-245">Звонки разрешены только на номера в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="aa841-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="aa841-246">При звонках в диапазон номеров Редмонда необходимо использовать определенный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="aa841-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="aa841-247">Номера не из США не будут маршрутизовы, если только пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="aa841-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="aa841-248">Джон Уайл — международная политика.</span><span class="sxs-lookup"><span data-stu-id="aa841-248">John Woods – International policy.</span></span>  <span data-ttu-id="aa841-249">Звонки разрешены на любой номер.</span><span class="sxs-lookup"><span data-stu-id="aa841-249">Calls are allowed to any number.</span></span> <span data-ttu-id="aa841-250">При звонках в диапазон номеров Редмонда необходимо использовать определенный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="aa841-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="aa841-251">Номера, не в сша, будут маршрутивться с помощью sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="aa841-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутинга голосовой почты, назначенная пользователю По низким уровням](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="aa841-253">Если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков Майкрософт), для всех остальных звонков используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="aa841-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="aa841-254">Если ничего не соответствует шаблонам номеров в сетевых голосовых маршрутах, созданных администратором, звонок перенаправлен с использованием плана звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa841-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="aa841-255">Если у пользователя только телефонная система Майкрософт, звонок перенабется, так как не доступны правила.</span><span class="sxs-lookup"><span data-stu-id="aa841-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутинга голосовой почты, назначенная пользователю ДжонУ Иванову](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="aa841-257">В таблице ниже общались политики маршрутизации с ограничениями использования и голосовой маршрутицией.</span><span class="sxs-lookup"><span data-stu-id="aa841-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="aa841-258">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="aa841-258">**PSTN usage**</span></span>|<span data-ttu-id="aa841-259">**Голосовой маршрут**</span><span class="sxs-lookup"><span data-stu-id="aa841-259">**Voice route**</span></span>|<span data-ttu-id="aa841-260">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="aa841-260">**Number pattern**</span></span>|<span data-ttu-id="aa841-261">**Priority**</span><span class="sxs-lookup"><span data-stu-id="aa841-261">**Priority**</span></span>|<span data-ttu-id="aa841-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="aa841-262">**SBC**</span></span>|<span data-ttu-id="aa841-263">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aa841-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa841-264">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-264">US and Canada</span></span>|<span data-ttu-id="aa841-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="aa841-265">"Redmond 1"</span></span>|<span data-ttu-id="aa841-266">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aa841-267">1</span><span class="sxs-lookup"><span data-stu-id="aa841-267">1</span></span>|<span data-ttu-id="aa841-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="aa841-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="aa841-270">Активный маршрут для телефонных номеров: +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aa841-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aa841-271">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-271">US and Canada</span></span>|<span data-ttu-id="aa841-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="aa841-272">"Redmond 2"</span></span>|<span data-ttu-id="aa841-273">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aa841-274">2</span><span class="sxs-lookup"><span data-stu-id="aa841-274">2</span></span>|<span data-ttu-id="aa841-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="aa841-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="aa841-277">Резервное копирование маршрута для номеров вызываемой телефонной карты +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aa841-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aa841-278">США и Канада</span><span class="sxs-lookup"><span data-stu-id="aa841-278">US and Canada</span></span>|<span data-ttu-id="aa841-279">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="aa841-279">"Other +1"</span></span>|<span data-ttu-id="aa841-280">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="aa841-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="aa841-281">3</span><span class="sxs-lookup"><span data-stu-id="aa841-281">3</span></span>|<span data-ttu-id="aa841-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="aa841-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="aa841-284">Маршрут для номеров вызываемой телефонной карты +1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="aa841-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="aa841-285">International</span><span class="sxs-lookup"><span data-stu-id="aa841-285">International</span></span>|<span data-ttu-id="aa841-286">International</span><span class="sxs-lookup"><span data-stu-id="aa841-286">International</span></span>|<span data-ttu-id="aa841-287">\d+</span><span class="sxs-lookup"><span data-stu-id="aa841-287">\d+</span></span>|<span data-ttu-id="aa841-288">4</span><span class="sxs-lookup"><span data-stu-id="aa841-288">4</span></span>|<span data-ttu-id="aa841-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="aa841-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aa841-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="aa841-291">Маршрут по любому шаблону номера</span><span class="sxs-lookup"><span data-stu-id="aa841-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="aa841-292">Порядок использования ННР в политиках голосовой маршрутки имеет крайне важное значение.</span><span class="sxs-lookup"><span data-stu-id="aa841-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="aa841-293">Использование применяется по порядку, а если совпадение найдено в первом использовании, то другие использования никогда не вычисляются.</span><span class="sxs-lookup"><span data-stu-id="aa841-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="aa841-294">После использования ОКП "США и Канада" необходимо сделать так, чтобы использование ОКП было "международным".</span><span class="sxs-lookup"><span data-stu-id="aa841-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="aa841-295">Чтобы изменить порядок использования ННР, запустите `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="aa841-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="aa841-296">Например, чтобы изменить порядок сначала с "США и Канада" на второй, а второй — на обратный, сменить порядок:</span><span class="sxs-lookup"><span data-stu-id="aa841-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="aa841-297">Приоритет голосовых маршрутов "Другие +1" и "Международные" наируются автоматически.</span><span class="sxs-lookup"><span data-stu-id="aa841-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="aa841-298">Они имеют более низкий приоритет, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="aa841-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="aa841-299">Пример 2. Шаги настройки</span><span class="sxs-lookup"><span data-stu-id="aa841-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="aa841-300">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="aa841-300">The following example shows how to:</span></span>

1. <span data-ttu-id="aa841-301">Создание нового правила использования ННР под названием "Международные".</span><span class="sxs-lookup"><span data-stu-id="aa841-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="aa841-302">Создайте новый голосовой маршрут под названием "Международные".</span><span class="sxs-lookup"><span data-stu-id="aa841-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="aa841-303">Создайте политику маршрутинга голосовой почты под названием "Нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="aa841-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="aa841-304">Назначьте политику пользователю Джону Ивану.</span><span class="sxs-lookup"><span data-stu-id="aa841-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="aa841-305">Для выполнения этих [действий можно использовать](#admincenterexample2) Центр администрирования Microsoft Teams или [PowerShell.](#powershellexample2)</span><span class="sxs-lookup"><span data-stu-id="aa841-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="aa841-306">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aa841-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="aa841-307">Шаг 1. Создание "международного" использования ДНР</span><span class="sxs-lookup"><span data-stu-id="aa841-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="aa841-308">В левой области навигации Центра администрирования Microsoft Teams перейдите к маршруту **Voice** Direct Routing, а затем в правом верхнем углу выберите "Управление записями использования  >   **ННР".**</span><span class="sxs-lookup"><span data-stu-id="aa841-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="aa841-309">Нажмите **кнопку "Добавить",** **введите**"Международные" и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="aa841-310">Шаг 2. Создание голосового маршрута "Международные"</span><span class="sxs-lookup"><span data-stu-id="aa841-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="aa841-311">В левой области навигации Центра администрирования Microsoft Teams перейдите к маршруту **Voice** Direct Routing и выберите вкладку  >   **"Маршруты голосовой связи".**</span><span class="sxs-lookup"><span data-stu-id="aa841-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="aa841-312">Нажмите **кнопку**"Добавить", введите в качестве имени название "Международные" и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="aa841-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="aa841-313">Установите для приоритета значение 4, а затем зайте для набра номера шаблон \d+.</span><span class="sxs-lookup"><span data-stu-id="aa841-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="aa841-314">В **области зарегистрированных SBCs (необязательно)** щелкните "Добавить **SBCs",** выберите sbc2.contoso.biz и sbc5.contoso.biz, а затем нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="aa841-315">В **записях** об использовании ДНР (необязательно) щелкните "Добавить использование **ПС ДНР",** выберите запись использования ОКП "Международные" и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="aa841-316">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa841-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="aa841-317">Шаг 3. Создание политики голосовой маршрутки с именем "Нет ограничений" и добавление в нее данных об использовании услуг ПС "США и Канада" и "Международные"</span><span class="sxs-lookup"><span data-stu-id="aa841-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="aa841-318">В этой политике перенаправки голосовой связи повторно зазвонены номера ННР", чтобы сохранить специальную обработку звонков на номера "+1 425 XXX XX XX" и "+1 206 XXX XX XX XX" как локальные и локальные звонки.</span><span class="sxs-lookup"><span data-stu-id="aa841-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="aa841-319">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутации голосовой голосовой почты и нажмите кнопку  >   **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="aa841-320">Введите **имя "Нет** ограничений" и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="aa841-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="aa841-321">В **записях** использования ОКП щелкните "Добавить использование ПС ДНР", выберите запись использования ННР "США и Канада", а затем выберите "Международный" запись использования ДНР.</span><span class="sxs-lookup"><span data-stu-id="aa841-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="aa841-322">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="aa841-322">Click **Apply**.</span></span>

    <span data-ttu-id="aa841-323">Обратите внимание на порядок использования услуг ННР:</span><span class="sxs-lookup"><span data-stu-id="aa841-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="aa841-324">Если звонок на номер "+1 425 XXX XX XX" с использованием, настроенным в данном примере, звонок передается по маршруту, заданной в стандарте "США и Канада", и применяется специальная логика маршрутации.</span><span class="sxs-lookup"><span data-stu-id="aa841-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="aa841-325">Это значит, что звонок сначала sbc1.contoso.biz и sbc2.contoso.biz, sbc3.contoso.biz и sbc4.contoso.biz в качестве запасных маршрутов.</span><span class="sxs-lookup"><span data-stu-id="aa841-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="aa841-326">Если до звонков на номер +1 425 XXX XX XX выбрана международная телефонная sbc2.contoso.biz и sbc5.contoso.biz, в логике маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="aa841-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="aa841-327">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa841-327">Click **Save**.</span></span>

<span data-ttu-id="aa841-328">Дополнительные узнать об этом см. в [управлении политиками маршрутинга голосовой почты.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="aa841-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="aa841-329">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем Иван</span><span class="sxs-lookup"><span data-stu-id="aa841-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="aa841-330">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa841-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="aa841-331">Щелкните **"Политики",** а затем рядом с **кнопкой "Назначенные политики"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="aa841-332">В **области "Политика маршрутинга голосовой** почты" выберите политику "Нет ограничений" и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="aa841-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="aa841-333">В результате политика голосовой связи, применяемая к звонкам Андрея Ивана Иванова, имеет неограниченные ограничений и будет следовать логике маршрутизазвонков, доступной для звонков в США, Канаде и международных звонках.</span><span class="sxs-lookup"><span data-stu-id="aa841-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aa841-334">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa841-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="aa841-335">Шаг 1. Создание "международного" использования ДНР</span><span class="sxs-lookup"><span data-stu-id="aa841-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="aa841-336">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="aa841-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="aa841-337">Шаг 2. Создание нового голосового маршрута с именем "Международные"</span><span class="sxs-lookup"><span data-stu-id="aa841-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="aa841-338">Возвращаемая возвращаемая</span><span class="sxs-lookup"><span data-stu-id="aa841-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="aa841-339">Шаг 3. Создание политики голосовой маршрутки с именем "Нет ограничений"</span><span class="sxs-lookup"><span data-stu-id="aa841-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="aa841-340">В этой политике маршрутации голосовой связи повторно повторно за счет использования услуг ПС "Редмонд 1" и "Редмонд" сохраняются специальные правила обработки звонков на номера "+1 425 XXX XX XX" и "+1 206 XXX XX XX XX" как локальные и локальные звонки.</span><span class="sxs-lookup"><span data-stu-id="aa841-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="aa841-341">Обратите внимание на порядок использования услуг ННР:</span><span class="sxs-lookup"><span data-stu-id="aa841-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="aa841-342">Если звонок на номер "+1 425 XXX XX XX" с использованием, настроенным, как по следующему примеру, звонок передается по маршруту, заехаемому в соответствии с использованием языка "США и Канада", и применяется специальная логика маршрутации.</span><span class="sxs-lookup"><span data-stu-id="aa841-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="aa841-343">Это значит, что звонок сначала sbc1.contoso.biz и sbc2.contoso.biz, sbc3.contoso.biz и sbc4.contoso.biz в качестве запасных маршрутов.</span><span class="sxs-lookup"><span data-stu-id="aa841-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="aa841-344">Если до звонков на номер +1 425 XXX XX XX выбрана международная телефонная sbc2.contoso.biz и sbc5.contoso.biz, в логике маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="aa841-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="aa841-345">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="aa841-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="aa841-346">Возвращаемая возвращаемая</span><span class="sxs-lookup"><span data-stu-id="aa841-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="aa841-347">Шаг 4. Назначение политики маршрутинга голосовой почты пользователю с именем Иван Иванов</span><span class="sxs-lookup"><span data-stu-id="aa841-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="aa841-348">Затем проверьте задание с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="aa841-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="aa841-349">Возвращаемая возвращаемая</span><span class="sxs-lookup"><span data-stu-id="aa841-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="aa841-350">В результате политика голосовой связи, применяемая к звонкам Андрея Ивана Иванова, имеет неограниченные ограничений и будет следовать логике маршрутизазвонков, доступной для международных и международных звонков в США, Канаде.</span><span class="sxs-lookup"><span data-stu-id="aa841-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa841-351">См. также</span><span class="sxs-lookup"><span data-stu-id="aa841-351">See also</span></span>

[<span data-ttu-id="aa841-352">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="aa841-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="aa841-353">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="aa841-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
