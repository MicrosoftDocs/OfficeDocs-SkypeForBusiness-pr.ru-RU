---
title: Задать пользователя телефонных конференций ПИН-код в Скайп для Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Сводка: Set пользователя телефонных конференций ПИН-кода для Скайп for Business Server.'
ms.openlocfilehash: 62b38b8ef15aa2283b66fc18abf5ec0e84e64870
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877393"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="35d9b-103">Задать пользователя телефонных конференций ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="35d9b-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="35d9b-104">**Сводка:** Задайте пользователя телефонных конференций ПИН-кода для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="35d9b-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="35d9b-105">Чтобы присоединиться к конференции номера в качестве пользователя с разрешением, Скайп для пользователя Business Server с использованием учетных данных доменных служб Active Directory (AD DS) требуется персонального идентификационного номера (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="35d9b-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="35d9b-106">Если пользователь забудет конференц связи с телефонным ПИН-код или не задано ПИН-кода с помощью Скайп for Business Server, можно задать ПИН-код пользователя из Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="35d9b-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="35d9b-107">You can automatically generate the PIN or create one manually.</span><span class="sxs-lookup"><span data-stu-id="35d9b-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35d9b-p102">Определенные характеристики ПИН-кода, такие как минимальная длина, можно настроить в виде политики. Кроме глобальной политики можно настроить политику ПИН-кода для отдельных узлов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="35d9b-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="35d9b-110">Чтобы задать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="35d9b-110">To set a user's PIN</span></span>

1. <span data-ttu-id="35d9b-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35d9b-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35d9b-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="35d9b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="35d9b-113">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="35d9b-114">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="35d9b-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="35d9b-115">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="35d9b-116">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="35d9b-117">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="35d9b-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="35d9b-118">а.</span><span class="sxs-lookup"><span data-stu-id="35d9b-118">a.</span></span> <span data-ttu-id="35d9b-119">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="35d9b-120">б.</span><span class="sxs-lookup"><span data-stu-id="35d9b-120">b.</span></span> <span data-ttu-id="35d9b-121">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="35d9b-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="35d9b-122">в.</span><span class="sxs-lookup"><span data-stu-id="35d9b-122">c.</span></span> <span data-ttu-id="35d9b-123">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="35d9b-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="35d9b-124">г.</span><span class="sxs-lookup"><span data-stu-id="35d9b-124">d.</span></span> <span data-ttu-id="35d9b-125">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="35d9b-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35d9b-126">Чтобы добавить в запрос дополнительные условия поиска, щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="35d9b-127">e.</span><span class="sxs-lookup"><span data-stu-id="35d9b-127">e.</span></span> <span data-ttu-id="35d9b-128">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35d9b-p108">Если ПИН-код заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН-код, щелкните **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="35d9b-131">Выберите пользователя в результатах поиска щелкните **Действие**, а затем выберите **Установить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="35d9b-132">В диалоговом окне **Установить ПИН-код** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="35d9b-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="35d9b-133">Чтобы разрешить Скайп для Business Server для создания ПИН-код пользователя, выберите **автоматически создавать допустимый ПИН-кода** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="35d9b-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="35d9b-134">Чтобы создать собственный ПИН-код, щелкните **Ввести ПИН-код вручную**, щелкните текстовое поле, а затем введите ПИН-код, который соответствует требованиям, указанным в параметрах политики ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="35d9b-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="35d9b-135">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="35d9b-136">В диалоговом окне **Установить ПИН-код** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="35d9b-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="35d9b-137">Установите флажок **Показывать ПИН-код**, чтобы увидеть ПИН-код, а затем скопируйте и сообщите его пользователю с помощью предпочитаемого в организации метода.</span><span class="sxs-lookup"><span data-stu-id="35d9b-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="35d9b-p109">Щелкните **Открыть мое приложение электронной почты для отправки нового ПИН-кода пользователю** для отправки ПИН-кода по электронной почте. Если клиентом электронной почты является Microsoft Office Outlook, ПИН-код будет автоматически скопирован в новое сообщение электронной почты. Если вы используете другой почтовый клиент, установите флажок **Показывать ПИН-код**, чтобы отобразить ПИН-код, а затем скопируйте его в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="35d9b-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="35d9b-141">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="35d9b-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="35d9b-142">Назначение ПИН-код пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35d9b-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="35d9b-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="35d9b-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="35d9b-144">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35d9b-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="35d9b-145">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="35d9b-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="35d9b-146">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="35d9b-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="35d9b-147">Автоматическое назначение ПИН-кода пользователю</span><span class="sxs-lookup"><span data-stu-id="35d9b-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="35d9b-148">Следующая команда служит для назначения GBY-кода пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="35d9b-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="35d9b-149">Так как не задан параметр ПИН-код, Скайп для Business Server автоматически создавать и назначение ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="35d9b-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="35d9b-150">Назначение пользователю определенного ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="35d9b-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="35d9b-151">Эта команда задействует параметр Pin для назначения ПИН-кода 121989 пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="35d9b-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="35d9b-152">Для получения дополнительных сведений см раздел справки для командлета [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="35d9b-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

