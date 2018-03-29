---
title: Управление учетными записями пользователей для Скайп для Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: В этой статье описаны как включить, временно отключить или удалить пользователей Active Directory из Скайп для Business Server 2015.
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a><span data-ttu-id="38cd2-103">Управление учетными записями пользователей для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38cd2-103">Manage user accounts for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38cd2-104">В этой статье описаны как включить, временно отключить или удалить пользователей Active Directory из Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38cd2-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="38cd2-105">Сведения о том, как включить пользователя Active Directory можно [Создать новую учетную запись пользователя](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="38cd2-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="38cd2-106">Удаление пользователя Active Directory содержатся в разделе [Удаление учетной записи пользователя](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="38cd2-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>
  
<span data-ttu-id="38cd2-107">Эти процедуры следует выполнять во время обслуживания, при Скайп для использования Business низшего.</span><span class="sxs-lookup"><span data-stu-id="38cd2-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="38cd2-108">Будет ли это делается по расписанию ежедневных и еженедельных определяются потребности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="38cd2-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span> 
  
<span data-ttu-id="38cd2-109">Эта статья содержит следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="38cd2-109">This article contains the following procedures:</span></span>
  
- [<span data-ttu-id="38cd2-110">Для поиска одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="38cd2-110">To search for one or more users</span></span>](user-accounts.md#Search)
    
- [<span data-ttu-id="38cd2-111">Добавление и включение новой Скайп для пользователя Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38cd2-111">Add and enable a new Skype for Business Server 2015 user</span></span>](user-accounts.md#Add)
    
- [<span data-ttu-id="38cd2-112">Отключение или повторное включение учетной записи пользователя, ранее было разрешено для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="38cd2-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)
    
- [<span data-ttu-id="38cd2-113">Отключение пользователя от корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="38cd2-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)
    
- [<span data-ttu-id="38cd2-114">Удаление учетной записи пользователя с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="38cd2-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="38cd2-115">Для поиска одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="38cd2-115">To search for one or more users</span></span>
<span data-ttu-id="38cd2-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-116"></span></span>

<span data-ttu-id="38cd2-117">Результаты запроса поиска можно использовать для настройки пользователей Active Directory для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38cd2-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server 2015.</span></span> <span data-ttu-id="38cd2-118">Можно выполнить поиск пользователей по отображаемое имя, имя первого, последнего имени, имя учетной записи диспетчера учетных записей (SAM), SIP-адрес или строки универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="38cd2-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>
  
<span data-ttu-id="38cd2-119">Можно выполнить поиск пользователей Скайп для или с помощью панели управления сервера Business Active Directory — пользователи и компьютеры оснастку.</span><span class="sxs-lookup"><span data-stu-id="38cd2-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="38cd2-120">Следующая процедура описывается использование Скайп для панели управления Business Server для поиска пользователей.</span><span class="sxs-lookup"><span data-stu-id="38cd2-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38cd2-121">В среде с топологии с центральным лесом результаты поиска может оказаться точных при выполнении поиска пользователя, адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="38cd2-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="38cd2-122">Вместо этого можно найти пользователей путем указания префикса адрес SIP, sip: имя, добавить фильтр поиска и выберите SIP-адрес, содержащий адрес электронной почты частичное или с помощью командлета **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="38cd2-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>
  
1. <span data-ttu-id="38cd2-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38cd2-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38cd2-124">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38cd2-125">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-125">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38cd2-126">В поле **поиска пользователей** , введите или первой части отображаемого имени, имени, фамилии, учетной записи SAM SIP-адрес или строке URI учетной записи пользователя, которую требуется найти и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>
    
5. <span data-ttu-id="38cd2-127">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="38cd2-127">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="38cd2-128">а.</span><span class="sxs-lookup"><span data-stu-id="38cd2-128">a.</span></span> <span data-ttu-id="38cd2-129">Нажмите кнопку со стрелкой развертывания в верхнем правом углу экрана над **результатами поиска**и нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
   <span data-ttu-id="38cd2-130">б.</span><span class="sxs-lookup"><span data-stu-id="38cd2-130">b.</span></span> <span data-ttu-id="38cd2-131">Введите свойство пользователя, введя его или щелкните стрелку в раскрывающемся списке выберите свойство пользователя.</span><span class="sxs-lookup"><span data-stu-id="38cd2-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
   <span data-ttu-id="38cd2-132">в.</span><span class="sxs-lookup"><span data-stu-id="38cd2-132">c.</span></span> <span data-ttu-id="38cd2-133">В списке **равно** щелкните **равно** или **не равно**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
   <span data-ttu-id="38cd2-134">г.</span><span class="sxs-lookup"><span data-stu-id="38cd2-134">d.</span></span> <span data-ttu-id="38cd2-135">В текстовом поле введите требуемые условия поиска, который будет использоваться для фильтрации результатов поиска и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>
    
6. <span data-ttu-id="38cd2-136">Результаты поиска отображаются в области **Результатов поиска**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="38cd2-137">Можно выбрать любой или всех пользователей в списке и выполнение задач по настройке для пользователей, которые вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="38cd2-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a><span data-ttu-id="38cd2-138">Добавление и включение новой Скайп для пользователя Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38cd2-138">Add and enable a new Skype for Business Server 2015 user</span></span>
<span data-ttu-id="38cd2-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-139"></span></span>

<span data-ttu-id="38cd2-140">После включения учетной записи пользователя в Active Directory — пользователи и компьютеры, можно использовать Скайп для панели управления Business Server для создания и включения новых Скайп для учетных записей пользователей Business Server 2015, добавив пользователя Active Directory для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38cd2-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server 2015 user accounts by adding an Active Directory user to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="38cd2-141">Также можно использовать командлет, а именно [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="38cd2-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>
  
1. <span data-ttu-id="38cd2-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38cd2-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38cd2-143">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="38cd2-144">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38cd2-145">Нажмите кнопку **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-145">Click **Enable users**.</span></span>
    
5. <span data-ttu-id="38cd2-146">В диалоговом окне **Новый пользователь Lync Server** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-146">On the **New Lync Server User** dialog, click **Add**.</span></span>
    
6. <span data-ttu-id="38cd2-147">В поле **поиска пользователей** , введите или первая часть имени отображать имя, имя, Фамилия, имя учетной записи диспетчера учетных записей (SAM), адрес электронной почты, имя участника пользователя (UPN) или номер телефона учетной записи пользователя Active Directory, которой следует , а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>
    
7. <span data-ttu-id="38cd2-148">В таблице выберите учетную запись, которую требуется добавить к Скайп для Business Server 2015 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-148">In the table, select the account you want to add to Skype for Business Server 2015, and then click **OK**.</span></span>
    
8. <span data-ttu-id="38cd2-149">Назначьте пользователя пулу, укажите дополнительные сведения и назначьте политики для пользователя, который будет и нажмите кнопку **Включить**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="38cd2-150">Отключение или повторное включение учетной записи пользователя, ранее было разрешено для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="38cd2-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="38cd2-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-151"></span></span>

<span data-ttu-id="38cd2-152">Чтобы отключить ранее учетную запись пользователя в Скайп для Business Server без потери Скайп для параметров Business Server, которые настроены для учетной записи пользователя, можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="38cd2-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="38cd2-153">Так как не потерять Скайп для параметров учетной записи пользователя Business Server, можно повторно включить ранее учетную запись пользователя еще раз без необходимости настройки учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="38cd2-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span> 
  
1. <span data-ttu-id="38cd2-154">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38cd2-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38cd2-155">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38cd2-156">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-156">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38cd2-157">В поле **поиска пользователей** , введите или первой части отображаемого имени, имя, Фамилия, имя учетной записи диспетчера учетных записей (SAM), SIP-адрес или строка универсальный код ресурса (URI) учетной записи пользователя, который нужно отключить или повторно включить и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="38cd2-158">В таблице щелкните учетную запись пользователя, который нужно отключить или повторно включить.</span><span class="sxs-lookup"><span data-stu-id="38cd2-158">In the table, click the user account that you want to disable or re-enable.</span></span>
    
6. <span data-ttu-id="38cd2-159">В меню **Действие** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="38cd2-159">On the **Action** menu, do one of the following:</span></span>
    
   - <span data-ttu-id="38cd2-160">Для временного отключения учетной записи пользователя для Скайп Business Server, щелкните **временно отключить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>
    
   - <span data-ttu-id="38cd2-161">Включение учетной записи пользователя для Скайп для Business Server, щелкните **повторно включить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="38cd2-162">Отключение или повторное включение учетных записей пользователей с помощью Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="38cd2-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="38cd2-163">Учетные записи пользователей можно временно отключить и затем их повторного включения, с помощью командлета **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="38cd2-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="38cd2-164">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38cd2-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38cd2-165">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="38cd2-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="38cd2-166">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-166">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account"></a><span data-ttu-id="38cd2-167">Для отключения учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="38cd2-167">To disable a user account</span></span>

- <span data-ttu-id="38cd2-168">Для временного отключения учетной записи пользователя, задайте значение свойства Enabled значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="38cd2-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="38cd2-169">Например:</span><span class="sxs-lookup"><span data-stu-id="38cd2-169">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="38cd2-170">Повторное включение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="38cd2-170">To re-enable a user account</span></span>

- <span data-ttu-id="38cd2-171">Чтобы повторно включить отключенная учетная запись пользователя, задайте значение свойства Enabled значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="38cd2-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="38cd2-172">Например:</span><span class="sxs-lookup"><span data-stu-id="38cd2-172">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="38cd2-173">Для получения дополнительных сведений см раздел справки для командлета [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="38cd2-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="38cd2-174">Отключение пользователя от корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="38cd2-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="38cd2-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-175"></span></span>

<span data-ttu-id="38cd2-176">Используйте следующую процедуру для отключения корпоративной голосовой связи для учетной записи пользователя, который включен для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38cd2-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server 2015.</span></span>
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="38cd2-177">Отключение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="38cd2-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="38cd2-178">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38cd2-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38cd2-179">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38cd2-180">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-180">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38cd2-181">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="38cd2-182">В таблице щелкните учетную запись пользователя, необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="38cd2-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="38cd2-183">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-183">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="38cd2-184">На странице " **Изменение пользователя Lync Server** " в разделе **Телефония**щелкните любой параметр, кроме **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38cd2-185">Чтобы ограничить для пользователя возможность выполнять аудио-или видеовызовы с помощью Lync, в разделе **Телефония**щелкните **Звук и видео отключены**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span> 
  
8. <span data-ttu-id="38cd2-186">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-186">Click **Commit**.</span></span>
    
<span data-ttu-id="38cd2-187">Пользователь является теперь сможет использовать функцию корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="38cd2-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="38cd2-188">Связанные сведения:</span><span class="sxs-lookup"><span data-stu-id="38cd2-188">Related information:</span></span> <br/>[<span data-ttu-id="38cd2-189">Корпоративная голосовая связь и мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="38cd2-189">Enterprise Voice and mobility</span></span>](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="38cd2-190">Включение пользователей для корпоративной голосовой связи в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38cd2-190">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="38cd2-191">Скайп для консоли Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38cd2-191">Skype for Business Server 2015 Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="38cd2-192">Удаление учетной записи пользователя с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="38cd2-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="38cd2-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-193"></span></span>

<span data-ttu-id="38cd2-194">Можно использовать следующую процедуру для удаления добавленной ранее учетной записи в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38cd2-194">You can use the following procedure to remove a previously added user account in Skype for Business Server 2015.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="38cd2-195">Удаление пользователя приведет к потере любые параметры, которые настроены для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="38cd2-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="38cd2-196">Если вы хотите вместо этого временного отключения учетной записи пользователя, видеть, [Отключение или повторное включение учетной записи пользователя, ранее было разрешено Скайп для Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="38cd2-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span> 
  
1. <span data-ttu-id="38cd2-197">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38cd2-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="38cd2-198">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="38cd2-199">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-199">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="38cd2-200">В поле **поиска пользователей** , введите или первой части отображаемого имени, имя, Фамилия, имя учетной записи диспетчера учетных записей (SAM), SIP-адрес или строка универсальный код ресурса (URI) учетной записи пользователя, который нужно отключить или повторно включить и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="38cd2-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="38cd2-201">В таблице щелкните учетную запись пользователя, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="38cd2-201">In the table, click the user account that you want to remove.</span></span>
    
6. <span data-ttu-id="38cd2-202">В меню **Действие** , выберите **Удалить из Lync Server**и диалогового окна появится окно.</span><span class="sxs-lookup"><span data-stu-id="38cd2-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>
    
7. <span data-ttu-id="38cd2-203">В диалоговом окне выберите **кнопку ОК** , чтобы удалить пользователя.</span><span class="sxs-lookup"><span data-stu-id="38cd2-203">From the dialog box, select **OK** to remove the user.</span></span>
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="38cd2-204">Удаление учетных записей пользователей с помощью командлетов Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="38cd2-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="38cd2-205">Учетные записи пользователей можно удалить с помощью командлета Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="38cd2-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="38cd2-206">Этот командлет можно выполнять с Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38cd2-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="38cd2-207">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="38cd2-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="38cd2-208">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="38cd2-208">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-user-account"></a><span data-ttu-id="38cd2-209">Для удаления учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="38cd2-209">To remove a user account</span></span>
<span data-ttu-id="38cd2-210">Для удаления учетной записи пользователя, используйте командлет Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="38cd2-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="38cd2-211">Например:</span><span class="sxs-lookup"><span data-stu-id="38cd2-211">For example:</span></span>
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
<span data-ttu-id="38cd2-212">Для получения дополнительных сведений см раздел справки для командлета [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="38cd2-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38cd2-213">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="38cd2-213">See also</span></span>
<span data-ttu-id="38cd2-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="38cd2-214"></span></span>

#### 

[<span data-ttu-id="38cd2-215">Командлет Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="38cd2-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[<span data-ttu-id="38cd2-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="38cd2-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

