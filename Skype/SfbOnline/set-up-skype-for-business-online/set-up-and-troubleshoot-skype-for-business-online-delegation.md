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
description: В этой статье объясняется, как настроить делегирования в Skype для бизнеса Online и устранить неполадки с этим приложением. В этой статье указаны рекомендации по настройке, рекомендации и инструкции по устранению неполадок.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010802"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="f100a-104">Настройка делегирования в Skype для бизнеса Online и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f100a-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="f100a-105">В этой статье объясняется, как настроить делегирования в Skype для бизнеса Online и устранить неполадки с этим приложением.</span><span class="sxs-lookup"><span data-stu-id="f100a-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="f100a-106">В этой статье указаны рекомендации по настройке, рекомендации и инструкции по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="f100a-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="f100a-107">Инструкции и требования</span><span class="sxs-lookup"><span data-stu-id="f100a-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="f100a-108">Рекомендации по делегирования</span><span class="sxs-lookup"><span data-stu-id="f100a-108">Guidelines for delegation</span></span>

<span data-ttu-id="f100a-109">Настройка и правильная настройка делегирования зависят от того, что вы совмести с этими правилами:</span><span class="sxs-lookup"><span data-stu-id="f100a-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="f100a-110">Необходимо использовать полный клиент Skype для бизнеса 2015 с последними обновлениями или полный клиент Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="f100a-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="f100a-111">Необходимо использовать клиент Outlook 2013 с последними обновлениями или клиент Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="f100a-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="f100a-112">Убедитесь, что у делегатов и компьютеров с делегированием есть один профиль почты Outlook, который является основным или профилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f100a-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="f100a-113">Профиль почты должен содержать только одну учетную запись.</span><span class="sxs-lookup"><span data-stu-id="f100a-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="f100a-114">Представитель и представитель Skype для бизнеса должны быть пользователями Online.</span><span class="sxs-lookup"><span data-stu-id="f100a-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="f100a-115">Кроме того, Exchange Server почтовые ящики для каждой учетной записи должны быть либо сетевыми, либо оба они должны быть локально.</span><span class="sxs-lookup"><span data-stu-id="f100a-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="f100a-116">У представителя и представителя должна быть одна и та же основная версия Outlook.</span><span class="sxs-lookup"><span data-stu-id="f100a-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="f100a-117">В политике клиента значение атрибута **EnableExchangeDelegateSync** должно быть установлено как истинное. </span><span class="sxs-lookup"><span data-stu-id="f100a-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="f100a-118">Вы можете проверить этот параметр, задав командлет **Get-CSClientPolicy** в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f100a-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="f100a-119">Как представитель, так и делегат должны одновременно ввести учетные данными в Skype для бизнеса и Outlook на разных рабочих станциях.</span><span class="sxs-lookup"><span data-stu-id="f100a-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="f100a-120">Делегирования в Skype для бизнеса Online не поддерживаются для общих почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="f100a-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="f100a-121">Это значит, что у общего почтового ящика нет списка управления доступом **от** имени отправляемой почты.</span><span class="sxs-lookup"><span data-stu-id="f100a-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="f100a-122">Поддержка версии клиента Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f100a-122">Skype for Business client version support</span></span>

||<span data-ttu-id="f100a-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="f100a-123">**Outlook 2013**</span></span>|<span data-ttu-id="f100a-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="f100a-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f100a-125">**Клиент Lync/Skype для бизнеса Basic**</span><span class="sxs-lookup"><span data-stu-id="f100a-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="f100a-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-126">Not supported</span></span> |<span data-ttu-id="f100a-127">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-127">Not supported</span></span>
|<span data-ttu-id="f100a-128">**Skype для бизнеса 2015**</span><span class="sxs-lookup"><span data-stu-id="f100a-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="f100a-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-129">Supported</span></span>| <span data-ttu-id="f100a-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-130">Supported</span></span>|
|<span data-ttu-id="f100a-131">**Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="f100a-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="f100a-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-132">Supported</span></span>| <span data-ttu-id="f100a-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="f100a-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="f100a-134">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="f100a-134">Licensing requirements</span></span>

