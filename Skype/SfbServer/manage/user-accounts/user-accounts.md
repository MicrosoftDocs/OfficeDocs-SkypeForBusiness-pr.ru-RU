---
title: Управление учетными записями пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: В этой статье описано, как включить, временно отключить или удалить пользователей Active Directory из Skype для бизнеса Server.
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992406"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="3833f-103">Управление учетными записями пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="3833f-104">В этой статье описано, как включить, временно отключить или удалить пользователей Active Directory из Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="3833f-105">Сведения о том, как включить пользователя Active Directory, можно найти в разделе [Создание новой учетной записи пользователя](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3833f-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="3833f-106">Сведения о том, как удалить пользователя Active Directory, можно найти в разделе [Удаление учетной записи пользователя](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3833f-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="3833f-107">Эти процедуры должны выполняться в течение периода обслуживания, когда использование Skype для бизнеса является минимальным.</span><span class="sxs-lookup"><span data-stu-id="3833f-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="3833f-108">Необходимость в ежедневном или еженедельном расписании зависит от потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3833f-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="3833f-109">В этой статье описаны следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="3833f-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="3833f-110">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="3833f-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="3833f-111">Добавление и включение нового пользователя Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="3833f-112">Отключение и повторное включение учетной записи пользователя, для которой ранее включена поддержка Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="3833f-113">Отключение пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3833f-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="3833f-114">Удаление учетной записи пользователя с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="3833f-115">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="3833f-115">To search for one or more users</span></span>
<span data-ttu-id="3833f-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-116"></span></span>

<span data-ttu-id="3833f-117">С помощью результатов поискового запроса можно настроить пользователей Active Directory для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="3833f-118">Для поиска пользователей можно использовать отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности (SAM), адрес SIP или универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="3833f-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="3833f-119">Найти пользователей можно с помощью панели управления Skype для бизнеса Server или оснастки Пользователи и компьютеры Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3833f-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="3833f-120">Ниже описана процедура поиска пользователей с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="3833f-121">В среде с центральным топологией леса результаты поиска могут быть неточными при поиске пользователя по адресу электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="3833f-122">Вместо этого вы можете найти пользователей, указав префикс адреса SIP, например SIP: Name, добавьте фильтр поиска и выберите адрес SIP, содержащий частичный адрес электронной почты, или используйте командлет **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="3833f-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="3833f-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3833f-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3833f-124">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3833f-125">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="3833f-126">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, имя учетной записи SAM, адрес SIP или строку URI для учетной записи пользователя, которую вы хотите найти, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="3833f-127">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="3833f-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="3833f-128">a)</span><span class="sxs-lookup"><span data-stu-id="3833f-128">a.</span></span> <span data-ttu-id="3833f-129">Нажмите кнопку со стрелкой "развернуть" в правом верхнем углу экрана над **результатами поиска**и выберите команду " **Добавить фильтр**".</span><span class="sxs-lookup"><span data-stu-id="3833f-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="3833f-130">б)</span><span class="sxs-lookup"><span data-stu-id="3833f-130">b.</span></span> <span data-ttu-id="3833f-131">Введите свойство User, введя его или щелкнув стрелку в раскрывающемся списке для выбора свойства пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="3833f-132">в.</span><span class="sxs-lookup"><span data-stu-id="3833f-132">c.</span></span> <span data-ttu-id="3833f-133">В списке " **равно** " выберите **значение равно** или **не равно**.</span><span class="sxs-lookup"><span data-stu-id="3833f-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="3833f-134">г.</span><span class="sxs-lookup"><span data-stu-id="3833f-134">d.</span></span> <span data-ttu-id="3833f-135">В текстовом поле введите условия поиска, которые нужно использовать, чтобы отфильтровать результаты поиска, и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="3833f-136">Результаты поиска выводятся в разделе **Результаты поиска**.</span><span class="sxs-lookup"><span data-stu-id="3833f-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="3833f-137">Вы можете выбрать одного или всех пользователей из списка и выполнить задачи по настройке выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3833f-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="3833f-138">Добавление и включение нового пользователя Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="3833f-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-139"></span></span>

<span data-ttu-id="3833f-140">После включения учетной записи пользователя в окне пользователи и компьютеры Active Directory вы можете использовать панель управления Skype для бизнеса Server для создания и включения новых учетных записей пользователей в Skype для бизнеса Server, добавив пользователя Active Directory в Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="3833f-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="3833f-141">Вы также можете использовать командлет, специально [включив параметр-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3833f-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="3833f-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3833f-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3833f-143">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3833f-144">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="3833f-145">Нажмите кнопку **включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="3833f-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="3833f-146">В диалоговом окне **Новый пользователь Lync Server** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3833f-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="3833f-147">В поле **Поиск пользователей** введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи безопасности (SAM), адрес электронной почты, имя участника-пользователя (UPN) или номер телефона нужной учетной записи пользователя Active Directory, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="3833f-148">В таблице выберите учетную запись, которую вы хотите добавить в Skype для бизнеса Server, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3833f-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="3833f-149">Назначьте пользователю пул, укажите дополнительные сведения и назначьте политики для нужного пользователя, а затем нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="3833f-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="3833f-150">Отключение и повторное включение учетной записи пользователя, для которой ранее включена поддержка Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="3833f-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-151"></span></span>

