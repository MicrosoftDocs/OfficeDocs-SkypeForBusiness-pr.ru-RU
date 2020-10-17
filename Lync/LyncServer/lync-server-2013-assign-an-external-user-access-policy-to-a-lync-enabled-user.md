---
title: 'Lync Server 2013: назначение политики доступа внешних пользователей пользователю с включенной поддержкой Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7b1f9436695c5bd455c376d9c75add996be28f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508946"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="08624-102">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08624-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08624-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="08624-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="08624-104">Если для пользователя включена поддержка Lync Server, вы можете настроить федерацию SIP, Федерацию XMPP, удаленный доступ пользователей и подключение к общедоступным обменам мгновенными сообщениями на панели управления Lync Server, применив соответствующие политики к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="08624-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="08624-105">Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю до того, как пользователь сможет подключиться к Lync Server из удаленного расположения и совместно работать с внутренними пользователями из удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="08624-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08624-106">Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии.</span><span class="sxs-lookup"><span data-stu-id="08624-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="08624-107">Дополнительные сведения: <A href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки доступа внешних пользователей в Lync server 2013</A> в документации по развертыванию или <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">управлении Федерации и внешним доступом к Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="08624-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="08624-108">Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="08624-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="08624-109">Применение политики доступа внешних пользователей к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="08624-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="08624-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="08624-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="08624-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08624-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08624-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="08624-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08624-113">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="08624-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="08624-114">В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="08624-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="08624-115">В окне **Изменение пользователя Lync Server** в разделе **Политика внешнего доступа** выберите политику доступа внешних пользователей, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="08624-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08624-116">Параметры <STRONG> &lt; автоматического &gt; </STRONG> применения применяют параметры сервера по умолчанию или глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="08624-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="08624-117">Назначение Per-User политикам внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08624-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="08624-118">Политики внешнего доступа на уровне пользователей можно назначить с помощью Windows PowerShell и командлета Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="08624-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="08624-119">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08624-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="08624-120">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="08624-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="08624-121">Назначение политики внешнего доступа на уровне пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="08624-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="08624-122">Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="08624-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="08624-123">Назначение политики внешнего доступа на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="08624-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="08624-124">Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08624-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="08624-125">Для получения дополнительных сведений о параметре OU, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="08624-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="08624-126">Отмена назначения политики внешнего доступа на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="08624-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="08624-p106">Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="08624-p106">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="08624-130">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="08624-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

