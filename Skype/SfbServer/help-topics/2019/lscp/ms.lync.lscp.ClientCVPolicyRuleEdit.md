---
title: Правило версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.
ms.openlocfilehash: 26f37c77886ac9f9fe7fb8d8680fb0dad642a9cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812379"
---
# <a name="client-version-rule"></a><span data-ttu-id="cf145-104">Правило версий клиентов</span><span class="sxs-lookup"><span data-stu-id="cf145-104">Client Version Rule</span></span>

<span data-ttu-id="cf145-p102">Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="cf145-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cf145-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="cf145-107">Tasks you can perform</span></span>

<span data-ttu-id="cf145-108">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="cf145-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="cf145-109">добавить новые правила в политику версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="cf145-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="cf145-110">изменить правила в существующей политике версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="cf145-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cf145-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="cf145-111">UI Reference</span></span>

<span data-ttu-id="cf145-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="cf145-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="cf145-113">**Агент пользователя** В списке можно выбрать тип клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="cf145-114">В следующей таблице определяются коды агентов пользователей.</span><span class="sxs-lookup"><span data-stu-id="cf145-114">The following table defines user agent codes.</span></span> <span data-ttu-id="cf145-115">Этот список включает устаревшие типы клиентов, некоторые из которых больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cf145-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="cf145-116">**Имя клиента**</span><span class="sxs-lookup"><span data-stu-id="cf145-116">**Client Name**</span></span>|<span data-ttu-id="cf145-117">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="cf145-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf145-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="cf145-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="cf145-119">OC</span><span class="sxs-lookup"><span data-stu-id="cf145-119">OC</span></span>  <br/> |
|<span data-ttu-id="cf145-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="cf145-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="cf145-121">CWA</span><span class="sxs-lookup"><span data-stu-id="cf145-121">CWA</span></span>  <br/> |
|<span data-ttu-id="cf145-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="cf145-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="cf145-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="cf145-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="cf145-124">Платформа Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="cf145-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="cf145-125">CPE</span><span class="sxs-lookup"><span data-stu-id="cf145-125">CPE</span></span>  <br/> |
|<span data-ttu-id="cf145-126">Платформа объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="cf145-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="cf145-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="cf145-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="cf145-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="cf145-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="cf145-129">AOC</span><span class="sxs-lookup"><span data-stu-id="cf145-129">AOC</span></span>  <br/> |
|<span data-ttu-id="cf145-130">Надстройка Live Meeting</span><span class="sxs-lookup"><span data-stu-id="cf145-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="cf145-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="cf145-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="cf145-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="cf145-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="cf145-133">LMC</span><span class="sxs-lookup"><span data-stu-id="cf145-133">LMC</span></span>  <br/> |
|<span data-ttu-id="cf145-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="cf145-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="cf145-135">WM</span><span class="sxs-lookup"><span data-stu-id="cf145-135">WM</span></span>  <br/> |
|<span data-ttu-id="cf145-136">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="cf145-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="cf145-137">RTC</span><span class="sxs-lookup"><span data-stu-id="cf145-137">RTC</span></span>  <br/> |
|<span data-ttu-id="cf145-138">Lync 2010 для iPad</span><span class="sxs-lookup"><span data-stu-id="cf145-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="cf145-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="cf145-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="cf145-140">Lync 2010 для iPhone</span><span class="sxs-lookup"><span data-stu-id="cf145-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="cf145-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="cf145-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="cf145-142">Lync 2010 для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cf145-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="cf145-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="cf145-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="cf145-144">Lync 2010 для Nokia</span><span class="sxs-lookup"><span data-stu-id="cf145-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="cf145-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="cf145-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="cf145-146">Lync 2010 для Android</span><span class="sxs-lookup"><span data-stu-id="cf145-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="cf145-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="cf145-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="cf145-148">Mobility service</span><span class="sxs-lookup"><span data-stu-id="cf145-148">Mobility service</span></span>  <br/> |<span data-ttu-id="cf145-149">McxService</span><span class="sxs-lookup"><span data-stu-id="cf145-149">McxService</span></span>  <br/> |

- <span data-ttu-id="cf145-150">**Номер версии** Вы можете указать номера версий для следующих полей или указать номер версии клиента с помощью подмайных обозначений.</span><span class="sxs-lookup"><span data-stu-id="cf145-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="cf145-151">**Основная версия** Указывает номер, соответствующий основной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="cf145-152">**Minor version** Указывает номер, соответствующий незначительному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="cf145-153">**Сборка** Указывает номер сборки, соответствующий основной и второстепенной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="cf145-154">**Обновление** Указывает номер, соответствующий обновленной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="cf145-155">**Операция сравнения** Можно указать операцию совпадения для версии клиента, указанной на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="cf145-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="cf145-156">Доступны следующие операции:</span><span class="sxs-lookup"><span data-stu-id="cf145-156">The following operations are available:</span></span>

  - <span data-ttu-id="cf145-157">**Совпадает с**</span><span class="sxs-lookup"><span data-stu-id="cf145-157">**Same as**</span></span>

  - <span data-ttu-id="cf145-158">**Не является**</span><span class="sxs-lookup"><span data-stu-id="cf145-158">**Is not**</span></span>

  - <span data-ttu-id="cf145-159">**Новее**</span><span class="sxs-lookup"><span data-stu-id="cf145-159">**Newer than**</span></span>

  - <span data-ttu-id="cf145-160">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="cf145-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="cf145-161">**Старее**</span><span class="sxs-lookup"><span data-stu-id="cf145-161">**Older than**</span></span>

  - <span data-ttu-id="cf145-162">**Старее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="cf145-162">**Older than or same as**</span></span>

- <span data-ttu-id="cf145-163">**Действие** Вы можете указать действие, выполняемые при выполнении критериев, которые были выполнены на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="cf145-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="cf145-164">Доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cf145-164">The following actions are available:</span></span>

  - <span data-ttu-id="cf145-165">**Разрешить** Позволяет клиенту войти в систему.</span><span class="sxs-lookup"><span data-stu-id="cf145-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="cf145-166">**Разрешение и обновление** Позволяет клиенту входить в систему и получать обновления из службы Windows Server Update Service или Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="cf145-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="cf145-167">Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="cf145-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf145-168">При выборе этого действия при следующем входе пользователей в Skype для бизнеса появляется уведомление.</span><span class="sxs-lookup"><span data-stu-id="cf145-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="cf145-169">В уведомлении говорится, что обновление доступно, даже если обновления для службы обновления Windows Server или Обновления Майкрософт еще не выпущены.</span><span class="sxs-lookup"><span data-stu-id="cf145-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="cf145-170">Чтобы избежать путаницы, это действие следует выбирать только после того, как обновления станут доступны.</span><span class="sxs-lookup"><span data-stu-id="cf145-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="cf145-171">**Разрешить с URL-адресом** Позволяет клиенту войти в систему и отображает сообщение о том, где скачать другую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="cf145-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="cf145-172">Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="cf145-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="cf145-173">**Block** Не позволяет клиенту войти в систему.</span><span class="sxs-lookup"><span data-stu-id="cf145-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="cf145-174">**Блокировка и обновление** Предотвращает вход в систему и позволяет клиенту получать обновления из службы обновления Windows Server или Обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf145-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="cf145-175">Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="cf145-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="cf145-p110">**Заблокировать с URL-адресом** — запрещает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другую версию клиента. Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="cf145-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="cf145-178">Подробные сведения о взаимосвязи между клиентами [](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) и версиями клиентов см. в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cf145-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="cf145-179">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="cf145-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