<span data-ttu-id="3833f-152">Вы можете использовать описанную ниже процедуру, чтобы отключить учетную запись пользователя в Skype для бизнеса Server, не теряя параметры Skype для бизнеса Server, настроенные для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="3833f-153">Так как вы не потеряли параметры учетной записи пользователя в Skype для бизнеса Server, вы можете снова включить ее еще раз, не требуя повторной настройки учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="3833f-154">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3833f-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3833f-155">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3833f-156">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="3833f-157">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить снова, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="3833f-158">В таблице выберите учетную запись пользователя, которую вы хотите отключить или включить заново.</span><span class="sxs-lookup"><span data-stu-id="3833f-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="3833f-159">В меню **действия** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3833f-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="3833f-160">Чтобы временно отключить учетную запись пользователя в Skype для бизнеса Server, выберите **временно отключить сервер Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3833f-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="3833f-161">Чтобы включить учетную запись пользователя в Skype для бизнеса Server, нажмите кнопку **повторно включить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3833f-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="3833f-162">Использование Windows PowerShell для отключения и повторного включения учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="3833f-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="3833f-163">Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="3833f-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="3833f-164">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3833f-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3833f-165">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="3833f-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3833f-166">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="3833f-167">Отключение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3833f-167">To disable a user account</span></span>

- <span data-ttu-id="3833f-168">Чтобы временно отключить учетную запись пользователя, установите для свойства Enabled значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="3833f-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="3833f-169">Например:</span><span class="sxs-lookup"><span data-stu-id="3833f-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="3833f-170">Повторное включение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3833f-170">To re-enable a user account</span></span>

- <span data-ttu-id="3833f-171">Чтобы повторно включить отключенную учетную запись пользователя, установите для свойства Enabled значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="3833f-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="3833f-172">Например:</span><span class="sxs-lookup"><span data-stu-id="3833f-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="3833f-173">Дополнительные сведения можно найти в разделе справки по командлету [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3833f-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="3833f-174">Отключение пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3833f-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="3833f-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-175"></span></span>

<span data-ttu-id="3833f-176">Чтобы отключить корпоративную голосовую почту для учетной записи пользователя, включенной в Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3833f-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="3833f-177">Отключение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3833f-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="3833f-178">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3833f-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3833f-179">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3833f-180">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="3833f-181">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="3833f-182">В таблице выберите учетную запись пользователя, которую вы хотите включить для корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3833f-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="3833f-183">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="3833f-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="3833f-184">На странице " **изменение пользователя Lync Server** " в разделе **телефония**выберите любой параметр, кроме **корпоративных голосовых сообщений**.</span><span class="sxs-lookup"><span data-stu-id="3833f-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3833f-185">Чтобы запретить пользователю выполнять голосовые и видеозвонки с помощью Lync, в разделе **телефония**выберите пункт **звук и видео отключен**.</span><span class="sxs-lookup"><span data-stu-id="3833f-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="3833f-186">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3833f-186">Click **Commit**.</span></span>

<span data-ttu-id="3833f-187">Теперь пользователь не может использовать функцию голосовой связи в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="3833f-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="3833f-188">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="3833f-188">Related information:</span></span> <br/>[<span data-ttu-id="3833f-189">Корпоративная голосовая связь и мобильность</span><span class="sxs-lookup"><span data-stu-id="3833f-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="3833f-190">Включение пользователей корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="3833f-191">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="3833f-192">Удаление учетной записи пользователя с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3833f-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="3833f-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-193"></span></span>

<span data-ttu-id="3833f-194">Для удаления ранее добавленной учетной записи пользователя в Skype для бизнеса Server можно использовать описанную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="3833f-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="3833f-195">Удаление пользователя приведет к потере всех параметров, настроенных для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="3833f-196">Если вы хотите временно отключить учетную запись пользователя, ознакомьтесь со сведениями [об отключении и повторном включении учетной записи пользователя, которая была включена в Skype для бизнеса Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="3833f-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="3833f-197">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3833f-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3833f-198">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3833f-199">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="3833f-200">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить снова, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="3833f-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="3833f-201">В таблице выберите учетную запись пользователя, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="3833f-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="3833f-202">В меню **действия** выберите команду **удалить из Lync Server**, и появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3833f-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="3833f-203">В диалоговом окне нажмите кнопку **ОК** , чтобы удалить пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="3833f-204">Удаление учетных записей пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3833f-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="3833f-205">Вы можете удалить учетные записи пользователей с помощью командлета Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="3833f-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="3833f-206">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3833f-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="3833f-207">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="3833f-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3833f-208">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3833f-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="3833f-209">Удаление учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3833f-209">To remove a user account</span></span>
<span data-ttu-id="3833f-210">Чтобы удалить учетную запись пользователя, используйте командлет Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="3833f-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="3833f-211">Например:</span><span class="sxs-lookup"><span data-stu-id="3833f-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="3833f-212">Дополнительные сведения можно найти в разделе справки по командлету [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3833f-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="3833f-213">См. также</span><span class="sxs-lookup"><span data-stu-id="3833f-213">See also</span></span>
<span data-ttu-id="3833f-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="3833f-214"></span></span>

[<span data-ttu-id="3833f-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="3833f-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="3833f-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="3833f-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
