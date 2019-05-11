---
title: Правило версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.
ms.openlocfilehash: 918d32b82a3f4fffddccdccc8ffe9671ad4b8a15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891882"
---
# <a name="client-version-rule"></a><span data-ttu-id="7c721-104">Правило версий клиентов</span><span class="sxs-lookup"><span data-stu-id="7c721-104">Client Version Rule</span></span>

<span data-ttu-id="7c721-p102">Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="7c721-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7c721-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="7c721-107">Tasks you can perform</span></span>

<span data-ttu-id="7c721-108">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="7c721-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="7c721-109">добавить новые правила в политику версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="7c721-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="7c721-110">изменить правила в существующей политике версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="7c721-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7c721-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7c721-111">UI Reference</span></span>

<span data-ttu-id="7c721-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7c721-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="7c721-113">**Агент пользователя** Тип клиента можно выбрать из списка.</span><span class="sxs-lookup"><span data-stu-id="7c721-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="7c721-114">В следующей таблице определяются коды агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c721-114">The following table defines user agent codes.</span></span> <span data-ttu-id="7c721-115">Этот список включает типы устаревшего клиента, некоторые из которых больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7c721-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="7c721-116">**Имя клиента**</span><span class="sxs-lookup"><span data-stu-id="7c721-116">**Client Name**</span></span>|<span data-ttu-id="7c721-117">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="7c721-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c721-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="7c721-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="7c721-119">OC</span><span class="sxs-lookup"><span data-stu-id="7c721-119">OC</span></span>  <br/> |
|<span data-ttu-id="7c721-120">Lync Web App, веб-клиента Communicator</span><span class="sxs-lookup"><span data-stu-id="7c721-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="7c721-121">CWA</span><span class="sxs-lookup"><span data-stu-id="7c721-121">CWA</span></span>  <br/> |
|<span data-ttu-id="7c721-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="7c721-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="7c721-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="7c721-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="7c721-124">Платформа Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7c721-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="7c721-125">CPE</span><span class="sxs-lookup"><span data-stu-id="7c721-125">CPE</span></span>  <br/> |
|<span data-ttu-id="7c721-126">Платформа объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="7c721-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="7c721-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="7c721-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="7c721-128">Участник Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7c721-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="7c721-129">AOC</span><span class="sxs-lookup"><span data-stu-id="7c721-129">AOC</span></span>  <br/> |
|<span data-ttu-id="7c721-130">Надстройка Live Meeting</span><span class="sxs-lookup"><span data-stu-id="7c721-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="7c721-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="7c721-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="7c721-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="7c721-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="7c721-133">LMC</span><span class="sxs-lookup"><span data-stu-id="7c721-133">LMC</span></span>  <br/> |
|<span data-ttu-id="7c721-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="7c721-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="7c721-135">WM</span><span class="sxs-lookup"><span data-stu-id="7c721-135">WM</span></span>  <br/> |
|<span data-ttu-id="7c721-136">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="7c721-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="7c721-137">RTC</span><span class="sxs-lookup"><span data-stu-id="7c721-137">RTC</span></span>  <br/> |
|<span data-ttu-id="7c721-138">Lync 2010 для iPad</span><span class="sxs-lookup"><span data-stu-id="7c721-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="7c721-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="7c721-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="7c721-140">Lync 2010 для iPhone</span><span class="sxs-lookup"><span data-stu-id="7c721-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="7c721-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="7c721-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="7c721-142">Lync 2010 для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7c721-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="7c721-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="7c721-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="7c721-144">Lync 2010 для Nokia</span><span class="sxs-lookup"><span data-stu-id="7c721-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="7c721-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="7c721-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="7c721-146">Lync 2010 для Android (en)</span><span class="sxs-lookup"><span data-stu-id="7c721-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="7c721-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="7c721-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="7c721-148">Mobility service</span><span class="sxs-lookup"><span data-stu-id="7c721-148">Mobility service</span></span>  <br/> |<span data-ttu-id="7c721-149">McxService</span><span class="sxs-lookup"><span data-stu-id="7c721-149">McxService</span></span>  <br/> |

- <span data-ttu-id="7c721-150">**Номер версии** Можно указать номера версий для следующих полей или использовать подстановочные знаки для указания номера версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="7c721-151">**Основной номер версии** Указывает номер, соответствующий основной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="7c721-152">**Дополнительный номер версии** Указывает число, соответствующее вспомогательной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="7c721-153">**Построение** Указывает номер сборки, соответствующий основной и дополнительной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="7c721-154">**Обновление** Указывает число, соответствующее обновленной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="7c721-155">**Операция сравнения** Можно указать операцию сопоставления для версии клиента, указанной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7c721-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="7c721-156">Доступны следующие операции:</span><span class="sxs-lookup"><span data-stu-id="7c721-156">The following operations are available:</span></span>

  - <span data-ttu-id="7c721-157">**Cовпадает с**</span><span class="sxs-lookup"><span data-stu-id="7c721-157">**Same as**</span></span>

  - <span data-ttu-id="7c721-158">**Не является**</span><span class="sxs-lookup"><span data-stu-id="7c721-158">**Is not**</span></span>

  - <span data-ttu-id="7c721-159">**Новее**</span><span class="sxs-lookup"><span data-stu-id="7c721-159">**Newer than**</span></span>

  - <span data-ttu-id="7c721-160">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="7c721-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="7c721-161">**Старше**</span><span class="sxs-lookup"><span data-stu-id="7c721-161">**Older than**</span></span>

  - <span data-ttu-id="7c721-162">**Старше или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="7c721-162">**Older than or same as**</span></span>

- <span data-ttu-id="7c721-163">**Действие** Можно указать действие, выполняемое при выполнении условий на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="7c721-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="7c721-164">Доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7c721-164">The following actions are available:</span></span>

  - <span data-ttu-id="7c721-165">**Разрешить** Разрешает клиенту выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="7c721-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="7c721-166">**Разрешить и обновление** Разрешает клиенту выполнить вход и получать обновления из службы Центра обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7c721-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7c721-167">Это действие доступно только в том случае, если выбран агента пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="7c721-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c721-168">Выбрав это действие вызывает уведомление отображаться Далее время пользователи выполняют вход Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c721-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="7c721-169">Уведомление говорится, что обновление доступно, даже если обновления еще не были предоставлены службы обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7c721-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7c721-170">Чтобы избежать путаницы, следует выбрать это действие только после обновления становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="7c721-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="7c721-171">**Разрешить с URL-адресом** Разрешает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другой версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7c721-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="7c721-172">Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="7c721-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="7c721-173">**Блок** Запрещает клиенту вход в систему.</span><span class="sxs-lookup"><span data-stu-id="7c721-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="7c721-174">**Блокировать и обновление** Запрещает клиенту вход в систему и позволяет клиентским для получения обновлений из службы обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7c721-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7c721-175">Это действие доступно только в том случае, если выбран агента пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="7c721-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="7c721-p110">**Заблокировать с URL-адресом** — запрещает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другую версию клиента. Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="7c721-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="7c721-178">Для получения дополнительных сведений о взаимодействии между клиентами и их версий в документации по планированию показано [Взаимодействие с клиентом](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7c721-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7c721-179">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7c721-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

