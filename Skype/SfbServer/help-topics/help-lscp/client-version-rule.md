---
title: Правило версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.
ms.openlocfilehash: 14e9c0d14ce988ec89d8bb13410272c4734ae882
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829499"
---
# <a name="client-version-rule"></a><span data-ttu-id="b2f05-104">Правило версий клиентов</span><span class="sxs-lookup"><span data-stu-id="b2f05-104">Client Version Rule</span></span>

<span data-ttu-id="b2f05-p102">Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="b2f05-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b2f05-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="b2f05-107">Tasks you can perform</span></span>

<span data-ttu-id="b2f05-108">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="b2f05-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="b2f05-109">добавить новые правила в политику версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="b2f05-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="b2f05-110">изменить правила в существующей политике версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="b2f05-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b2f05-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="b2f05-111">UI Reference</span></span>

<span data-ttu-id="b2f05-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b2f05-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="b2f05-113">**Агент пользователя** В списке можно выбрать тип клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="b2f05-114">В следующей таблице определяются коды агентов пользователя.</span><span class="sxs-lookup"><span data-stu-id="b2f05-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="b2f05-115">**Имя клиента**</span><span class="sxs-lookup"><span data-stu-id="b2f05-115">**Client Name**</span></span>|<span data-ttu-id="b2f05-116">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="b2f05-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2f05-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="b2f05-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="b2f05-118">OC</span><span class="sxs-lookup"><span data-stu-id="b2f05-118">OC</span></span>  <br/> |
|<span data-ttu-id="b2f05-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="b2f05-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="b2f05-120">CWA</span><span class="sxs-lookup"><span data-stu-id="b2f05-120">CWA</span></span>  <br/> |
|<span data-ttu-id="b2f05-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="b2f05-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="b2f05-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="b2f05-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="b2f05-123">Платформа Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b2f05-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="b2f05-124">CPE</span><span class="sxs-lookup"><span data-stu-id="b2f05-124">CPE</span></span>  <br/> |
|<span data-ttu-id="b2f05-125">Платформа объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="b2f05-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="b2f05-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="b2f05-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="b2f05-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="b2f05-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="b2f05-128">AOC</span><span class="sxs-lookup"><span data-stu-id="b2f05-128">AOC</span></span>  <br/> |
|<span data-ttu-id="b2f05-129">Надстройка Live Meeting</span><span class="sxs-lookup"><span data-stu-id="b2f05-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="b2f05-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="b2f05-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="b2f05-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="b2f05-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="b2f05-132">LMC</span><span class="sxs-lookup"><span data-stu-id="b2f05-132">LMC</span></span>  <br/> |
|<span data-ttu-id="b2f05-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="b2f05-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="b2f05-134">WM</span><span class="sxs-lookup"><span data-stu-id="b2f05-134">WM</span></span>  <br/> |
|<span data-ttu-id="b2f05-135">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="b2f05-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="b2f05-136">RTC</span><span class="sxs-lookup"><span data-stu-id="b2f05-136">RTC</span></span>  <br/> |
|<span data-ttu-id="b2f05-137">Lync 2010 для iPad</span><span class="sxs-lookup"><span data-stu-id="b2f05-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="b2f05-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="b2f05-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="b2f05-139">Lync 2010 для iPhone</span><span class="sxs-lookup"><span data-stu-id="b2f05-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="b2f05-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="b2f05-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="b2f05-141">Lync 2010 для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b2f05-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="b2f05-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="b2f05-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="b2f05-143">Lync 2010 для Nokia</span><span class="sxs-lookup"><span data-stu-id="b2f05-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="b2f05-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="b2f05-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="b2f05-145">Lync 2010 для Android</span><span class="sxs-lookup"><span data-stu-id="b2f05-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="b2f05-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="b2f05-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="b2f05-147">Mobility service</span><span class="sxs-lookup"><span data-stu-id="b2f05-147">Mobility service</span></span>  <br/> |<span data-ttu-id="b2f05-148">McxService</span><span class="sxs-lookup"><span data-stu-id="b2f05-148">McxService</span></span>  <br/> |

- <span data-ttu-id="b2f05-149">**Номер версии** Вы можете указать номера версий для следующих полей или указать номер версии клиента с помощью подмайных обозначений.</span><span class="sxs-lookup"><span data-stu-id="b2f05-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="b2f05-150">**Основная версия** Указывает номер, соответствующий основной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="b2f05-151">**Minor version** Указывает номер, соответствующий незначительному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="b2f05-152">**Сборка** Указывает номер сборки, соответствующий основной и второстепенной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="b2f05-153">**Обновление** Указывает номер, соответствующий обновленной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="b2f05-154">**Операция сравнения** Можно указать операцию совпадения для версии клиента, указанной на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="b2f05-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="b2f05-155">Доступны следующие операции:</span><span class="sxs-lookup"><span data-stu-id="b2f05-155">The following operations are available:</span></span>

  - <span data-ttu-id="b2f05-156">**Совпадает с**</span><span class="sxs-lookup"><span data-stu-id="b2f05-156">**Same as**</span></span>

  - <span data-ttu-id="b2f05-157">**Не является**</span><span class="sxs-lookup"><span data-stu-id="b2f05-157">**Is not**</span></span>

  - <span data-ttu-id="b2f05-158">**Новее**</span><span class="sxs-lookup"><span data-stu-id="b2f05-158">**Newer than**</span></span>

  - <span data-ttu-id="b2f05-159">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="b2f05-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="b2f05-160">**Старее**</span><span class="sxs-lookup"><span data-stu-id="b2f05-160">**Older than**</span></span>

  - <span data-ttu-id="b2f05-161">**Старее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="b2f05-161">**Older than or same as**</span></span>

- <span data-ttu-id="b2f05-162">**Действие** Вы можете указать действие, выполняемые при выполнении критериев, которые были выполнены на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="b2f05-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="b2f05-163">Доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b2f05-163">The following actions are available:</span></span>

  - <span data-ttu-id="b2f05-164">**Разрешить** Позволяет клиенту войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b2f05-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="b2f05-165">**Разрешение и обновление** Позволяет клиенту входить в систему и получать обновления из службы Обновления Windows Server или Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="b2f05-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="b2f05-166">Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="b2f05-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2f05-167">При выборе этого действия при следующем входе пользователей в Skype для бизнеса появляется уведомление.</span><span class="sxs-lookup"><span data-stu-id="b2f05-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="b2f05-168">В уведомлении говорится, что обновление доступно, даже если обновления для службы обновления Windows Server или Обновления Майкрософт еще не выпущены.</span><span class="sxs-lookup"><span data-stu-id="b2f05-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="b2f05-169">Чтобы избежать путаницы, это действие следует выбирать только после того, как обновления станут доступны.</span><span class="sxs-lookup"><span data-stu-id="b2f05-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="b2f05-170">**Разрешить с URL-адресом** Позволяет клиенту войти в систему и отображает сообщение о том, где скачать другую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="b2f05-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="b2f05-171">Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="b2f05-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="b2f05-172">**Block** Не позволяет клиенту войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b2f05-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="b2f05-173">**Блокировка и обновление** Предотвращает вход в систему и позволяет клиенту получать обновления из службы обновления Windows Server или Обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2f05-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="b2f05-174">Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="b2f05-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="b2f05-p110">**Заблокировать с URL-адресом** — запрещает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другую версию клиента. Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="b2f05-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="b2f05-177">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b2f05-177">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b2f05-178">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="b2f05-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

