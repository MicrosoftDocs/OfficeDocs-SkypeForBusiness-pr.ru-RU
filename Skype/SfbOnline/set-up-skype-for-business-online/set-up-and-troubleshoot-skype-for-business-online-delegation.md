---
title: Настройка делегирования в Skype для бизнеса Online и устранение неполадок
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: В этой статье объясняется, как настроить и устранении неполадок Скайп для бизнеса в Интернет делегирования. В этой статье описаны рекомендации по рекомендации по настройке, рекомендации и действия по устранению неполадок.
ms.openlocfilehash: 5af84a6731d1f1e95a8d9da70fcd7c2677f36d7d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370893"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="a4849-104">Настройка делегирования в Skype для бизнеса Online и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a4849-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="a4849-105">В этой статье объясняется, как настроить и устранении неполадок Скайп для бизнеса в Интернет делегирования.</span><span class="sxs-lookup"><span data-stu-id="a4849-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="a4849-106">В этой статье описаны рекомендации по рекомендации по настройке, рекомендации и действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="a4849-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="a4849-107">Рекомендации и требования</span><span class="sxs-lookup"><span data-stu-id="a4849-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="a4849-108">Рекомендации для делегирования</span><span class="sxs-lookup"><span data-stu-id="a4849-108">Guidelines for delegation</span></span>

<span data-ttu-id="a4849-109">Настройка и делегирования для правильной работы зависит от следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="a4849-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="a4849-110">Необходимо использовать Скайп для бизнеса 2015 полный клиент с последними обновлениями или Скайп для полного клиента 2016 бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a4849-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="a4849-111">Необходимо использовать клиент Outlook 2013 с последними обновлениями или в клиенте Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="a4849-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="a4849-112">Убедитесь в том, что представитель и делегат компьютеры имеют один профиль почты Outlook, который является основной или профиля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4849-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="a4849-113">Что профиль электронной почты должен содержать только одну учетную запись.</span><span class="sxs-lookup"><span data-stu-id="a4849-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="a4849-114">Скайп для бизнеса для сотрудника и делегат должны быть активные пользователи.</span><span class="sxs-lookup"><span data-stu-id="a4849-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="a4849-115">Кроме того почтовые ящики Exchange Server для каждой учетной записи, необходимо быть Online или быть локальной.</span><span class="sxs-lookup"><span data-stu-id="a4849-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="a4849-116">Представитель и делегат должен с помощью той же основной версии Outlook.</span><span class="sxs-lookup"><span data-stu-id="a4849-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="a4849-117">Значение атрибута **EnableExchangeDelegateSync** должен иметь значение **true** в политике клиента.</span><span class="sxs-lookup"><span data-stu-id="a4849-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="a4849-118">Этот параметр можно проверить с помощью командлета **Get-CSClientPolicy** в Скайп для модуля Online PowerShell бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a4849-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="a4849-119">Представитель и делегат должен входить в систему Скайп для бизнес-деятельности и Outlook в то же время на разных рабочих станциях.</span><span class="sxs-lookup"><span data-stu-id="a4849-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="a4849-120">Общие почтовые ящики не поддерживаются для Скайп для бизнеса в Интернет делегирования.</span><span class="sxs-lookup"><span data-stu-id="a4849-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="a4849-121">Это так, как общего почтового ящика не имеет **sendonbehalf** управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="a4849-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="a4849-122">Скайп для поддержки версии клиента Business</span><span class="sxs-lookup"><span data-stu-id="a4849-122">Skype for Business client version support</span></span>

||<span data-ttu-id="a4849-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="a4849-123">**Outlook 2013**</span></span>|<span data-ttu-id="a4849-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="a4849-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4849-125">**Lync/Скайп для базовой клиента Business**</span><span class="sxs-lookup"><span data-stu-id="a4849-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="a4849-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-126">Not supported</span></span> |<span data-ttu-id="a4849-127">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-127">Not supported</span></span>
|<span data-ttu-id="a4849-128">**Skype для бизнеса 2015**</span><span class="sxs-lookup"><span data-stu-id="a4849-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="a4849-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-129">Supported</span></span>| <span data-ttu-id="a4849-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-130">Supported</span></span>|
|<span data-ttu-id="a4849-131">**Скайп 2016 бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a4849-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="a4849-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-132">Supported</span></span>| <span data-ttu-id="a4849-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a4849-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="a4849-134">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="a4849-134">Licensing requirements</span></span>

