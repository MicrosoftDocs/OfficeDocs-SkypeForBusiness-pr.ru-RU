---
title: Управление учетными записями пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: В разделах этой статьи описывается включение, временное отключение и удаление пользователей Active Directory из Skype для бизнеса Server.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009642"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="93abe-103">Управление учетными записями пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="93abe-104">В разделах этой статьи описывается включение, временное отключение и удаление пользователей Active Directory из Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="93abe-105">Сведения о том, как включить пользователя Active Directory, можно найти в статье [Создание новой учетной записи пользователя](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="93abe-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="93abe-106">Сведения о том, как удалить пользователя Active Directory, можно найти в статье [Удаление учетной записи пользователя](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="93abe-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="93abe-107">Эти процедуры следует выполнять во время периода обслуживания, когда использование Skype для бизнеса будет минимальным.</span><span class="sxs-lookup"><span data-stu-id="93abe-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="93abe-108">Необходимость в ежедневном или еженедельном расписании зависит от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="93abe-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="93abe-109">Эта статья содержит следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="93abe-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="93abe-110">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="93abe-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="93abe-111">Добавление и включение нового пользователя Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="93abe-112">Отключение или повторное включение учетной записи пользователя, для которой ранее была включена поддержка Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="93abe-113">Отключение пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="93abe-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="93abe-114">Удаление учетной записи пользователя с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="93abe-115">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="93abe-115">To search for one or more users</span></span>
<span data-ttu-id="93abe-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-116"><a name="Search"> </a></span></span>

<span data-ttu-id="93abe-117">С помощью результатов поискового запроса можно настроить пользователей Active Directory для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="93abe-118">Вы можете осуществлять поиск пользователей по отображаемому имени, имени, фамилии, имени учетной записи диспетчера учетных записей безопасности, SIP-адресу или универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="93abe-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="93abe-119">Для поиска пользователей можно использовать панель управления Skype для бизнеса Server или оснастку "Active Directory — пользователи и компьютеры".</span><span class="sxs-lookup"><span data-stu-id="93abe-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="93abe-120">В следующей процедуре описывается, как использовать панель управления Skype для бизнеса Server для поиска пользователей.</span><span class="sxs-lookup"><span data-stu-id="93abe-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="93abe-121">В среде с топологией центрального леса результаты поиска могут быть неточными при поиске пользователя по адресу электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="93abe-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="93abe-122">Вместо этого вы можете выполнить поиск пользователей, указав префикс SIP-адреса, например, sip:имя, добавить фильтр поиска и выбрать SIP-адрес с частичным адресом электронной почты, а также воспользоваться командлетом **Get-CSUser**.</span><span class="sxs-lookup"><span data-stu-id="93abe-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="93abe-123">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93abe-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93abe-124">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="93abe-125">В левой панели навигации щелкните элемент **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="93abe-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="93abe-126">В поле **Search users** (Поиск пользователей) полностью или частично введите отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности, SIP-адрес или URI искомой учетной записи пользователя Active Directory, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="93abe-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="93abe-127">(Необязательно) Укажите дополнительные условия поиска, чтобы уменьшить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="93abe-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="93abe-128">а.</span><span class="sxs-lookup"><span data-stu-id="93abe-128">a.</span></span> <span data-ttu-id="93abe-129">Нажмите кнопку со стрелкой развертывания в верхнем правом углу экрана над элементом **Search results** (Результаты поиска) и нажмите кнопку **Add Filter** (Добавить фильтр).</span><span class="sxs-lookup"><span data-stu-id="93abe-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="93abe-130">б.</span><span class="sxs-lookup"><span data-stu-id="93abe-130">b.</span></span> <span data-ttu-id="93abe-131">Укажите свойство пользователя, введя его вручную или щелкнув стрелку в раскрывающемся списке и выбрав свойство в этом списке.</span><span class="sxs-lookup"><span data-stu-id="93abe-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="93abe-132">в.</span><span class="sxs-lookup"><span data-stu-id="93abe-132">c.</span></span> <span data-ttu-id="93abe-133">В списке **Equal to** (Равно) щелкните элемент **Equal to** (Равно) или **Not equal to** (Не равно).</span><span class="sxs-lookup"><span data-stu-id="93abe-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="93abe-134">г.</span><span class="sxs-lookup"><span data-stu-id="93abe-134">d.</span></span> <span data-ttu-id="93abe-135">В текстовом поле введите требуемые условия поиска для фильтрации результатов, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="93abe-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="93abe-p110">Результаты поиска отображаются под элементом **Search Results** (Результаты поиска). Вы можете выбрать любых или всех пользователей в списке и выполнить для них задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="93abe-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="93abe-138">Добавление и включение нового пользователя Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="93abe-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-139"><a name="Add"> </a></span></span>

<span data-ttu-id="93abe-140">После включения учетной записи пользователя в оснастке "Active Directory — пользователи и компьютеры" можно использовать панель управления Skype для бизнеса Server для создания и включения новых учетных записей пользователей Skype для бизнеса Server, добавив пользователя Active Directory в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="93abe-141">Вы также можете использовать командлет, специально [включив параметр – CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="93abe-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="93abe-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93abe-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93abe-143">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="93abe-144">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="93abe-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="93abe-145">Щелкните элемент **Enable users** (Разрешить пользователей).</span><span class="sxs-lookup"><span data-stu-id="93abe-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="93abe-146">В диалоговом окне **New Lync Server User** (Новый пользователь Lync Server) нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="93abe-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="93abe-147">В поле **Search users** (Поиск пользователей) полностью или частично введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности, адрес электронной почты, имя участника-пользователя или номер телефона требуемой учетной записи пользователя Active Directory, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="93abe-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="93abe-148">В таблице выберите учетную запись, которую нужно добавить в Skype для бизнеса Server, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="93abe-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="93abe-149">Назначьте пользователя пулу, укажите дополнительные сведения и назначьте пользователю политики, а затем щелкните элемент **Enable** (Разрешить).</span><span class="sxs-lookup"><span data-stu-id="93abe-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="93abe-150">Отключение или повторное включение учетной записи пользователя, для которой ранее была включена поддержка Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="93abe-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="93abe-152">Вы можете использовать следующую процедуру, чтобы отключить ранее включенную учетную запись пользователя в Skype для бизнеса Server без потери параметров Skype для бизнеса Server, настроенных для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="93abe-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="93abe-153">Так как параметры учетной записи пользователя Skype для бизнеса Server не теряются, вы можете повторно включить учетную запись пользователя, включенную ранее, без необходимости повторной настройки учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="93abe-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="93abe-154">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93abe-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93abe-155">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="93abe-156">На левой панели навигации щелкните пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="93abe-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="93abe-157">В поле **Search users** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, которую требуется отключить или активировать повторно, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="93abe-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="93abe-158">В таблице щелкните учетную запись пользователя, которую необходимо отключить или активировать повторно.</span><span class="sxs-lookup"><span data-stu-id="93abe-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="93abe-159">В меню **Действие** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="93abe-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="93abe-160">Чтобы временно отключить учетную запись пользователя в Skype для бизнеса Server, выберите **временно отключить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="93abe-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="93abe-161">Чтобы включить учетную запись пользователя для Skype для бизнеса Server, нажмите кнопку **повторно включить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="93abe-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="93abe-162">Использование Windows PowerShell для отключения или повторного включения учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="93abe-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="93abe-163">Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set – CsUser** .</span><span class="sxs-lookup"><span data-stu-id="93abe-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="93abe-164">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93abe-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="93abe-165">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к Skype для бизнеса Server приведены в статье ["Быстрый запуск: Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="93abe-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="93abe-166">Этот процесс аналогичен в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="93abe-167">Отключение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="93abe-167">To disable a user account</span></span>

- <span data-ttu-id="93abe-168">Чтобы временно отключить учетную запись пользователя, установите значение свойства "Enabled" равным False ($False).</span><span class="sxs-lookup"><span data-stu-id="93abe-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="93abe-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="93abe-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="93abe-170">Повторное включение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="93abe-170">To re-enable a user account</span></span>

- <span data-ttu-id="93abe-171">Чтобы повторно включить отключенную учетную запись пользователя, установите значение свойства "Enabled" равным True ($True).</span><span class="sxs-lookup"><span data-stu-id="93abe-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="93abe-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="93abe-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="93abe-173">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93abe-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="93abe-174">Отключение пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="93abe-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="93abe-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="93abe-176">Используйте следующую процедуру, чтобы отключить корпоративную голосовую связь для учетной записи пользователя, для которой включена поддержка Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="93abe-177">Отключение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="93abe-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="93abe-178">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93abe-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93abe-179">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="93abe-180">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="93abe-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="93abe-181">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="93abe-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="93abe-182">В таблице щелкните учетную запись пользователя, для которой необходимо включить поддержку корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="93abe-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="93abe-183">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="93abe-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="93abe-184">На странице **Изменение пользователя Lync Server** в разделе **Телефония** щелкните любой параметр, кроме **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="93abe-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93abe-185">Чтобы запретить пользователю совершать аудио-и видеовызовы с помощью Lync, в разделе **телефония**нажмите кнопку **аудио/видео отключена**.</span><span class="sxs-lookup"><span data-stu-id="93abe-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="93abe-186">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="93abe-186">Click **Commit**.</span></span>

<span data-ttu-id="93abe-187">Теперь пользователь не может использовать функцию корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="93abe-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="93abe-188">Связанные сведения:</span><span class="sxs-lookup"><span data-stu-id="93abe-188">Related information:</span></span> <br/>[<span data-ttu-id="93abe-189">Корпоративная голосовая связь и мобильность</span><span class="sxs-lookup"><span data-stu-id="93abe-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="93abe-190">Включение поддержки корпоративной голосовой связи для пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="93abe-191">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="93abe-192">Удаление учетной записи пользователя с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93abe-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="93abe-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="93abe-194">Для удаления ранее добавленной учетной записи пользователя в Skype для бизнеса Server можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="93abe-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="93abe-195">При удалении пользователя будут удалены все параметры, настроенные для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="93abe-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="93abe-196">Если вместо этого вы хотите временно отключить учетную запись пользователя, ознакомьтесь [со статьей отключение или повторное включение учетной записи пользователя, для которой ранее была включена поддержка Skype для бизнеса Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="93abe-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="93abe-197">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93abe-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="93abe-198">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="93abe-199">На левой панели навигации щелкните пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="93abe-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="93abe-200">В поле **Поиск пользователей** введите полностью или только первую часть отображаемого имени, имени, фамилии, имени учетной записи диспетчера учетных записей безопасности (SAM), адреса SIP или строки универсального кода ресурса (URI) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="93abe-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="93abe-201">В таблице щелкните учетную запись пользователя, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="93abe-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="93abe-202">В меню **Макрокоманда** выберите команду **Удалить с сервера Lync Server**; откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="93abe-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="93abe-203">В этом диалоговом окне нажмите кнопку **ОК** для удаления пользователя.</span><span class="sxs-lookup"><span data-stu-id="93abe-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="93abe-204">Удаление учетных записей пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93abe-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="93abe-205">Удалить учетные записи пользователей можно с помощью командлета Disable – CsUser.</span><span class="sxs-lookup"><span data-stu-id="93abe-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="93abe-206">Этот командлет можно запустить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93abe-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="93abe-207">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к Skype для бизнеса Server приведены в статье ["Быстрый запуск: Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="93abe-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="93abe-208">Этот процесс аналогичен в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93abe-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="93abe-209">Удаление учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="93abe-209">To remove a user account</span></span>
<span data-ttu-id="93abe-210">Для удаления учетной записи пользователя используйте командлет Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="93abe-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="93abe-211">Пример:</span><span class="sxs-lookup"><span data-stu-id="93abe-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="93abe-212">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Disable – CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93abe-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="93abe-213">См. также</span><span class="sxs-lookup"><span data-stu-id="93abe-213">See also</span></span>
<span data-ttu-id="93abe-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="93abe-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="93abe-215">Enable — CsUser</span><span class="sxs-lookup"><span data-stu-id="93abe-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="93abe-216">Disable — CsUser</span><span class="sxs-lookup"><span data-stu-id="93abe-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
