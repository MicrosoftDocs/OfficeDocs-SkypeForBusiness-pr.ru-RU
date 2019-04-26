---
title: Правило версий клиентов
ms.reviewer: ''
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.
ms.openlocfilehash: c70d831d88948bd50f14b9591807e2ce1f36611a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234730"
---
# <a name="client-version-rule"></a><span data-ttu-id="ebaab-104">Правило версий клиентов</span><span class="sxs-lookup"><span data-stu-id="ebaab-104">Client Version Rule</span></span>

<span data-ttu-id="ebaab-p102">Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="ebaab-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ebaab-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="ebaab-107">Tasks you can perform</span></span>

<span data-ttu-id="ebaab-108">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="ebaab-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="ebaab-109">добавить новые правила в политику версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="ebaab-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="ebaab-110">изменить правила в существующей политике версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ebaab-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ebaab-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="ebaab-111">UI Reference</span></span>

<span data-ttu-id="ebaab-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ebaab-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="ebaab-113">**Агент пользователя** Тип клиента можно выбрать из списка.</span><span class="sxs-lookup"><span data-stu-id="ebaab-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="ebaab-114">В следующей таблице определяются коды агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ebaab-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="ebaab-115">**Имя клиента**</span><span class="sxs-lookup"><span data-stu-id="ebaab-115">**Client Name**</span></span>|<span data-ttu-id="ebaab-116">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="ebaab-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebaab-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="ebaab-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="ebaab-118">OC</span><span class="sxs-lookup"><span data-stu-id="ebaab-118">OC</span></span>  <br/> |
|<span data-ttu-id="ebaab-119">Lync Web App, веб-клиента Communicator</span><span class="sxs-lookup"><span data-stu-id="ebaab-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="ebaab-120">CWA</span><span class="sxs-lookup"><span data-stu-id="ebaab-120">CWA</span></span>  <br/> |
|<span data-ttu-id="ebaab-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="ebaab-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="ebaab-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ebaab-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="ebaab-123">Платформа Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ebaab-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="ebaab-124">CPE</span><span class="sxs-lookup"><span data-stu-id="ebaab-124">CPE</span></span>  <br/> |
|<span data-ttu-id="ebaab-125">Платформа объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="ebaab-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="ebaab-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="ebaab-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="ebaab-127">Участник Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebaab-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="ebaab-128">AOC</span><span class="sxs-lookup"><span data-stu-id="ebaab-128">AOC</span></span>  <br/> |
|<span data-ttu-id="ebaab-129">Надстройка Live Meeting</span><span class="sxs-lookup"><span data-stu-id="ebaab-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="ebaab-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="ebaab-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="ebaab-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="ebaab-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="ebaab-132">LMC</span><span class="sxs-lookup"><span data-stu-id="ebaab-132">LMC</span></span>  <br/> |
|<span data-ttu-id="ebaab-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="ebaab-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="ebaab-134">WM</span><span class="sxs-lookup"><span data-stu-id="ebaab-134">WM</span></span>  <br/> |
|<span data-ttu-id="ebaab-135">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="ebaab-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="ebaab-136">RTC</span><span class="sxs-lookup"><span data-stu-id="ebaab-136">RTC</span></span>  <br/> |
|<span data-ttu-id="ebaab-137">Lync 2010 для iPad</span><span class="sxs-lookup"><span data-stu-id="ebaab-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="ebaab-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ebaab-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="ebaab-139">Lync 2010 для iPhone</span><span class="sxs-lookup"><span data-stu-id="ebaab-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="ebaab-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ebaab-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="ebaab-141">Lync 2010 для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ebaab-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="ebaab-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="ebaab-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="ebaab-143">Lync 2010 для Nokia</span><span class="sxs-lookup"><span data-stu-id="ebaab-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="ebaab-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ebaab-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="ebaab-145">Lync 2010 для Android (en)</span><span class="sxs-lookup"><span data-stu-id="ebaab-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="ebaab-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ebaab-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="ebaab-147">Mobility service</span><span class="sxs-lookup"><span data-stu-id="ebaab-147">Mobility service</span></span>  <br/> |<span data-ttu-id="ebaab-148">McxService</span><span class="sxs-lookup"><span data-stu-id="ebaab-148">McxService</span></span>  <br/> |

- <span data-ttu-id="ebaab-149">**Номер версии** Можно указать номера версий для следующих полей или использовать подстановочные знаки для указания номера версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="ebaab-150">**Основной номер версии** Указывает номер, соответствующий основной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="ebaab-151">**Дополнительный номер версии** Указывает число, соответствующее вспомогательной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="ebaab-152">**Построение** Указывает номер сборки, соответствующий основной и дополнительной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="ebaab-153">**Обновление** Указывает число, соответствующее обновленной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="ebaab-154">**Операция сравнения** Можно указать операцию сопоставления для версии клиента, указанной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="ebaab-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="ebaab-155">Доступны следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ebaab-155">The following operations are available:</span></span>

  - <span data-ttu-id="ebaab-156">**Cовпадает с**</span><span class="sxs-lookup"><span data-stu-id="ebaab-156">**Same as**</span></span>

  - <span data-ttu-id="ebaab-157">**Не является**</span><span class="sxs-lookup"><span data-stu-id="ebaab-157">**Is not**</span></span>

  - <span data-ttu-id="ebaab-158">**Новее**</span><span class="sxs-lookup"><span data-stu-id="ebaab-158">**Newer than**</span></span>

  - <span data-ttu-id="ebaab-159">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="ebaab-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="ebaab-160">**Старше**</span><span class="sxs-lookup"><span data-stu-id="ebaab-160">**Older than**</span></span>

  - <span data-ttu-id="ebaab-161">**Старше или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="ebaab-161">**Older than or same as**</span></span>

- <span data-ttu-id="ebaab-162">**Действие** Можно указать действие, выполняемое при выполнении условий на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="ebaab-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="ebaab-163">Доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ebaab-163">The following actions are available:</span></span>

  - <span data-ttu-id="ebaab-164">**Разрешить** Разрешает клиенту выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="ebaab-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="ebaab-165">**Разрешить и обновление** Разрешает клиенту выполнить вход и получать обновления из службы Центра обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ebaab-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebaab-166">Это действие доступно только в том случае, если выбран агента пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="ebaab-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebaab-167">Выбрав это действие вызывает уведомление отображаться Далее время пользователи выполняют вход Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ebaab-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="ebaab-168">Уведомление говорится, что обновление доступно, даже если обновления еще не были предоставлены службы обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ebaab-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebaab-169">Чтобы избежать путаницы, следует выбрать это действие только после обновления становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="ebaab-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="ebaab-170">**Разрешить с URL-адресом** Разрешает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другой версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ebaab-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="ebaab-171">Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="ebaab-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="ebaab-172">**Блок** Запрещает клиенту вход в систему.</span><span class="sxs-lookup"><span data-stu-id="ebaab-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="ebaab-173">**Блокировать и обновление** Запрещает клиенту вход в систему и позволяет клиентским для получения обновлений из службы обновления Windows Server или Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ebaab-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebaab-174">Это действие доступно только в том случае, если выбран агента пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="ebaab-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="ebaab-p110">**Заблокировать с URL-адресом** — запрещает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другую версию клиента. Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="ebaab-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="ebaab-p111">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) документации по планированию. Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="ebaab-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

