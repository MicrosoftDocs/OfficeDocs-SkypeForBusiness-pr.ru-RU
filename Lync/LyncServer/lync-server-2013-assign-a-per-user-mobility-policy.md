---
title: 'Lync Server 2013: назначение политики мобильности на уровне пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20b5929959e87f4a39c69ab09f7836a471e16b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722849"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="9fe48-102">Назначение политики мобильности на мобильные пользователи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe48-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9fe48-103">Политика мобильности — это один из параметров учетной записи пользователя, которую можно настроить в управляющей панели Lync Server или в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9fe48-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="9fe48-104">Назначение политики мобильности для пользователей с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9fe48-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9fe48-105">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9fe48-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fe48-106">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fe48-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9fe48-107">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9fe48-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9fe48-108">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9fe48-109">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="9fe48-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9fe48-110">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9fe48-111">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9fe48-112">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="9fe48-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9fe48-113">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9fe48-114">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="9fe48-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9fe48-115">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="9fe48-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9fe48-116">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9fe48-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9fe48-117">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9fe48-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="9fe48-118">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-118">Click **Find**.</span></span>

6.  <span data-ttu-id="9fe48-119">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="9fe48-120">Если вы хотите применить одну и ту же политику мобильной связи для нескольких пользователей, выберите в результатах поиска нескольких пользователей, а затем нажмите кнопку <STRONG>действия</STRONG>и выберите команду <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9fe48-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="9fe48-121">В разделе **назначение политик**в группе **Политика мобильных устройств**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9fe48-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe48-122">Поскольку есть несколько политик, которые можно настроить в разделе <STRONG>назначение политик</STRONG>, <STRONG> &lt;&gt; </STRONG> для каждой из них в диалоговом окне по умолчанию выбран параметр Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="9fe48-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="9fe48-123">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="9fe48-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="9fe48-124">Выберите \*\* \<автоматически\> \*\* , чтобы разрешить Lync Server 2013 автоматически выбрать политику глобального уровня или, если она определена, политику на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9fe48-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="9fe48-125">Щелкните имя политики мобильной связи на мобильном уровне, определенную на странице " **Политика Mobility Service** ".</span><span class="sxs-lookup"><span data-stu-id="9fe48-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9fe48-126">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="9fe48-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="9fe48-127">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9fe48-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9fe48-128">Назначение политики мобильности для пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fe48-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9fe48-129">Вы можете назначать политики мобильности для пользователей с помощью Windows PowerShell и командлета **Grant-ксмобилитиполици** .</span><span class="sxs-lookup"><span data-stu-id="9fe48-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="9fe48-130">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fe48-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9fe48-131">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fe48-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="9fe48-132">Назначение индивидуальной политики мобильности для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="9fe48-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="9fe48-133">Следующая команда назначает пользователю Редмондмобилитиполициную политику мобильности для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9fe48-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="9fe48-134">Назначение политики мобильности для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="9fe48-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="9fe48-135">Следующая команда назначает политику мобильности пользователей Редмондмобилитиполици всем пользователям, которым в данный момент назначена политика Норсамерикамобилитиполици.</span><span class="sxs-lookup"><span data-stu-id="9fe48-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="9fe48-136">Дополнительные сведения о параметре фильтрации, используемом в этой команде, приведены в разделе [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="9fe48-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="9fe48-137">Отмена назначения политики мобильности на уровне пользователей</span><span class="sxs-lookup"><span data-stu-id="9fe48-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="9fe48-138">Следующая команда отменяет назначение любой политики мобильной связи, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="9fe48-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="9fe48-139">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="9fe48-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="9fe48-140">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="9fe48-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9fe48-141">Подробности можно найти в разделе [Grant-ксмобилитиполици](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="9fe48-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="9fe48-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9fe48-142">See Also</span></span>


[<span data-ttu-id="9fe48-143">Настройка политики мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe48-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

