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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: В этой статье объясняется, как настроить и устранить неполадки Skype для бизнеса делегирования в Интернете. В этой статье вы можете получить рекомендации по настройке, рекомендациям и шагам по устранению неполадок.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239828"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="ed755-104">Настройка делегирования в Skype для бизнеса Online и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ed755-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ed755-105">В этой статье объясняется, как настроить и устранить неполадки Skype для бизнеса делегирования в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ed755-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="ed755-106">В этой статье вы можете получить рекомендации по настройке, рекомендациям и шагам по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="ed755-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="ed755-107">Рекомендации и требования</span><span class="sxs-lookup"><span data-stu-id="ed755-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="ed755-108">Рекомендации по делегирования</span><span class="sxs-lookup"><span data-stu-id="ed755-108">Guidelines for delegation</span></span>

<span data-ttu-id="ed755-109">Настройка и получение правильной работы делегирования зависят от следующих рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="ed755-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="ed755-110">Вы должны использовать клиент Skype для бизнеса 2015 с последними обновлениями или клиент Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="ed755-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="ed755-111">Необходимо использовать клиент Outlook 2013 с последними обновлениями или клиентом Outlook 2016 клиента.</span><span class="sxs-lookup"><span data-stu-id="ed755-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="ed755-112">Убедитесь, что у компьютеров представителя и делегатов есть один профиль Outlook, который является основным или профилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ed755-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="ed755-113">Этот профиль должен содержать только одну учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ed755-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="ed755-114">Skype для бизнеса представителем должны быть пользователи Online.</span><span class="sxs-lookup"><span data-stu-id="ed755-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="ed755-115">Кроме того, Exchange Server почтовые ящики для каждой учетной записи должны быть либо в сети, либо оба они должны быть локально.</span><span class="sxs-lookup"><span data-stu-id="ed755-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="ed755-116">Как представитель, так и представитель должны использовать один и тот же основной Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed755-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="ed755-117">Значение **атрибута EnableExchangeDelegateSync** должно иметь значение **true** в клиентской политике.</span><span class="sxs-lookup"><span data-stu-id="ed755-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="ed755-118">Вы можете проверить этот параметр, задав **командлет Get-CSClientPolicy** в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed755-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="ed755-119">Как представитель, так и представитель должны быть одновременно Skype для бизнеса и Outlook на разных рабочих станциях.</span><span class="sxs-lookup"><span data-stu-id="ed755-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="ed755-120">Общие почтовые ящики не поддерживаются для делегирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="ed755-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="ed755-121">Это значит, что у общего почтового ящика нет списка управления доступом **к** отправителю.</span><span class="sxs-lookup"><span data-stu-id="ed755-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="ed755-122">Skype для бизнеса версии клиента</span><span class="sxs-lookup"><span data-stu-id="ed755-122">Skype for Business client version support</span></span>

||<span data-ttu-id="ed755-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="ed755-123">**Outlook 2013**</span></span>|<span data-ttu-id="ed755-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="ed755-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed755-125">**Lync/Skype для бизнеса Basic Client**</span><span class="sxs-lookup"><span data-stu-id="ed755-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="ed755-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-126">Not supported</span></span> |<span data-ttu-id="ed755-127">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-127">Not supported</span></span>
|<span data-ttu-id="ed755-128">**Skype для бизнеса 2015**</span><span class="sxs-lookup"><span data-stu-id="ed755-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="ed755-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-129">Supported</span></span>| <span data-ttu-id="ed755-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-130">Supported</span></span>|
|<span data-ttu-id="ed755-131">**Skype для бизнеса 2016 г.**</span><span class="sxs-lookup"><span data-stu-id="ed755-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="ed755-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-132">Supported</span></span>| <span data-ttu-id="ed755-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="ed755-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="ed755-134">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="ed755-134">Licensing requirements</span></span>

