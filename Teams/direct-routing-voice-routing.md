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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158011"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="703f5-103">Настройка маршрутизации голосовой связи для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="703f5-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="703f5-104">В этой статье описано, как настроить маршрутизацию голосовой связи для прямой маршрутизации телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="703f5-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="703f5-105">Это действие 3 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="703f5-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="703f5-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="703f5-106">Step 1.</span></span> [<span data-ttu-id="703f5-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="703f5-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="703f5-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="703f5-108">Step 2.</span></span> [<span data-ttu-id="703f5-109">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="703f5-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="703f5-110">**Шаг 3. Настройка голосовой маршрутизации** (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="703f5-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="703f5-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="703f5-111">Step 4.</span></span> [<span data-ttu-id="703f5-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="703f5-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="703f5-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="703f5-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="703f5-114">Общие сведения о маршрутизации голосовой почты</span><span class="sxs-lookup"><span data-stu-id="703f5-114">Voice routing overview</span></span>

<span data-ttu-id="703f5-115">В телефонной системе Microsoft есть механизм маршрутизации, позволяющий отправлять звонки на определенный контроллер границ сеанса (SBC), основанный на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="703f5-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="703f5-116">Вызываемый шаблон номера</span><span class="sxs-lookup"><span data-stu-id="703f5-116">The called number pattern</span></span> 
- <span data-ttu-id="703f5-117">Вызываемый шаблон номера и конкретный пользователь, который совершает звонок;</span><span class="sxs-lookup"><span data-stu-id="703f5-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="703f5-118">SBCs можно назначить активными и архивировать.</span><span class="sxs-lookup"><span data-stu-id="703f5-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="703f5-119">Если объект SBC, настроенный как активный, недоступен для определенного маршрута вызова, этот звонок будет перенаправлен на одноэлементный объект SBC.</span><span class="sxs-lookup"><span data-stu-id="703f5-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="703f5-120">Маршрутизация голосовой связи состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="703f5-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="703f5-121">**Политика маршрутизации голосовой связи** — контейнер использования PSTN, который можно назначить пользователю или нескольким пользователям.</span><span class="sxs-lookup"><span data-stu-id="703f5-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="703f5-122">**Использование PSTN** — контейнер для голосовых маршрутов и использование PSTN, которые можно использовать в разных политиках голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="703f5-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="703f5-123">**Голосовые маршруты** — шаблон номера и набор сетевых шлюзов, используемых для звонков, где номер звонка соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="703f5-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="703f5-124">**Сетевой шлюз PSTN** — указатель на объект SBC, который также хранит конфигурацию, которая применяется при размещении вызова через SBC, например переадресация (паи) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты.</span><span class="sxs-lookup"><span data-stu-id="703f5-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="703f5-125">Пример 1: Маршрутизация голосовой связи с использованием одной PSTN</span><span class="sxs-lookup"><span data-stu-id="703f5-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="703f5-126">На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке звонков.</span><span class="sxs-lookup"><span data-stu-id="703f5-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="703f5-127">**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="703f5-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="703f5-128">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="703f5-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="703f5-129">**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="703f5-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="703f5-130">Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="703f5-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="703f5-131">Если ни одна из этих SBCs недоступна, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="703f5-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="703f5-133">В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="703f5-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="703f5-134">Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются.</span><span class="sxs-lookup"><span data-stu-id="703f5-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="703f5-135">Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="703f5-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="703f5-136">План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="703f5-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="703f5-137">В примере, показанном на приведенной ниже схеме, маршрут голосовой связи добавляется для отправки звонков на все остальные номера США и Канады (звонки, находящиеся под названием "шаблон номера" + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="703f5-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="703f5-139">Для всех остальных звонков:</span><span class="sxs-lookup"><span data-stu-id="703f5-139">For all other calls:</span></span>

- <span data-ttu-id="703f5-140">Если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="703f5-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="703f5-141">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, этот звонок направляется через план звонков по Microsoft.</span><span class="sxs-lookup"><span data-stu-id="703f5-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="703f5-142">Если у пользователя есть только телефонная система Microsoft, вызов отбрасывается из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="703f5-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="703f5-143">Значение приоритета для маршрута "Other + 1" не имеет значения в этом случае, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="703f5-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="703f5-144">Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="703f5-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="703f5-145">В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="703f5-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="703f5-146">В этом примере все три маршрута являются частью одного и того же использования КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="703f5-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="703f5-147">Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только США".</span><span class="sxs-lookup"><span data-stu-id="703f5-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="703f5-148">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="703f5-148">**PSTN usage**</span></span>|<span data-ttu-id="703f5-149">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="703f5-149">**Voice route**</span></span>|<span data-ttu-id="703f5-150">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="703f5-150">**Number pattern**</span></span>|<span data-ttu-id="703f5-151">**Priority**</span><span class="sxs-lookup"><span data-stu-id="703f5-151">**Priority**</span></span>|<span data-ttu-id="703f5-152">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="703f5-152">**SBC**</span></span>|<span data-ttu-id="703f5-153">**Описание**</span><span class="sxs-lookup"><span data-stu-id="703f5-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="703f5-154">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-154">US only</span></span>|<span data-ttu-id="703f5-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="703f5-155">"Redmond 1"</span></span>|<span data-ttu-id="703f5-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="703f5-157">1</span><span class="sxs-lookup"><span data-stu-id="703f5-157">1</span></span>|<span data-ttu-id="703f5-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="703f5-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="703f5-160">Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="703f5-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="703f5-161">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-161">US only</span></span>|<span data-ttu-id="703f5-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="703f5-162">"Redmond 2"</span></span>|<span data-ttu-id="703f5-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="703f5-164">2</span><span class="sxs-lookup"><span data-stu-id="703f5-164">2</span></span>|<span data-ttu-id="703f5-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="703f5-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="703f5-167">Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="703f5-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="703f5-168">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-168">US only</span></span>|<span data-ttu-id="703f5-169">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="703f5-169">"Other +1"</span></span>|<span data-ttu-id="703f5-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="703f5-171">3</span><span class="sxs-lookup"><span data-stu-id="703f5-171">3</span></span>|<span data-ttu-id="703f5-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="703f5-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="703f5-174">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="703f5-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="703f5-175">Пример 1: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="703f5-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="703f5-176">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="703f5-176">The following example shows how to:</span></span>

- <span data-ttu-id="703f5-177">Создание единственной использование PSTN</span><span class="sxs-lookup"><span data-stu-id="703f5-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="703f5-178">Настройка трех голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="703f5-178">Configure three voice routes</span></span>
- <span data-ttu-id="703f5-179">Создание политики голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="703f5-179">Create a voice routing policy</span></span>
- <span data-ttu-id="703f5-180">Назначение политики для пользователя Спенцер низкий</span><span class="sxs-lookup"><span data-stu-id="703f5-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="703f5-181">**Действие 1:** Создание использования PSTN "США и Канада"</span><span class="sxs-lookup"><span data-stu-id="703f5-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="703f5-182">В удаленном сеансе PowerShell в Skype для бизнеса введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="703f5-183">Убедитесь в том, что использование было создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="703f5-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="703f5-184">Возвращающий список имен, которые могут быть усечены:</span><span class="sxs-lookup"><span data-stu-id="703f5-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="703f5-185">В приведенном ниже примере показан результат выполнения команды `(Get-CSOnlinePSTNUsage).usage` PowerShell для отображения полных имен (не усеченных):</span><span class="sxs-lookup"><span data-stu-id="703f5-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="703f5-186">**Шаг 2.** В сеансе PowerShell в Skype для бизнеса Online создайте три маршрута: Redmond 1, Redmond 2 и другие + 1, как показано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="703f5-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="703f5-187">Чтобы создать маршрут "Redmond 1", введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="703f5-188">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="703f5-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="703f5-189">Чтобы создать маршрут на 2 Redmond, введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="703f5-190">Чтобы создать другой маршрут + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="703f5-191">Убедитесь, что регулярное выражение в атрибуте Нумберпаттерн является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="703f5-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="703f5-192">Вы можете протестировать его с помощью этого веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="703f5-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="703f5-193">В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Используйте-Нумберпаттерн ". \*"</span><span class="sxs-lookup"><span data-stu-id="703f5-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="703f5-194">Перенаправлять все вызовы в один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="703f5-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="703f5-195">Проверьте, правильно ли вы настроили маршрут, выполнив команду `Get-CSOnlineVoiceRoute` PowerShell, используя указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="703f5-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="703f5-196">Что должно вернуть:</span><span class="sxs-lookup"><span data-stu-id="703f5-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="703f5-197">В примере для маршрута "Other + 1" автоматически назначается приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="703f5-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="703f5-198">**Шаг 3.** Создайте политику голосовой маршрутизации "только США" и добавьте в политику использование КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="703f5-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="703f5-199">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="703f5-200">Результат показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="703f5-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="703f5-201">**Шаг 4:** С помощью PowerShell вы можете предоставить пользователю политику маршрутизации голосовой связи Спенцер низкий:</span><span class="sxs-lookup"><span data-stu-id="703f5-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="703f5-202">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="703f5-203">Чтобы проверить назначение политики, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="703f5-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="703f5-204">Команда возвращает следующее:</span><span class="sxs-lookup"><span data-stu-id="703f5-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="703f5-205">Пример 2: Маршрутизация голосовой связи с несколькими использованием PSTN</span><span class="sxs-lookup"><span data-stu-id="703f5-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="703f5-206">Политика маршрутизации голосовой связи, созданная в примере 1, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).</span><span class="sxs-lookup"><span data-stu-id="703f5-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="703f5-207">В приведенном ниже примере вы можете создать политику маршрутизации голосовой связи "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="703f5-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="703f5-208">Политика повторно использует использование КТСОП "США и Канада", созданное в примере 1, а также новую использование PSTN "Международная".</span><span class="sxs-lookup"><span data-stu-id="703f5-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="703f5-209">Эта политика маршрутизирует все другие вызовы на SBCs sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="703f5-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="703f5-210">Приведенные примеры применяют политику "только для США" для пользователей Спенцер Low и политики "нет ограничений" для пользователя Джон лесу таким образом, чтобы маршрутизация была показана ниже.</span><span class="sxs-lookup"><span data-stu-id="703f5-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="703f5-211">Спенцер низкий – только политика США.</span><span class="sxs-lookup"><span data-stu-id="703f5-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="703f5-212">Звонки разрешены только в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="703f5-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="703f5-213">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="703f5-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="703f5-214">Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="703f5-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="703f5-215">Джон лесу – Международная политика.</span><span class="sxs-lookup"><span data-stu-id="703f5-215">John Woods – International policy.</span></span>  <span data-ttu-id="703f5-216">Звонки разрешены любому числу.</span><span class="sxs-lookup"><span data-stu-id="703f5-216">Calls are allowed to any number.</span></span> <span data-ttu-id="703f5-217">При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs.</span><span class="sxs-lookup"><span data-stu-id="703f5-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="703f5-218">Номера, не относящиеся к США, будут маршрутизироваться с помощью sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="703f5-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю Спенцер низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="703f5-220">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="703f5-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="703f5-221">Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, вызов осуществляется с помощью плана звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="703f5-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="703f5-222">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="703f5-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="703f5-224">В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="703f5-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="703f5-225">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="703f5-225">**PSTN usage**</span></span>|<span data-ttu-id="703f5-226">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="703f5-226">**Voice route**</span></span>|<span data-ttu-id="703f5-227">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="703f5-227">**Number pattern**</span></span>|<span data-ttu-id="703f5-228">**Priority**</span><span class="sxs-lookup"><span data-stu-id="703f5-228">**Priority**</span></span>|<span data-ttu-id="703f5-229">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="703f5-229">**SBC**</span></span>|<span data-ttu-id="703f5-230">**Описание**</span><span class="sxs-lookup"><span data-stu-id="703f5-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="703f5-231">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-231">US Only</span></span>|<span data-ttu-id="703f5-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="703f5-232">"Redmond 1"</span></span>|<span data-ttu-id="703f5-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="703f5-234">1</span><span class="sxs-lookup"><span data-stu-id="703f5-234">1</span></span>|<span data-ttu-id="703f5-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="703f5-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="703f5-237">Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="703f5-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="703f5-238">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-238">US Only</span></span>|<span data-ttu-id="703f5-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="703f5-239">"Redmond 2"</span></span>|<span data-ttu-id="703f5-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="703f5-241">2</span><span class="sxs-lookup"><span data-stu-id="703f5-241">2</span></span>|<span data-ttu-id="703f5-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="703f5-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="703f5-244">Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="703f5-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="703f5-245">Только для США</span><span class="sxs-lookup"><span data-stu-id="703f5-245">US Only</span></span>|<span data-ttu-id="703f5-246">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="703f5-246">"Other +1"</span></span>|<span data-ttu-id="703f5-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="703f5-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="703f5-248">3</span><span class="sxs-lookup"><span data-stu-id="703f5-248">3</span></span>|<span data-ttu-id="703f5-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="703f5-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="703f5-251">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="703f5-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="703f5-252">International</span><span class="sxs-lookup"><span data-stu-id="703f5-252">International</span></span>|<span data-ttu-id="703f5-253">International</span><span class="sxs-lookup"><span data-stu-id="703f5-253">International</span></span>|<span data-ttu-id="703f5-254">\d +</span><span class="sxs-lookup"><span data-stu-id="703f5-254">\d+</span></span>|<span data-ttu-id="703f5-255">4</span><span class="sxs-lookup"><span data-stu-id="703f5-255">4</span></span>|<span data-ttu-id="703f5-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="703f5-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="703f5-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="703f5-258">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="703f5-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="703f5-259">Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен.</span><span class="sxs-lookup"><span data-stu-id="703f5-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="703f5-260">Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="703f5-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="703f5-261">Использование КТСОП "Международная" должно быть размещено после использования КТСОП "только США".</span><span class="sxs-lookup"><span data-stu-id="703f5-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="703f5-262">Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="703f5-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="703f5-263">Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="703f5-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="703f5-264">Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="703f5-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="703f5-265">Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="703f5-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="703f5-266">Пример 2: этапы настройки</span><span class="sxs-lookup"><span data-stu-id="703f5-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="703f5-267">В следующем примере показано, как выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="703f5-267">The following example shows how to:</span></span>