<span data-ttu-id="f100a-135">**Сценарий лицензирования корпоративный E3**</span><span class="sxs-lookup"><span data-stu-id="f100a-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="f100a-136">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="f100a-136">**License**</span></span>|<span data-ttu-id="f100a-137">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="f100a-137">**Clients**</span></span>|<span data-ttu-id="f100a-138">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="f100a-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f100a-139">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="f100a-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="f100a-140">Lync 2013 (Skype для бизнеса 2015), используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f100a-141">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="f100a-142">Клиент Skype для бизнеса Basic не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="f100a-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f100a-143">В клиентах Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="f100a-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="f100a-144">Корпоративный E3 с телефонной системой Office 365 + План xCalling Office 365</span><span class="sxs-lookup"><span data-stu-id="f100a-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="f100a-145">Lync 2013 (Skype для бизнеса 2015), используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f100a-146">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f100a-147">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="f100a-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="f100a-148">Клиент Skype для бизнеса Basic не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="f100a-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f100a-149">В клиентах Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="f100a-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="f100a-150">**Сценарий лицензирования корпоративный E5**</span><span class="sxs-lookup"><span data-stu-id="f100a-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="f100a-151">**Лицензия**</span><span class="sxs-lookup"><span data-stu-id="f100a-151">**License**</span></span>|<span data-ttu-id="f100a-152">**Клиенты**</span><span class="sxs-lookup"><span data-stu-id="f100a-152">**Clients**</span></span>|<span data-ttu-id="f100a-153">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="f100a-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f100a-154">Корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="f100a-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="f100a-155">Lync 2013 (Skype для бизнеса 2015), используемый в Outlook 2013 или Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="f100a-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="f100a-156">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="f100a-157">Клиент Skype для бизнеса Basic не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="f100a-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f100a-158">В клиентах Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="f100a-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="f100a-159">Корпоративный E5 и план звонков Office 365</span><span class="sxs-lookup"><span data-stu-id="f100a-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="f100a-160">Skype для бизнеса для Mac 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="f100a-161">Lync 2013 (Skype для бизнеса 2015), используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f100a-162">Skype для бизнеса 2016, используемый в Outlook 2013 или Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f100a-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f100a-163">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="f100a-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="f100a-164">Клиент Skype для бизнеса Basic не поддерживает делегирования.</span><span class="sxs-lookup"><span data-stu-id="f100a-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f100a-165">В клиентах Mac можно делегировать звонки, но не собрания.</span><span class="sxs-lookup"><span data-stu-id="f100a-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="f100a-166">Настройка и проверка делегирования</span><span class="sxs-lookup"><span data-stu-id="f100a-166">Set up and verify delegation</span></span>

<span data-ttu-id="f100a-167">Чтобы настроить делегирования в Skype для бизнеса Online, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f100a-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="f100a-168">Для клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="f100a-168">For Windows clients</span></span>

 <span data-ttu-id="f100a-169">**Вкладка "Переадные вызовы"**</span><span class="sxs-lookup"><span data-stu-id="f100a-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="f100a-170">Выберите **"Параметры**  >  **переададной**  >  **связи" в меню "Инструменты".**</span><span class="sxs-lookup"><span data-stu-id="f100a-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="f100a-171">Выберите **"Изменить участников-делегатов".**</span><span class="sxs-lookup"><span data-stu-id="f100a-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="f100a-172">Выберите **"Добавить",** выберите делегата, который вы хотите добавить, а затем выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="f100a-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="f100a-173">**Вкладка "Не переад вызовов"**</span><span class="sxs-lookup"><span data-stu-id="f100a-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="f100a-174">В Outlook выберите **"Добавить"**  >  **в параметрах учетной** записи для  >  **учетной записи с делегированием**  >  **доступа.**</span><span class="sxs-lookup"><span data-stu-id="f100a-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="f100a-175">Найдите и добавьте имя человека, который будет делегатом.</span><span class="sxs-lookup"><span data-stu-id="f100a-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="f100a-176">В меню **"Календарь"** выберите "Редактор" **(может читать, создавать и изменять элементы).**</span><span class="sxs-lookup"><span data-stu-id="f100a-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="f100a-177">Для клиентов Mac — Lync</span><span class="sxs-lookup"><span data-stu-id="f100a-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="f100a-178">**Вкладка "Переадные вызовы"**</span><span class="sxs-lookup"><span data-stu-id="f100a-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="f100a-179">Если у клиента нет  вкладки "Переадстройка вызовов", которая имеет ссылку "Изменить участников-делегатов", а представитель находится на компьютере Mac, то для того чтобы настроить делегирование, необходимо войти на компьютер с Windows. </span><span class="sxs-lookup"><span data-stu-id="f100a-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="f100a-180">Это необходимо для того, чтобы в клиентах Mac не было подключений MAPI, а это необходимо для делегирования skype для бизнеса из Outlook.</span><span class="sxs-lookup"><span data-stu-id="f100a-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="f100a-181">Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="f100a-181">Verify success</span></span>

