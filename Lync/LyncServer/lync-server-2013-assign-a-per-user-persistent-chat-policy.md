---
title: 'Lync Server 2013: назначение политики сохраняемого чата на уровне пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134415"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="b70fb-102">Назначение политики сохраняемого чата на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b70fb-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b70fb-103">Политику сохраняемого чата для отдельных пользователей можно назначить с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b70fb-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b70fb-104">Дополнительные сведения о создании политик пользователей для сервера сохраняемого чата приведены [в статье Создание пользовательской политики для сохраняемого чата в Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="b70fb-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="b70fb-105">Назначение политики сохраняемого чата на уровне пользователя с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="b70fb-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b70fb-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b70fb-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b70fb-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b70fb-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b70fb-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b70fb-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b70fb-109">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b70fb-110">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="b70fb-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b70fb-111">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b70fb-112">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b70fb-113">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="b70fb-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b70fb-114">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b70fb-115">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="b70fb-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b70fb-116">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="b70fb-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b70fb-117">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="b70fb-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b70fb-118">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b70fb-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b70fb-119">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-119">Click **Find**.</span></span>

6.  <span data-ttu-id="b70fb-120">Выберите пользователя в результатах поиска, щелкните пункт **Действие**, а затем щелкните **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b70fb-121">Если вы хотите применить одну политику сохраняемого чата к нескольким пользователям, выберите в результатах поиска нескольких пользователей, щелкните пункт <STRONG>Действия</STRONG>, а затем щелкните <STRONG>Назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b70fb-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b70fb-122">В окне **Назначение политик** в разделе **Политика сохраняемого чата** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b70fb-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b70fb-123">Так как существует несколько политик, которые можно настроить с помощью диалогового окна <STRONG>Assign Policies (назначить политики</STRONG> ), <STRONG> &lt;&gt; </STRONG> по умолчанию для каждой политики в диалоговом окне флажок Сохранить как установлен.</span><span class="sxs-lookup"><span data-stu-id="b70fb-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b70fb-124">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="b70fb-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b70fb-125">Выберите \*\* \<автоматически\> \*\* , чтобы разрешить Lync Server 2013 автоматически выбрать политику глобального уровня или, если она определена, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b70fb-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b70fb-126">Щелкните имя политики сохраняемого чата на уровне пользователя, которую вы ранее определили на странице **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b70fb-127">Чтобы вам было легче определить политику, которую нужно назначить пользователю, после выбора названия политики вы можете нажать кнопку <STRONG>Просмотреть</STRONG>, чтобы просмотреть права и разрешения, определенные в рамках этой политики.</span><span class="sxs-lookup"><span data-stu-id="b70fb-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b70fb-128">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b70fb-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b70fb-129">Назначение политики сохраняемого чата на уровне пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b70fb-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b70fb-130">Вы также можете назначить политики сохраняемого чата для отдельных пользователей с помощью командлета **Grant – CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b70fb-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="b70fb-131">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b70fb-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b70fb-132">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="b70fb-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="b70fb-133">Назначение политики сохраняемого чата для отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="b70fb-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="b70fb-134">Следующая команда назначает политику сохраняемого чата RedmondPersistentChatPolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b70fb-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="b70fb-135">Назначение политики сохраняемого чата для отдельных пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="b70fb-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="b70fb-136">Эта команда назначает политику сохраняемого чата на уровне пользователя RedmondUsersPersistentChatPolicy всем пользователям, которые работают в ИТ-отделе.</span><span class="sxs-lookup"><span data-stu-id="b70fb-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="b70fb-137">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b70fb-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="b70fb-138">Отмена назначения политики сохраняемого чата на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="b70fb-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="b70fb-p106">Следующая команда отменяет назначение сохраняемого чата, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="b70fb-p106">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b70fb-142">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b70fb-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b70fb-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b70fb-143">See Also</span></span>


[<span data-ttu-id="b70fb-144">Создание пользовательской политики для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b70fb-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

