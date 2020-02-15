---
title: 'Lync Server 2013: назначение политики голосовой связи на уровне пользователя'
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
ms.openlocfilehash: 029d9c24a5fb460128c523192c7db682e2122370
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030112"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="8573f-102">Назначение политики голосовой связи на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8573f-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8573f-103">Глобальные и на уровне сайта политики голосовой связи автоматически назначаются всем учетным записям пользователей Lync Server 2013, для которых включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8573f-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="8573f-104">Вы также можете назначать политики голосовой связи определенным пользователям с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8573f-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="8573f-105">Используйте процедуры, описанные в этом разделе, чтобы явным образом назначить политики для пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8573f-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="8573f-106">Назначение политики голосовой связи для отдельных пользователей с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="8573f-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8573f-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8573f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8573f-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8573f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8573f-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8573f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8573f-110">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="8573f-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="8573f-111">В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="8573f-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8573f-112">В окне **Изменение пользователя Lync Server** в разделе **Политика голосовой связи** выберите необходимую политику пользователя.</span><span class="sxs-lookup"><span data-stu-id="8573f-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8573f-113">Параметры <STRONG> &lt;автоматического&gt; </STRONG> применения применяют параметры сервера по умолчанию или глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="8573f-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8573f-114">Назначение политики голосовой связи на уровне пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8573f-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8573f-115">Политики голосовой связи на уровне пользователей можно назначить с помощью Windows PowerShell и командлета **Grant – CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="8573f-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="8573f-116">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8573f-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8573f-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="8573f-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="8573f-118">Назначение индивидуальной политики голосовой связи одному пользователю</span><span class="sxs-lookup"><span data-stu-id="8573f-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="8573f-119">Следующая команда назначает политику голосовой связи уровня пользователя с именем RedmondVoicePolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8573f-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="8573f-120">Назначение индивидуальной политики голосовой связи нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="8573f-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="8573f-121">Эта команда назначает политику голосовой связи уровня пользователя с именем FinanceVoicePolicy всем пользователям с учетными записями подразделения Finance в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8573f-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="8573f-122">Для получения дополнительных сведений о параметре OU, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="8573f-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="8573f-123">Отмена назначения политики голосовой связи на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="8573f-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="8573f-p105">Следующая команда отменяет политику голосовой связи уровня пользователя, назначенную пользователю Ken Myer. После отмены политики уровня пользователя к пользователю Ken Myer будет автоматически применяться глобальная политика или локальная политика сайта (если она существует). Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="8573f-p105">The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8573f-127">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="8573f-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="8573f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8573f-128">See Also</span></span>


[<span data-ttu-id="8573f-129">Отключение пользователя для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8573f-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="8573f-130">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="8573f-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