<span data-ttu-id="f100a-182">В случае успешной настройки представитель  увидит, что вас добавили в качестве делегата < Имя >, а также о том, что создана группа "Люди, управление звонками для которых я".</span><span class="sxs-lookup"><span data-stu-id="f100a-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="f100a-183">Делегат должен увидеть, что **группа** "Делегаты" создана.</span><span class="sxs-lookup"><span data-stu-id="f100a-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f100a-184">Разрешения делегирования обычно появляются в течение 30 минут после настройки.</span><span class="sxs-lookup"><span data-stu-id="f100a-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="f100a-185">Однако этот процесс может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f100a-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="f100a-186">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f100a-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="f100a-187">Распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="f100a-187">Common issues</span></span>

- > <span data-ttu-id="f100a-188">**Проблема 1** Запись делегата по-прежнему будет отображаться в группе **"Люди,** которые управляют звонками в группе", после того как представитель удал делегата из клиента Outlook.</span><span class="sxs-lookup"><span data-stu-id="f100a-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="f100a-189">**Разрешение 1** В клиенте Skype для бизнеса щелкните  правой кнопкой мыши делегата в группе "Делегаты" и выберите **"Удалить из группы".**</span><span class="sxs-lookup"><span data-stu-id="f100a-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="f100a-190">**Проблема 2** После предоставления делегата в клиенте Outlook ни подтверждение,  ни группа "Люди, управление звонками для которых я" не отображаются для делегата.</span><span class="sxs-lookup"><span data-stu-id="f100a-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="f100a-191">**Разрешение 2** Удалите делегирование из клиента Outlook, подождите около 15 минут репликации и снова добавьте делегата.</span><span class="sxs-lookup"><span data-stu-id="f100a-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="f100a-192">Другие распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="f100a-192">Other common issues</span></span>

- <span data-ttu-id="f100a-193">Делегирования не работают, если превышено пороговое значение в 25 представителей и 25 делегатов.</span><span class="sxs-lookup"><span data-stu-id="f100a-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="f100a-194">Клиент Skype для бизнеса Basic не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f100a-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f100a-195">При установке клиента Skype для бизнеса Basic он удаляет и разрывает делегирования.</span><span class="sxs-lookup"><span data-stu-id="f100a-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="f100a-196">Если значение **состояния MAPI** не **соответствует,** убедитесь, что значения **SIP** и **SMTP** совпадают.</span><span class="sxs-lookup"><span data-stu-id="f100a-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f100a-197">Состояние MAPI отображается в состоянии "ОК" в течение нескольких минут после первого запуска Skype для бизнеса и Outlook. </span><span class="sxs-lookup"><span data-stu-id="f100a-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="f100a-198">Создание группы безопасности и добавление для нее разрешений делегирования не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f100a-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="f100a-199">MapI недоступна.</span><span class="sxs-lookup"><span data-stu-id="f100a-199">MAPI is unavailable.</span></span> <span data-ttu-id="f100a-200">См. [сообщение об ошибке MAPI в клиенте Skype для бизнеса 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="f100a-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="f100a-201">Почтовый ящик Exchange Online не доступен через клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f100a-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="f100a-202">В этом случае запустите тест [подключения к Outlook,](https://testconnectivity.microsoft.com/) чтобы убедиться, что он прошел.</span><span class="sxs-lookup"><span data-stu-id="f100a-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f100a-203">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f100a-203">Related topics</span></span>
[<span data-ttu-id="f100a-204">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f100a-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f100a-205">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f100a-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