<span data-ttu-id="a4849-135">**Сценарий E3 корпоративного лицензирования**</span><span class="sxs-lookup"><span data-stu-id="a4849-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="a4849-136">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="a4849-136">**License**</span></span>|<span data-ttu-id="a4849-137">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="a4849-137">**Clients**</span></span>|<span data-ttu-id="a4849-138">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="a4849-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4849-139">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="a4849-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="a4849-140">Использовать с Outlook 2013 и Outlook 2016 Lync 2013 (Скайп для бизнеса 2015)</span><span class="sxs-lookup"><span data-stu-id="a4849-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a4849-141">Скайп использовать с Outlook 2013 и Outlook 2016 2016 бизнеса</span><span class="sxs-lookup"><span data-stu-id="a4849-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="a4849-142">Скайп для бизнеса базовый клиент не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="a4849-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a4849-143">Для клиентов можно передать вызовов, но не встреч.</span><span class="sxs-lookup"><span data-stu-id="a4849-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="a4849-144">Для предприятий E3 с телефонной системой Office 365 + Office 365 xCalling плана</span><span class="sxs-lookup"><span data-stu-id="a4849-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="a4849-145">Использовать с Outlook 2013 и Outlook 2016 Lync 2013 (Скайп для бизнеса 2015)</span><span class="sxs-lookup"><span data-stu-id="a4849-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a4849-146">Скайп использовать с Outlook 2013 и Outlook 2016 2016 бизнеса</span><span class="sxs-lookup"><span data-stu-id="a4849-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a4849-147">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="a4849-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="a4849-148">Скайп для бизнеса базовый клиент не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="a4849-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a4849-149">Для клиентов можно передать вызовов, но не встреч.</span><span class="sxs-lookup"><span data-stu-id="a4849-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="a4849-150">**Сценарий E5 корпоративного лицензирования**</span><span class="sxs-lookup"><span data-stu-id="a4849-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="a4849-151">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="a4849-151">**License**</span></span>|<span data-ttu-id="a4849-152">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="a4849-152">**Clients**</span></span>|<span data-ttu-id="a4849-153">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="a4849-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4849-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a4849-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="a4849-155">Lync 2013 (Скайп для бизнеса 2015) используется с Outlook 2016 или Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="a4849-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="a4849-156">Скайп использовать с Outlook 2013 и Outlook 2016 2016 бизнеса</span><span class="sxs-lookup"><span data-stu-id="a4849-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="a4849-157">Скайп для бизнеса базовый клиент не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="a4849-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a4849-158">Для клиентов можно передать вызовов, но не встреч.</span><span class="sxs-lookup"><span data-stu-id="a4849-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="a4849-159">E5 предприятия, а также план вызова Office 365</span><span class="sxs-lookup"><span data-stu-id="a4849-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="a4849-160">Скайп для бизнеса 2016 Mac</span><span class="sxs-lookup"><span data-stu-id="a4849-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="a4849-161">Использовать с Outlook 2013 и Outlook 2016 Lync 2013 (Скайп для бизнеса 2015)</span><span class="sxs-lookup"><span data-stu-id="a4849-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a4849-162">Скайп использовать с Outlook 2013 и Outlook 2016 2016 бизнеса</span><span class="sxs-lookup"><span data-stu-id="a4849-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a4849-163">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="a4849-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="a4849-164">Скайп для бизнеса базовый клиент не поддерживает делегирование.</span><span class="sxs-lookup"><span data-stu-id="a4849-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a4849-165">Для клиентов можно передать вызовов, но не встреч.</span><span class="sxs-lookup"><span data-stu-id="a4849-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="a4849-166">Установка и проверка делегирования</span><span class="sxs-lookup"><span data-stu-id="a4849-166">Set up and verify delegation</span></span>

<span data-ttu-id="a4849-167">Чтобы настроить Скайп для бизнеса в Интернет делегирования, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a4849-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="a4849-168">Для клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="a4849-168">For Windows clients</span></span>

 <span data-ttu-id="a4849-169">**Вкладка переадресации звонков**</span><span class="sxs-lookup"><span data-stu-id="a4849-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="a4849-170">Выбор **инструментов** > **Параметры** > **параметры переадресации звонков**.</span><span class="sxs-lookup"><span data-stu-id="a4849-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="a4849-171">Выберите команду **изменить участников-делегатов**.</span><span class="sxs-lookup"><span data-stu-id="a4849-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="a4849-172">Выберите **Добавить**, выберите делегата, который вы хотите добавить и нажмите кнопку « **ОК»**.</span><span class="sxs-lookup"><span data-stu-id="a4849-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
   <span data-ttu-id="a4849-173">**Отсутствует вкладка переадресация звонков**</span><span class="sxs-lookup"><span data-stu-id="a4849-173">**No Call Forwarding tab**</span></span>
  
