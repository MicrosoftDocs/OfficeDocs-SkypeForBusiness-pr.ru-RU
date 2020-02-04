---
title: 'Lync Server 2013: назначение политики голосовой связи для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723409"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="cf433-102">Назначение политики голосовой связи для пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf433-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="cf433-103">Глобальные и высокоуровневые политики на уровне сайта автоматически назначаются всем учетным записям пользователей Lync Server 2013, которые включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cf433-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="cf433-104">Вы также можете назначать политики голосовой связи определенным пользователям с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf433-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="cf433-105">С помощью процедур, описанных в этом разделе, явным образом назначьте политики для пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf433-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="cf433-106">Назначение особой политики голосовой связи с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="cf433-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cf433-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf433-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cf433-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf433-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf433-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf433-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf433-110">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="cf433-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="cf433-111">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="cf433-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cf433-112">В диалоговом окне **изменение пользователя Lync Server** в разделе **политика голосовой связи**выберите политику пользователей, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="cf433-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="cf433-113">Параметры <STRONG> &lt;автоматической&gt; </STRONG> настройки применяются к параметрам сервера или глобальной политики, используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf433-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cf433-114">Назначение политики голосовой почты для пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf433-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cf433-115">Вы можете назначать политики голосовой связи для пользователей с помощью Windows PowerShell и командлета **Grant-ксвоицеполици** .</span><span class="sxs-lookup"><span data-stu-id="cf433-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="cf433-116">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf433-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cf433-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf433-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="cf433-118">Назначение политики голосовой почты для отдельного пользователя</span><span class="sxs-lookup"><span data-stu-id="cf433-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="cf433-119">Следующая команда назначает пользовательскую политику голосовой связи "на пользователя", Редмондвоицеполици с пользователем Кен мер.</span><span class="sxs-lookup"><span data-stu-id="cf433-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="cf433-120">Назначение политики голосовой почты для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="cf433-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="cf433-121">Эта команда назначает политику голосовой связи для пользователя Финанцевоицеполици всем пользователям, у которых есть учетные записи в подразделении "Финансы" в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf433-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="cf433-122">Дополнительные сведения о параметре OU, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="cf433-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="cf433-123">Отмена назначения политики голосовой почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="cf433-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="cf433-124">Следующая команда отменяет назначение любой политики голосовой почты для каждого пользователя, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="cf433-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="cf433-125">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="cf433-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="cf433-126">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="cf433-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="cf433-127">Дополнительные сведения можно найти в разделе справки о командлете [Grant-ксвоицеполици](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="cf433-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf433-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cf433-128">See Also</span></span>


[<span data-ttu-id="cf433-129">Отключение пользователя для корпоративного голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf433-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="cf433-130">командная консоль Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf433-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

