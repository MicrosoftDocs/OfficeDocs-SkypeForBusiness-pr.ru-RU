---
title: Настройка делегирования в Skype для бизнеса Online и устранение неполадок
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: В этой статье объясняется, как настроить и устранить неполадки, связанные с делегированием Skype для бизнеса Online. В этой статье приводятся инструкции по настройке, рекомендации и инструкции по устранению неполадок.
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285247"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="cba7f-104">Настройка делегирования в Skype для бизнеса Online и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="cba7f-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="cba7f-105">В этой статье объясняется, как настроить и устранить неполадки, связанные с делегированием Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="cba7f-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="cba7f-106">В этой статье приводятся инструкции по настройке, рекомендации и инструкции по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="cba7f-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="cba7f-107">Рекомендации и требования</span><span class="sxs-lookup"><span data-stu-id="cba7f-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="cba7f-108">Рекомендации для делегирования</span><span class="sxs-lookup"><span data-stu-id="cba7f-108">Guidelines for delegation</span></span>

<span data-ttu-id="cba7f-109">Настройка и обеспечение правильной работы делегирования зависят от указанных ниже правил.</span><span class="sxs-lookup"><span data-stu-id="cba7f-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="cba7f-110">Вы должны использовать полную версию клиента Skype для бизнеса 2015 с последними обновлениями или полноценным клиентом Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="cba7f-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="cba7f-111">Необходимо использовать клиент Outlook 2013 с последними обновлениями или клиентом Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="cba7f-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="cba7f-112">Убедитесь в том, что представитель и делегаты компьютеров имеют один профиль электронной почты Outlook, который является основным или профилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cba7f-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="cba7f-113">Этот почтовый профиль должен содержать только одну учетную запись.</span><span class="sxs-lookup"><span data-stu-id="cba7f-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="cba7f-114">Skype для бизнеса для представителя и делегат должны быть пользователями сети.</span><span class="sxs-lookup"><span data-stu-id="cba7f-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="cba7f-115">Кроме того, почтовые ящики Exchange Server для каждой учетной записи должны быть либо в сети, либо локально.</span><span class="sxs-lookup"><span data-stu-id="cba7f-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="cba7f-116">И представитель, и делегат должны использовать одну и ту же основную версию Outlook.</span><span class="sxs-lookup"><span data-stu-id="cba7f-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="cba7f-117">В политике клиента для значения атрибута **енабликсчанжеделегатесинк** должно быть задано значение **true** .</span><span class="sxs-lookup"><span data-stu-id="cba7f-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="cba7f-118">Вы можете проверить этот параметр, запустив командлет **Get-CSClientPolicy** в модуле PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="cba7f-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="cba7f-119">И представитель, и делегат должны входить в Skype для бизнеса и Outlook одновременно на разных рабочих станциях.</span><span class="sxs-lookup"><span data-stu-id="cba7f-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="cba7f-120">Общие почтовые ящики не поддерживаются для делегирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="cba7f-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="cba7f-121">Это связано с тем, что в общем почтовом ящике нет списка управления доступом (ACL) **сендонбехалф** .</span><span class="sxs-lookup"><span data-stu-id="cba7f-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="cba7f-122">Поддержка версии клиента Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cba7f-122">Skype for Business client version support</span></span>

||<span data-ttu-id="cba7f-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="cba7f-123">**Outlook 2013**</span></span>|<span data-ttu-id="cba7f-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="cba7f-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cba7f-125">**Клиент Lync или Skype для бизнеса Basic**</span><span class="sxs-lookup"><span data-stu-id="cba7f-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="cba7f-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-126">Not supported</span></span> |<span data-ttu-id="cba7f-127">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-127">Not supported</span></span>
|<span data-ttu-id="cba7f-128">**Skype для бизнеса 2015**</span><span class="sxs-lookup"><span data-stu-id="cba7f-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="cba7f-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-129">Supported</span></span>| <span data-ttu-id="cba7f-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-130">Supported</span></span>|
|<span data-ttu-id="cba7f-131">**Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="cba7f-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="cba7f-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-132">Supported</span></span>| <span data-ttu-id="cba7f-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cba7f-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="cba7f-134">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="cba7f-134">Licensing requirements</span></span>

