---
title: 'Lync Server 2013: Установка ПИН-кода для конференц-связи с телефонным подключением пользователя'
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
ms.openlocfilehash: 2d63156f0eae10d71e0af7721f4e69fe6e2bd8fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510026"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="06b26-102">Установка ПИН-кода для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b26-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06b26-103">_**Последнее изменение темы:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="06b26-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="06b26-104">Чтобы присоединиться к Конференции с телефонным подключением в качестве пользователя, прошедшего проверку подлинности, пользователю Lync Server 2013 с учетными данными доменных служб Active Directory (AD DS) требуется персональный идентификационный номер (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="06b26-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="06b26-105">Если пользователь забыл ПИН-код для конференц-связи с телефонным подключением или не задается ПИН-код с помощью Lync Server, вы можете задать ПИН-код пользователя в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06b26-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="06b26-106">Вы можете автоматически создать ПИН-код или установить его вручную.</span><span class="sxs-lookup"><span data-stu-id="06b26-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06b26-107">Определенные характеристики ПИН-кода, такие как минимальная длина, можно настроить в виде политики.</span><span class="sxs-lookup"><span data-stu-id="06b26-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="06b26-108">Кроме глобальной политики можно настроить политику ПИН-кода для отдельных узлов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="06b26-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="06b26-109">Подробнее о настройке политики ПИН-кодов можно узнать <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">в статье Настройка правил ПИН-кодов для конференц-связи с телефонным подключением в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="06b26-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="06b26-110">Установка ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="06b26-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="06b26-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="06b26-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="06b26-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06b26-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="06b26-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="06b26-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="06b26-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="06b26-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="06b26-115">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="06b26-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="06b26-116">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="06b26-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="06b26-117">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="06b26-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="06b26-118">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="06b26-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="06b26-119">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="06b26-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="06b26-120">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="06b26-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="06b26-121">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="06b26-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="06b26-122">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="06b26-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="06b26-123">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="06b26-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="06b26-124">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="06b26-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06b26-p104">Если ПИН заблокирован, необходимо его разблокировать, чтобы установить его. Для разблокировки ПИН-кода, щелкните имя пользователя, выберите параметр <STRONG>Действие</STRONG>, а затем нажмите кнопку <STRONG>Разблокировать ПИН-код</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="06b26-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="06b26-127">Выберите пользователя в результатах поиска щелкните **Действие**, а затем выберите **Установить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="06b26-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="06b26-128">В диалоговом окне **Установить ПИН-код** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="06b26-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="06b26-129">Чтобы разрешить Lync Server 2013 создавать ПИН-код пользователя, выберите **автоматически создать действительный ПИН-код** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="06b26-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="06b26-130">Чтобы создать собственный ПИН-код, щелкните **Вручную ввести определенный ПИН-код**, щелкните текстовое поле, а затем введите ПИН-код, который соответствует требованиям, указанным в параметрах политики ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="06b26-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="06b26-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="06b26-131">Click **OK**.</span></span>

9.  <span data-ttu-id="06b26-132">В диалоговом окне **Установить ПИН-код** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="06b26-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="06b26-133">Установите флажок **Показывать ПИН-код**, чтобы увидеть ПИН-код, а затем скопируйте и сообщите его пользователю с помощью предпочитаемого в организации метода.</span><span class="sxs-lookup"><span data-stu-id="06b26-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="06b26-p105">Щелкните **Открыть приложение электронной почты, чтобы отправить новый ПИН-код пользователю** для отправки ПИН-кода по электронной почте. Если клиентом электронной почты является Microsoft Office Outlook, ПИН-код будет автоматически скопирован в новое сообщение электронной почты. Если вы используете другой почтовый клиент, установите флажок **Показывать ПИН-код**, чтобы отобразить ПИН-код, а затем скопируйте его в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="06b26-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="06b26-137">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="06b26-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="06b26-138">Назначение ПИН-кода пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06b26-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="06b26-139">Вы также можете назначить PIN-коды с помощью командлета Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="06b26-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="06b26-140">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06b26-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="06b26-141">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="06b26-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="06b26-142">Автоматическое назначение ПИН-кода пользователю</span><span class="sxs-lookup"><span data-stu-id="06b26-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="06b26-143">Следующая команда служит для назначения GBY-кода пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="06b26-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="06b26-144">Так как параметр PIN не включен, Lync Server автоматически создаст и присвоит PIN-код.</span><span class="sxs-lookup"><span data-stu-id="06b26-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="06b26-145">Назначение пользователю определенного ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="06b26-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="06b26-146">Эта команда задействует параметр Pin для назначения ПИН-кода 121989 to the user Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="06b26-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="06b26-147">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="06b26-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06b26-148">См. также</span><span class="sxs-lookup"><span data-stu-id="06b26-148">See Also</span></span>


<span data-ttu-id="06b26-149">[Номер доступа для телефонного подключения](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="06b26-149">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="06b26-150">Настройка правил ПИН-кодов для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b26-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