<span data-ttu-id="ed755-135">**Enterprise Сценарий лицензирования E3**</span><span class="sxs-lookup"><span data-stu-id="ed755-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="ed755-136">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="ed755-136">**License**</span></span>|<span data-ttu-id="ed755-137">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="ed755-137">**Clients**</span></span>|<span data-ttu-id="ed755-138">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="ed755-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed755-139">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="ed755-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="ed755-140">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="ed755-141">Skype для бизнеса 2016 для Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="ed755-142">Skype для бизнеса Основной клиент не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="ed755-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="ed755-143">Для клиентов Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="ed755-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="ed755-144">Enterprise E3 с планом Телефонная система Office 365 + Office 365 xCalling</span><span class="sxs-lookup"><span data-stu-id="ed755-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="ed755-145">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="ed755-146">Skype для бизнеса 2016 для Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="ed755-147">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="ed755-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="ed755-148">Skype для бизнеса Основной клиент не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="ed755-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="ed755-149">Для клиентов Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="ed755-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="ed755-150">**Enterprise Сценарий лицензирования E5**</span><span class="sxs-lookup"><span data-stu-id="ed755-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="ed755-151">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="ed755-151">**License**</span></span>|<span data-ttu-id="ed755-152">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="ed755-152">**Clients**</span></span>|<span data-ttu-id="ed755-153">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="ed755-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed755-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="ed755-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="ed755-155">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="ed755-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="ed755-156">Skype для бизнеса 2016 для Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="ed755-157">Skype для бизнеса Основной клиент не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="ed755-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="ed755-158">Для клиентов Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="ed755-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="ed755-159">Enterprise План звонков Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ed755-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="ed755-160">Skype для бизнеса на Mac 2016 г.</span><span class="sxs-lookup"><span data-stu-id="ed755-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="ed755-161">Lync 2013 (Skype для бизнеса 2015) используется с Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="ed755-162">Skype для бизнеса 2016 для Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed755-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="ed755-163">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="ed755-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="ed755-164">Skype для бизнеса Основной клиент не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="ed755-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="ed755-165">Для клиентов Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="ed755-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="ed755-166">Настройка и проверка делегирования</span><span class="sxs-lookup"><span data-stu-id="ed755-166">Set up and verify delegation</span></span>

<span data-ttu-id="ed755-167">Чтобы настроить делег Skype для бизнеса Online, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ed755-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="ed755-168">Для Windows клиентов</span><span class="sxs-lookup"><span data-stu-id="ed755-168">For Windows clients</span></span>

 <span data-ttu-id="ed755-169">**Вкладка "Переадные вызовы"**</span><span class="sxs-lookup"><span data-stu-id="ed755-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="ed755-170">Выберите   >  **Инструменты**  >  **Параметры Переад** Параметры .</span><span class="sxs-lookup"><span data-stu-id="ed755-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="ed755-171">Выберите **Изменить участников-делегатов**.</span><span class="sxs-lookup"><span data-stu-id="ed755-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="ed755-172">Выберите **Добавить**, выберите делегата, который вы хотите добавить, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ed755-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="ed755-173">**Вкладка "Не переадваровка зовите"**</span><span class="sxs-lookup"><span data-stu-id="ed755-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="ed755-174">В Outlook выберите **Учетная** запись  >  **Параметры**  >  **делегировать**  >  **доступ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ed755-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="ed755-175">Найдите и добавьте имя человека, который будет делегатом.</span><span class="sxs-lookup"><span data-stu-id="ed755-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="ed755-176">Выберите меню **Календарь,** а затем — Редактор **(может читать, создавать и изменять элементы).**</span><span class="sxs-lookup"><span data-stu-id="ed755-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="ed755-177">Для клиентов Mac — Lync</span><span class="sxs-lookup"><span data-stu-id="ed755-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="ed755-178">**Вкладка "Переадные вызовы"**</span><span class="sxs-lookup"><span data-stu-id="ed755-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="ed755-179">Если у клиента нет  вкладки "Переадстройка зовов" со ссылкой Изменить участников-делегатов, а представитель находится на компьютере Mac, для того чтобы настроить делегирование, представитель должен войти на Windows на компьютере на базе Windows. </span><span class="sxs-lookup"><span data-stu-id="ed755-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="ed755-180">Это потому, что клиенты Mac не могут устанавливать подключения MAPI, и это необходимо для Skype для бизнеса делегирования Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed755-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="ed755-181">Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="ed755-181">Verify success</span></span>