<span data-ttu-id="cba7f-135">**Сценарий лицензирования Enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="cba7f-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="cba7f-136">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="cba7f-136">**License**</span></span>|<span data-ttu-id="cba7f-137">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="cba7f-137">**Clients**</span></span>|<span data-ttu-id="cba7f-138">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="cba7f-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cba7f-139">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="cba7f-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="cba7f-140">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="cba7f-141">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="cba7f-142">Клиент Skype для бизнеса Basic не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="cba7f-143">Для клиентов Mac вы можете делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="cba7f-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="cba7f-144">Корпоративная система E3 с Office 365 Phone System + Office 365 Кскаллинг</span><span class="sxs-lookup"><span data-stu-id="cba7f-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="cba7f-145">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="cba7f-146">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="cba7f-147">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="cba7f-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="cba7f-148">Клиент Skype для бизнеса Basic не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="cba7f-149">Для клиентов Mac вы можете делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="cba7f-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="cba7f-150">**Сценарий корпоративного лицензирования "Корпоративная"**</span><span class="sxs-lookup"><span data-stu-id="cba7f-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="cba7f-151">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="cba7f-151">**License**</span></span>|<span data-ttu-id="cba7f-152">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="cba7f-152">**Clients**</span></span>|<span data-ttu-id="cba7f-153">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="cba7f-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cba7f-154">Корпоративный + ~</span><span class="sxs-lookup"><span data-stu-id="cba7f-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="cba7f-155">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="cba7f-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="cba7f-156">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="cba7f-157">Клиент Skype для бизнеса Basic не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="cba7f-158">Для клиентов Mac вы можете делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="cba7f-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="cba7f-159">Корпоративная стоимость + план звонков по Office 365</span><span class="sxs-lookup"><span data-stu-id="cba7f-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="cba7f-160">Skype для бизнеса для Mac 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="cba7f-161">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="cba7f-162">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba7f-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="cba7f-163">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="cba7f-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="cba7f-164">Клиент Skype для бизнеса Basic не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="cba7f-165">Для клиентов Mac вы можете делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="cba7f-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="cba7f-166">Настройка и проверка делегирования</span><span class="sxs-lookup"><span data-stu-id="cba7f-166">Set up and verify delegation</span></span>

<span data-ttu-id="cba7f-167">Чтобы настроить делегирование Skype для бизнеса Online, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cba7f-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="cba7f-168">Для клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="cba7f-168">For Windows clients</span></span>

 <span data-ttu-id="cba7f-169">**Вкладка "переадресация звонков"**</span><span class="sxs-lookup"><span data-stu-id="cba7f-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="cba7f-170">Выберите **Сервис** > **Параметры** > **переадресации звонков**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="cba7f-171">Выберите команду **изменить участников делегата**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="cba7f-172">Нажмите кнопку **Добавить**, выберите делегат, который вы хотите добавить, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="cba7f-173">**На вкладке "переадресация звонков"**</span><span class="sxs-lookup"><span data-stu-id="cba7f-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="cba7f-174">В \*\*\*\* Outlook выберите > **Параметры** > учетной записи для**делегирования доступа** > **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="cba7f-175">Найдите и добавьте имя человека, который будет представителем.</span><span class="sxs-lookup"><span data-stu-id="cba7f-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="cba7f-176">Откройте меню **Календарь** и выберите **редактор (может просматривать, создавать и изменять элементы)**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="cba7f-177">Для клиентов Mac — Lync</span><span class="sxs-lookup"><span data-stu-id="cba7f-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="cba7f-178">**Вкладка "переадресация звонков"**</span><span class="sxs-lookup"><span data-stu-id="cba7f-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="cba7f-179">Если у клиента нет вкладки **переадресации звонков** , в которой есть ссылка **изменить участников** -делегатов, а он расположен на компьютере Mac, он должен войти на компьютер под управлением Windows, чтобы настроить делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="cba7f-180">Это связано с тем, что клиенты Macintosh не могут устанавливать подключения по протоколу MAPI, и это требование для делегирования Skype для бизнеса из Outlook.</span><span class="sxs-lookup"><span data-stu-id="cba7f-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="cba7f-181">Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="cba7f-181">Verify success</span></span>

