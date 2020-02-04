---
title: 'Lync Server 2013: Установка ПИН-кода конференц-связи с телефонным подключением пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab97b3efe350ef82527262103e9b00104990245a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="7ef23-102">Установка ПИН-кода конференц-связи с телефонным подключением пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ef23-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ef23-103">_**Тема последнего изменения:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="7ef23-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="7ef23-104">Чтобы присоединиться к Конференции с телефонным подключением в качестве пользователя, прошедшего проверку подлинности, пользователю Lync Server 2013 с учетными данными доменных служб Active Directory (AD DS) требуется персональный идентификационный номер (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="7ef23-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="7ef23-105">Если пользователь забывает PIN-код для Конференции с телефонным подключением или вы не настроили ПИН-код с помощью Lync Server, вы можете задать PIN-код пользователя на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ef23-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="7ef23-106">You can automatically generate the PIN or create one manually.</span><span class="sxs-lookup"><span data-stu-id="7ef23-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ef23-107">Определенные характеристики ПИН-кода, такие как минимальная длина, можно настроить в виде политики.</span><span class="sxs-lookup"><span data-stu-id="7ef23-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="7ef23-108">Кроме глобальной политики можно настроить политику ПИН-кода для отдельных узлов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ef23-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="7ef23-109">Подробные сведения о настройке политики ПИН-кода можно найти <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">в разделе Настройка правил доступа к персональному идентификационному номеру (PIN) в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ef23-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="7ef23-110">Установка ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="7ef23-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="7ef23-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7ef23-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ef23-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ef23-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ef23-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7ef23-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ef23-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7ef23-115">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="7ef23-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="7ef23-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="7ef23-117">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="7ef23-118">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="7ef23-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="7ef23-119">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="7ef23-120">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="7ef23-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="7ef23-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="7ef23-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="7ef23-122">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7ef23-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="7ef23-123">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7ef23-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="7ef23-124">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ef23-p104">Если ПИН-код заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН-код, щелкните <STRONG>Действие</STRONG>, затем <STRONG>Разблокировать ПИН-код</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7ef23-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="7ef23-127">Выберите пользователя в результатах поиска щелкните **Действие**, а затем выберите **Установить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="7ef23-128">В диалоговом окне **Установить ПИН-код** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7ef23-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="7ef23-129">Чтобы позволить Lync Server 2013 создать PIN-код пользователя, выберите **автоматически создать допустимый ПИН-код** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7ef23-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="7ef23-130">Чтобы создать собственный ПИН-код, щелкните **Ввести ПИН-код вручную**, щелкните текстовое поле, а затем введите ПИН-код, который соответствует требованиям, указанным в параметрах политики ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="7ef23-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="7ef23-131">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-131">Click **OK**.</span></span>

9.  <span data-ttu-id="7ef23-132">В диалоговом окне **Установить ПИН-код** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7ef23-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="7ef23-133">Установите флажок **Показывать ПИН-код**, чтобы увидеть ПИН-код, а затем скопируйте и сообщите его пользователю с помощью предпочитаемого в организации метода.</span><span class="sxs-lookup"><span data-stu-id="7ef23-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="7ef23-p105">Щелкните **Открыть мое приложение электронной почты для отправки нового ПИН-кода пользователю** для отправки ПИН-кода по электронной почте. Если клиентом электронной почты является Microsoft Office Outlook, ПИН-код будет автоматически скопирован в новое сообщение электронной почты. Если вы используете другой почтовый клиент, установите флажок **Показывать ПИН-код**, чтобы отобразить ПИН-код, а затем скопируйте его в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7ef23-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="7ef23-137">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7ef23-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ef23-138">Назначение PIN-кода пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef23-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7ef23-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ef23-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="7ef23-140">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ef23-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7ef23-141">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ef23-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="7ef23-142">Автоматическое назначение ПИН-кода пользователю</span><span class="sxs-lookup"><span data-stu-id="7ef23-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="7ef23-143">Следующая команда служит для назначения GBY-кода пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7ef23-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="7ef23-144">Так как параметр PIN-кода не указан, Lync Server автоматически создаст и назначает PIN-код.</span><span class="sxs-lookup"><span data-stu-id="7ef23-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="7ef23-145">Назначение пользователю определенного ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="7ef23-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="7ef23-146">Эта команда задействует параметр Pin для назначения ПИН-кода 121989 пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7ef23-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="7ef23-147">Дополнительные сведения можно найти в разделе справки по командлету [Set-ксклиентпин](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="7ef23-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ef23-148">См. также</span><span class="sxs-lookup"><span data-stu-id="7ef23-148">See Also</span></span>


<span data-ttu-id="7ef23-149">[Номер доступа для телефонного подключения](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ef23-149">[Dial-in Access Number](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="7ef23-150">Настройка правил для личного идентификационного номера конференц-связи с телефонным подключением (PIN) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ef23-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