<span data-ttu-id="ed755-182">Если настройка прошла успешно, делегат должен увидеть, что вы были добавлены в качестве делегата  для < Name **>,** а также о том, что создана группа Люди, которые управляют звонками для.</span><span class="sxs-lookup"><span data-stu-id="ed755-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="ed755-183">Делегат должен увидеть, что **создана** группа Делегаты.</span><span class="sxs-lookup"><span data-stu-id="ed755-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed755-184">Разрешения делегирования обычно появляются в течение 30 минут после настройки.</span><span class="sxs-lookup"><span data-stu-id="ed755-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="ed755-185">Однако этот процесс может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ed755-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="ed755-186">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ed755-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="ed755-187">Распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="ed755-187">Common issues</span></span>

- > <span data-ttu-id="ed755-188">**Проблема 1** Представитель по-прежнему будет отображаться в группе Люди, которые управляют **звонками,** после того как представитель удалил делегата из Outlook клиента.</span><span class="sxs-lookup"><span data-stu-id="ed755-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="ed755-189">**Разрешение 1** В клиенте Skype для бизнеса щелкните правой кнопкой  мыши делегата в группе Представители и выберите **удалить из группы**.</span><span class="sxs-lookup"><span data-stu-id="ed755-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="ed755-190">**Проблема 2** После предоставления делегатского доступа через клиента Outlook ни подтверждение, ни  группа "Люди, которые управляют звонками для" не отображаются для делегата.</span><span class="sxs-lookup"><span data-stu-id="ed755-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="ed755-191">**Разрешение 2** Удалите делегирование из клиента Outlook, подождите около 15 минут для репликации, а затем снова добавьте представителя.</span><span class="sxs-lookup"><span data-stu-id="ed755-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="ed755-192">Другие распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="ed755-192">Other common issues</span></span>

- <span data-ttu-id="ed755-193">Делегирования не работают, если превышен пороговое значение в 25 представителей и 25 делегатов.</span><span class="sxs-lookup"><span data-stu-id="ed755-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="ed755-194">Клиент Skype для бизнеса Basic не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ed755-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed755-195">Если вы установите клиент Skype для бизнеса Basic, делегирования будут удаляться и разрываться.</span><span class="sxs-lookup"><span data-stu-id="ed755-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="ed755-196">Если значение **СОСТОЯНИЕ MAPI** не **ОК,** убедитесь, что значения **SIP** и **SMTP** совпадают.</span><span class="sxs-lookup"><span data-stu-id="ed755-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed755-197">Состояние MAPI отображается как ОК после  первого Skype для бизнеса и Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed755-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="ed755-198">Создание группы безопасности и добавление для нее разрешений делегирования не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ed755-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="ed755-199">MapI недоступен.</span><span class="sxs-lookup"><span data-stu-id="ed755-199">MAPI is unavailable.</span></span> <span data-ttu-id="ed755-200">См. [сообщение об ошибке MAPI в Skype для бизнеса 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="ed755-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="ed755-201">Почтовый Exchange Online недоступн через Skype для бизнеса клиента.</span><span class="sxs-lookup"><span data-stu-id="ed755-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="ed755-202">В этом случае запустите проверку Outlook [подключения,](https://testconnectivity.microsoft.com/) чтобы убедиться, что он прошел.</span><span class="sxs-lookup"><span data-stu-id="ed755-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ed755-203">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ed755-203">Related topics</span></span>
[<span data-ttu-id="ed755-204">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ed755-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ed755-205">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed755-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
