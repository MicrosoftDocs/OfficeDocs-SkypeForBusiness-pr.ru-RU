---
title: Установите ПИН-код телефонных разговоров пользователя в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: Сводка. Установите ПИН-код телефонных разговоров пользователя для Skype для бизнеса Server.
ms.openlocfilehash: c34e895471fdffb13a4cdb10806bd07146474e44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119558"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="d646c-103">Установите ПИН-код телефонных разговоров пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d646c-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="d646c-104">**Сводка:** Установите пин-код телефонных разговоров пользователя для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d646c-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="d646c-105">Чтобы присоединиться к телефонной конференции в качестве пользователя с проверкой подлинности, пользователю Skype для бизнеса Server с учетными данными Active Directory Domain Services (AD DS) требуется личный идентификационный номер (PIN).</span><span class="sxs-lookup"><span data-stu-id="d646c-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="d646c-106">Если пользователь забывает ПИН-код телефонных разговоров или не установил ПИН-код с помощью Skype для бизнеса Server, вы можете настроить ПИН-код пользователя из панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="d646c-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d646c-107">Вы можете автоматически создать ПИН-код или установить его вручную.</span><span class="sxs-lookup"><span data-stu-id="d646c-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d646c-108">Определенные характеристики ПИН-кода, такие как минимальная длина, можно настроить в виде политики.</span><span class="sxs-lookup"><span data-stu-id="d646c-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="d646c-109">Кроме глобальной политики можно настроить политику ПИН-кода для отдельных узлов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="d646c-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="d646c-110">Настройка ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="d646c-110">To set a user's PIN</span></span>

1. <span data-ttu-id="d646c-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d646c-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d646c-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="d646c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d646c-113">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d646c-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d646c-114">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="d646c-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="d646c-115">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d646c-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="d646c-116">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d646c-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="d646c-117">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="d646c-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="d646c-118">а)</span><span class="sxs-lookup"><span data-stu-id="d646c-118">a.</span></span> <span data-ttu-id="d646c-119">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d646c-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="d646c-120">б)</span><span class="sxs-lookup"><span data-stu-id="d646c-120">b.</span></span> <span data-ttu-id="d646c-121">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="d646c-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="d646c-122">в.</span><span class="sxs-lookup"><span data-stu-id="d646c-122">c.</span></span> <span data-ttu-id="d646c-123">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="d646c-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="d646c-124">г.</span><span class="sxs-lookup"><span data-stu-id="d646c-124">d.</span></span> <span data-ttu-id="d646c-125">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="d646c-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d646c-126">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d646c-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="d646c-127">д.</span><span class="sxs-lookup"><span data-stu-id="d646c-127">e.</span></span> <span data-ttu-id="d646c-128">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d646c-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d646c-p108">Если ПИН заблокирован, необходимо его разблокировать, чтобы установить его. Для разблокировки ПИН-кода, щелкните имя пользователя, выберите параметр **Действие**, а затем нажмите кнопку **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d646c-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="d646c-131">Выберите пользователя в результатах поиска щелкните **Действие**, а затем выберите **Установить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d646c-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="d646c-132">В диалоговом окне **Установить ПИН-код** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d646c-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="d646c-133">Чтобы разрешить Skype для бизнес-сервера создавать ПИН-код пользователя, выберите автоматически создать **допустимый ПИН-код** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d646c-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="d646c-134">Чтобы создать собственный ПИН-код, щелкните **Вручную ввести определенный ПИН-код**, щелкните текстовое поле, а затем введите ПИН-код, который соответствует требованиям, указанным в параметрах политики ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="d646c-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="d646c-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d646c-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="d646c-136">В диалоговом окне **Установить ПИН-код** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d646c-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="d646c-137">Установите флажок **Показывать ПИН-код**, чтобы увидеть ПИН-код, а затем скопируйте и сообщите его пользователю с помощью предпочитаемого в организации метода.</span><span class="sxs-lookup"><span data-stu-id="d646c-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="d646c-p109">Щелкните **Открыть приложение электронной почты, чтобы отправить новый ПИН-код пользователю** для отправки ПИН-кода по электронной почте. Если клиентом электронной почты является Microsoft Office Outlook, ПИН-код будет автоматически скопирован в новое сообщение электронной почты. Если вы используете другой почтовый клиент, установите флажок **Показывать ПИН-код**, чтобы отобразить ПИН-код, а затем скопируйте его в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d646c-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="d646c-141">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d646c-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d646c-142">Назначение ПИН-кода пользователя с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="d646c-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d646c-143">Вы также можете назначить ПИН-коды, используя Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="d646c-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="d646c-144">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d646c-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d646c-145">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="d646c-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d646c-146">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="d646c-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="d646c-147">Автоназначить ПИН-код пользователю</span><span class="sxs-lookup"><span data-stu-id="d646c-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="d646c-148">Следующая команда служит для назначения GBY-кода пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d646c-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="d646c-149">Так как параметр Pin не включен, Skype для бизнеса Server автоматически создает и назначает ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="d646c-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="d646c-150">Назначение определенного ПИН-номера пользователю</span><span class="sxs-lookup"><span data-stu-id="d646c-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="d646c-151">Эта команда задействует параметр Pin для назначения ПИН-кода 121989 to the user Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d646c-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="d646c-152">Дополнительные сведения см. в разделе Справка для [cmdlet Set-CsClientPin.](/powershell/module/skype/set-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d646c-152">For more information, see the help topic for the [Set-CsClientPin](/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