<span data-ttu-id="cba7f-182">Если установка прошла успешно, представителю будет видно, что **вы были добавлены в качестве делегата для _Лт_ наме_гт_** , а также о том, что пользователи, которые **управляют звонками для** группы, созданы.</span><span class="sxs-lookup"><span data-stu-id="cba7f-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="cba7f-183">Представитель должен увидеть, что группа **делегатов** создана.</span><span class="sxs-lookup"><span data-stu-id="cba7f-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cba7f-184">Разрешения на делегирование обычно выводятся в течение 30 минут после установки.</span><span class="sxs-lookup"><span data-stu-id="cba7f-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="cba7f-185">Тем не менее, этот процесс может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="cba7f-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="cba7f-186">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="cba7f-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="cba7f-187">Распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="cba7f-187">Common issues</span></span>

- > <span data-ttu-id="cba7f-188">**Вопрос 1** Запись делегата продолжает появляться в том случае, если **Пользователи управляют звонками для** групп после того, как он удалил делегат из клиента Outlook.</span><span class="sxs-lookup"><span data-stu-id="cba7f-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="cba7f-189">**Разрешение 1** В клиенте Skype для бизнеса щелкните делегат в группе **представители** правой кнопкой мыши и выберите команду **удалить из группы**.</span><span class="sxs-lookup"><span data-stu-id="cba7f-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="cba7f-190">**Вопрос 2** После того как представителю предоставлен доступ через клиент Outlook, ни сообщение с подтверждением, ни **Пользователи, которые не управляют вызовами для** группы, появятся для этого представителя.</span><span class="sxs-lookup"><span data-stu-id="cba7f-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="cba7f-191">**Разрешение 2** Удалите делегирование из клиента Outlook, подождите около 15 минут для репликации, а затем снова добавьте делегат.</span><span class="sxs-lookup"><span data-stu-id="cba7f-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="cba7f-192">Другие распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="cba7f-192">Other common issues</span></span>

- <span data-ttu-id="cba7f-193">Делегирование не работает в том случае, если превышено пороговое значение для 25 делегирований и 25 делегатов.</span><span class="sxs-lookup"><span data-stu-id="cba7f-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="cba7f-194">Клиент Skype для бизнеса базовый не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cba7f-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cba7f-195">При установке клиента Skype для бизнеса Basic будет удалено и разорвано делегирование.</span><span class="sxs-lookup"><span data-stu-id="cba7f-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="cba7f-196">Если значение **состояния MAPI** не подходит \*\*\*\*, убедитесь, что значения **SIP** и **SMTP** совпадают.</span><span class="sxs-lookup"><span data-stu-id="cba7f-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cba7f-197">После первого запуска Skype для бизнеса и Outlook может потребоваться несколько минут, чтобы состояние MAPI отображалось как " **ОК** ".</span><span class="sxs-lookup"><span data-stu-id="cba7f-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="cba7f-198">Создание группы безопасности и Добавление разрешений на делегирование для этой группы безопасности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cba7f-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="cba7f-199">MAPI недоступен.</span><span class="sxs-lookup"><span data-stu-id="cba7f-199">MAPI is unavailable.</span></span> <span data-ttu-id="cba7f-200">[В клиенте Skype для бизнеса 2016 появляется сообщение об ошибке "MAPI недоступен"](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="cba7f-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="cba7f-201">Почтовый ящик Exchange Online недоступен в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cba7f-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="cba7f-202">В этом случае выполните [проверку подключения Outlook](https://testconnectivity.microsoft.com/) , чтобы убедиться, что она пройдет.</span><span class="sxs-lookup"><span data-stu-id="cba7f-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="cba7f-203">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cba7f-203">Related topics</span></span>
[<span data-ttu-id="cba7f-204">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cba7f-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cba7f-205">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cba7f-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
