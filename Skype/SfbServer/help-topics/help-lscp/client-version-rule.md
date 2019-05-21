---
title: Правило версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.
ms.openlocfilehash: 6fa3ca3f59756c8a6fedb9fd8f1f457ca3f2df40
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277932"
---
# <a name="client-version-rule"></a><span data-ttu-id="33559-104">Правило версий клиентов</span><span class="sxs-lookup"><span data-stu-id="33559-104">Client Version Rule</span></span>

<span data-ttu-id="33559-p102">Политика версий клиентов состоит из набора правил версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="33559-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="33559-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="33559-107">Tasks you can perform</span></span>

<span data-ttu-id="33559-108">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="33559-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="33559-109">добавить новые правила в политику версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="33559-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="33559-110">изменить правила в существующей политике версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="33559-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="33559-111">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="33559-111">UI Reference</span></span>

<span data-ttu-id="33559-112">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="33559-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="33559-113">**Агент пользователя** Вы можете выбрать тип клиента из списка.</span><span class="sxs-lookup"><span data-stu-id="33559-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="33559-114">В следующей таблице описаны коды агентов пользователя.</span><span class="sxs-lookup"><span data-stu-id="33559-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="33559-115">**Имя клиента**</span><span class="sxs-lookup"><span data-stu-id="33559-115">**Client Name**</span></span>|<span data-ttu-id="33559-116">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="33559-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33559-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="33559-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="33559-118">OC</span><span class="sxs-lookup"><span data-stu-id="33559-118">OC</span></span>  <br/> |
|<span data-ttu-id="33559-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="33559-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="33559-120">CWA</span><span class="sxs-lookup"><span data-stu-id="33559-120">CWA</span></span>  <br/> |
|<span data-ttu-id="33559-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="33559-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="33559-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="33559-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="33559-123">Платформа Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="33559-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="33559-124">CPE</span><span class="sxs-lookup"><span data-stu-id="33559-124">CPE</span></span>  <br/> |
|<span data-ttu-id="33559-125">Платформа объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="33559-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="33559-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="33559-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="33559-127">Участник Lync 2010</span><span class="sxs-lookup"><span data-stu-id="33559-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="33559-128">AOC</span><span class="sxs-lookup"><span data-stu-id="33559-128">AOC</span></span>  <br/> |
|<span data-ttu-id="33559-129">Надстройка Live Meeting</span><span class="sxs-lookup"><span data-stu-id="33559-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="33559-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="33559-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="33559-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="33559-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="33559-132">LMC</span><span class="sxs-lookup"><span data-stu-id="33559-132">LMC</span></span>  <br/> |
|<span data-ttu-id="33559-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="33559-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="33559-134">WM</span><span class="sxs-lookup"><span data-stu-id="33559-134">WM</span></span>  <br/> |
|<span data-ttu-id="33559-135">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="33559-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="33559-136">RTC</span><span class="sxs-lookup"><span data-stu-id="33559-136">RTC</span></span>  <br/> |
|<span data-ttu-id="33559-137">Lync 2010 для iPad</span><span class="sxs-lookup"><span data-stu-id="33559-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="33559-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="33559-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="33559-139">Lync 2010 для iPhone</span><span class="sxs-lookup"><span data-stu-id="33559-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="33559-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="33559-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="33559-141">Lync 2010 для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="33559-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="33559-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="33559-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="33559-143">Lync 2010 для Nokia</span><span class="sxs-lookup"><span data-stu-id="33559-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="33559-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="33559-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="33559-145">Lync 2010 для Android</span><span class="sxs-lookup"><span data-stu-id="33559-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="33559-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="33559-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="33559-147">Mobility service</span><span class="sxs-lookup"><span data-stu-id="33559-147">Mobility service</span></span>  <br/> |<span data-ttu-id="33559-148">McxService</span><span class="sxs-lookup"><span data-stu-id="33559-148">McxService</span></span>  <br/> |

- <span data-ttu-id="33559-149">**Номер версии** Вы можете указать номера версий для указанных ниже полей или использовать подстановочные знаки, чтобы указать номер версии клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="33559-150">**Основная версия** Указывает номер, соответствующий главному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="33559-151">**Вспомогательная версия** Указывает номер, соответствующий вспомогательному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="33559-152">**Сборка** Задает номер сборки, соответствующий основной и вспомогательной выпуске клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="33559-153">**Обновление** Указывает номер, соответствующий обновленному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="33559-154">**Операция сравнения** Вы можете указать подходящую операцию для клиентской версии, которая указана в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="33559-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="33559-155">Доступны следующие операции:</span><span class="sxs-lookup"><span data-stu-id="33559-155">The following operations are available:</span></span>

  - <span data-ttu-id="33559-156">**Cовпадает с**</span><span class="sxs-lookup"><span data-stu-id="33559-156">**Same as**</span></span>

  - <span data-ttu-id="33559-157">**Не является**</span><span class="sxs-lookup"><span data-stu-id="33559-157">**Is not**</span></span>

  - <span data-ttu-id="33559-158">**Новее**</span><span class="sxs-lookup"><span data-stu-id="33559-158">**Newer than**</span></span>

  - <span data-ttu-id="33559-159">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="33559-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="33559-160">**Старше**</span><span class="sxs-lookup"><span data-stu-id="33559-160">**Older than**</span></span>

  - <span data-ttu-id="33559-161">**Старше или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="33559-161">**Older than or same as**</span></span>

- <span data-ttu-id="33559-162">**Действие** Вы можете указать действие, которое будет выполняться при выполнении условий, описанных в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="33559-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="33559-163">Доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33559-163">The following actions are available:</span></span>

  - <span data-ttu-id="33559-164">**Разрешение** Позволяет клиенту войти в систему.</span><span class="sxs-lookup"><span data-stu-id="33559-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="33559-165">**Разрешение и обновление** Позволяет клиенту входить в систему и получать обновления из службы обновления Windows Server Update Service или центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33559-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="33559-166">Это действие доступно только в том случае, если выбран агент пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="33559-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33559-167">При выборе этого действия уведомление появляется при следующем входе в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="33559-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="33559-168">В уведомлении говорится, что обновление доступно, даже если они еще не были выпущены в службе обновления Windows Server или Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="33559-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="33559-169">Чтобы избежать путаницы, выбирайте это действие только после того, как обновления станут доступны.</span><span class="sxs-lookup"><span data-stu-id="33559-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="33559-170">**Разрешить с URL-адресом** Позволяет клиенту входить в систему и выводит сообщение о том, куда загрузить другую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="33559-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="33559-171">Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="33559-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="33559-172">**Блокировать** Запрещает клиенту входить в систему.</span><span class="sxs-lookup"><span data-stu-id="33559-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="33559-173">**Блокировка и обновление** Запрещает клиенту входить в систему и позволяет клиенту получать обновления из службы Windows Server Update Service или центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33559-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="33559-174">Это действие доступно только в том случае, если выбран агент пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="33559-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="33559-p110">**Заблокировать с URL-адресом** — запрещает клиенту выполнить вход и отображает сообщение о том, где можно загрузить другую версию клиента. Соответствующий URL-адрес указывается в поле **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="33559-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="33559-p111">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) документации по планированию. Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="33559-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