- <span data-ttu-id="703f5-268">Создание нового использования PSTN, называемого международным</span><span class="sxs-lookup"><span data-stu-id="703f5-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="703f5-269">Создать новый голосовой маршрут с именем International</span><span class="sxs-lookup"><span data-stu-id="703f5-269">Create a new voice route called International</span></span>
- <span data-ttu-id="703f5-270">Создание политики голосовой маршрутизации с именем "нет ограничений"</span><span class="sxs-lookup"><span data-stu-id="703f5-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="703f5-271">Назначение политики пользователю John лесу</span><span class="sxs-lookup"><span data-stu-id="703f5-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="703f5-272">**Действие 1**: Создайте использование КТСОП "Международная".</span><span class="sxs-lookup"><span data-stu-id="703f5-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="703f5-273">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="703f5-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="703f5-274">**Действие 2**: Создайте новый голосовой маршрут "Международная".</span><span class="sxs-lookup"><span data-stu-id="703f5-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="703f5-275">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="703f5-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="703f5-276">**Шаг 3**: Создание политики маршрутизации голосовой связи "без ограничений".</span><span class="sxs-lookup"><span data-stu-id="703f5-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="703f5-277">Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="703f5-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="703f5-278">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="703f5-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="703f5-279">a)</span><span class="sxs-lookup"><span data-stu-id="703f5-279">a.</span></span> <span data-ttu-id="703f5-280">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, вызов проходит по маршруту, заданному в разделе "США и Канада", и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="703f5-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="703f5-281">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="703f5-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="703f5-282">б)</span><span class="sxs-lookup"><span data-stu-id="703f5-282">b.</span></span> <span data-ttu-id="703f5-283">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="703f5-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="703f5-284">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="703f5-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="703f5-285">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="703f5-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="703f5-286">**Действие 4**: назначьте политику маршрутизации голосовой связи пользователю John лесу с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="703f5-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="703f5-287">Затем проверьте назначение с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="703f5-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="703f5-288">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="703f5-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="703f5-289">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="703f5-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="703f5-290">См. также</span><span class="sxs-lookup"><span data-stu-id="703f5-290">See also</span></span>

[<span data-ttu-id="703f5-291">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="703f5-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="703f5-292">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="703f5-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