4. <span data-ttu-id="a4849-174">В программе Outlook, выберите **файл** > **Параметры учетной записи** > **Делегированный доступ** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="a4849-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
5. <span data-ttu-id="a4849-175">Найдите, а затем добавьте имя человека, который будет делегата.</span><span class="sxs-lookup"><span data-stu-id="a4849-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
6. <span data-ttu-id="a4849-176">Выберите меню « **Календарь** », а затем выберите **редактора (можно читать, создавать и изменять элементы)**.</span><span class="sxs-lookup"><span data-stu-id="a4849-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="a4849-177">Для клиентов, Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="a4849-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="a4849-178">**Вкладка переадресации звонков**</span><span class="sxs-lookup"><span data-stu-id="a4849-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="a4849-179">Если клиент не настроено на вкладке **Переадресация звонков** , имеющей ссылку **изменить участников-делегатов** и представитель расположен на компьютере Mac, представитель необходимо выполнить вход на компьютере под управлением Windows для настройки делегирования.</span><span class="sxs-lookup"><span data-stu-id="a4849-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="a4849-180">Это так, как клиентов не может подключаться MAPI, и это требование для установления Скайп для делегирования Business из Outlook.</span><span class="sxs-lookup"><span data-stu-id="a4849-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="a4849-181">Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="a4849-181">Verify success</span></span>

<span data-ttu-id="a4849-182">Если настройка выполнена успешно, делегат должны отображаться **были добавлены в качестве представителя для < имя >** сообщения и Кроме того, создается группа **людей я управление вызовы для** .</span><span class="sxs-lookup"><span data-stu-id="a4849-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="a4849-183">Представитель должны видеть, что создана группа **делегаты** .</span><span class="sxs-lookup"><span data-stu-id="a4849-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4849-184">Делегирование разрешений обычно отобразиться в течение 30 минут процесс установки.</span><span class="sxs-lookup"><span data-stu-id="a4849-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="a4849-185">Тем не менее этот процесс может занять более 24 часов.</span><span class="sxs-lookup"><span data-stu-id="a4849-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="a4849-186">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a4849-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="a4849-187">Распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="a4849-187">Common issues</span></span>

- > <span data-ttu-id="a4849-188">**Проблема 1** Запись делегат остается в группе **людей я управление вызовы для** после представитель делегата из клиента Outlook.</span><span class="sxs-lookup"><span data-stu-id="a4849-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="a4849-189">**Решение 1** На Скайп для клиента Business щелкните правой кнопкой мыши пользователя в группу **делегатов** и затем выберите команду **Удалить из группы**.</span><span class="sxs-lookup"><span data-stu-id="a4849-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="a4849-190">**Проблема 2** После делегированный доступ предоставляется с помощью клиента Outlook, ни сообщении о подтверждении, ни **людей я управление звонки для** группы отображаются для делегата.</span><span class="sxs-lookup"><span data-stu-id="a4849-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="a4849-191">**Решение 2** Удаление делегирования из клиента Outlook, подождите в течение 15 минут для репликации и затем снова добавьте делегат.</span><span class="sxs-lookup"><span data-stu-id="a4849-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="a4849-192">Другие распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="a4849-192">Other common issues</span></span>

- <span data-ttu-id="a4849-193">Делегирование не работает при превышении порогового значения 25 выполнившему и 25 делегатов.</span><span class="sxs-lookup"><span data-stu-id="a4849-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="a4849-194">Скайп для бизнеса базовый клиент не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a4849-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a4849-195">При установке Скайп для бизнеса базовой клиента, его можно было удалить и нарушение делегирования.</span><span class="sxs-lookup"><span data-stu-id="a4849-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="a4849-196">Если значение **Состояния MAPI** не **ОК**, убедитесь в том, что соответствующие значения **SIP** и **SMTP** .</span><span class="sxs-lookup"><span data-stu-id="a4849-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a4849-197">Может потребоваться несколько минут состояние MAPI для отображения как **ОК** после сначала запустите Скайп для бизнес-деятельности и Outlook.</span><span class="sxs-lookup"><span data-stu-id="a4849-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="a4849-198">Создание группы безопасности и добавления разрешений делегирования для этой группы безопасности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a4849-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="a4849-199">MAPI недоступна.</span><span class="sxs-lookup"><span data-stu-id="a4849-199">MAPI is unavailable.</span></span> <span data-ttu-id="a4849-200">В разделе [«недоступен» ошибка в Скайп для клиента 2016 бизнеса](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="a4849-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="a4849-201">Почтовый ящик Exchange Online не будет доступна через Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="a4849-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="a4849-202">При возникновении этой ошибки запустите [Outlook Проверка подключения](https://testconnectivity.microsoft.com/) к убедитесь в том, что они передают.</span><span class="sxs-lookup"><span data-stu-id="a4849-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a4849-203">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a4849-203">Related topics</span></span>
[<span data-ttu-id="a4849-204">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a4849-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a4849-205">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a4849-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 