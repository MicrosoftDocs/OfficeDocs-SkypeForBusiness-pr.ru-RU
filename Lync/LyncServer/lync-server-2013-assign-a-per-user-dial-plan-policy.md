---
title: 'Lync Server 2013: назначение политики абонентской группы на уровне пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134445"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="02a12-102">Назначение политики абонентской группы на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a12-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="02a12-p101">Чтобы выполнить настройку учетной записи пользователя как для пользователей корпоративной голосовой связи, так и для пользователей конференц-связи с телефонным подключением, этот пользователь должен быть назначен соответствующей абонентской группе. Если абонентская группа уровня пользователей не будет назначена явным образом, для учетных записей пользователей будет автоматически использоваться глобальная абонентская группа или абонентская группа уровня сайта (если она существует). Если требуется использовать глобальную абонентскую группу или абонентскую группу уровня сайта для всех пользователей, включенных для корпоративной голосовой связи, этот раздел можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="02a12-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="02a12-106">Назначение абонентской группы с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a12-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="02a12-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="02a12-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02a12-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02a12-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02a12-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02a12-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02a12-110">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="02a12-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="02a12-111">В поле **Поиск пользователей** введите полностью или только первую часть отображаемого имени, имени, фамилии, имени учетной записи диспетчера учетных записей безопасности (SAM), адреса SIP или строки универсального кода ресурса (URI) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="02a12-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="02a12-112">В таблице выберите учетную запись пользователя, которого требуется назначить абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="02a12-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="02a12-113">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="02a12-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="02a12-114">На странице **Изменение пользователя Lync Server** в разделе **Телефония** выберите **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="02a12-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="02a12-115">Щелкните **Политика абонентской группы**, а затем выберите нужную абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="02a12-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="02a12-116">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="02a12-116">Click **Commit**.</span></span>

<span data-ttu-id="02a12-117">Более подробную информацию о настройке абонентских группы можно узнать в статье [Настройка абонентских группы в Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="02a12-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02a12-118">Назначение абонентской группы на уровне пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02a12-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02a12-119">Абонентские группы для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета **Grant – CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="02a12-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="02a12-120">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02a12-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02a12-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="02a12-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="02a12-122">Назначение абонентской группы отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="02a12-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="02a12-123">Следующая команда назначает абонентскую группу на уровне пользователей RedmondDialPlan пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="02a12-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="02a12-124">Назначение абонентской группы на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="02a12-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="02a12-125">Эта команда назначает абонентскую группу на уровне пользователей RedmondDialPlan всем пользователям, работающим в городе Редмонд (Redmond).</span><span class="sxs-lookup"><span data-stu-id="02a12-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="02a12-126">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="02a12-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="02a12-127">Отмена назначения абонентской группы на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="02a12-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="02a12-p105">Следующая команда отменяет назначение абонентской группы на уровне пользователей, ранее назначенной пользователю Ken Myer. После отмены назначения абонентской группы на уровне пользователей управление пользователем Ken Myer автоматически осуществляется с помощью глобальной абонентской группы, его локальной абонентской группы уровня сайта (если она существует) или абонентской группы уровня службы, назначенной его службе Registrar или шлюзу ТСОП. Абонентская группа уровня службы обладает приоритетом по отношению к абонентской группе уровня сайта, а абонентская группа уровня сайта — по отношению к глобальной абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="02a12-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="02a12-131">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="02a12-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="02a12-132">См. также</span><span class="sxs-lookup"><span data-stu-id="02a12-132">See Also</span></span>


[<span data-ttu-id="02a12-133">Настройка абонентских планов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a12-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="02a12-134">Учетные записи пользователей, включенные для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a12-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

