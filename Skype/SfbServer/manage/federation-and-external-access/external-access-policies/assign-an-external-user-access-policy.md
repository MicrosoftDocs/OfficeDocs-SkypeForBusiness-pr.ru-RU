---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если для пользователя включена поддержка Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями на панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043681"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="24a28-103">Назначение политики доступа внешних пользователей для пользователя с включенной поддержкой Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="24a28-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="24a28-104">Если для пользователя включена поддержка Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями на панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="24a28-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="24a28-105">Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю до того, как пользователь сможет подключиться к Skype для бизнеса Server из удаленного расположения и сотрудничать с внутренними пользователями из удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="24a28-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="24a28-106">Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии.</span><span class="sxs-lookup"><span data-stu-id="24a28-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="24a28-107">Дополнительные сведения см [в статье Управление федерациями и внешним доступом к Skype для бизнеса Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="24a28-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="24a28-108">Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="24a28-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="24a28-109">Применение политики доступа внешних пользователей к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="24a28-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="24a28-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24a28-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24a28-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="24a28-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="24a28-112">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="24a28-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="24a28-113">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="24a28-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="24a28-114">В разделе **изменение пользователя Skype для бизнеса Server** в разделе **Политика внешнего доступа**выберите пользовательскую политику, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="24a28-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="24a28-115">Параметры \*\* \<автоматического>\*\* применяют параметры сервера по умолчанию или глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="24a28-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24a28-116">Назначение политик внешнего доступа для отдельных пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24a28-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24a28-117">Политики внешнего доступа на уровне пользователей можно назначить с помощью Windows PowerShell и командлета Grant – CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="24a28-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="24a28-118">Этот командлет можно запустить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24a28-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="24a28-119">Назначение политики внешнего доступа на уровне пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="24a28-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="24a28-120">Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="24a28-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="24a28-121">Назначение политики внешнего доступа на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="24a28-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="24a28-122">Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24a28-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="24a28-123">Для получения дополнительных сведений о параметре OU, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="24a28-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="24a28-124">Отмена назначения политики внешнего доступа на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="24a28-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="24a28-p105">Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="24a28-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="24a28-128">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="24a28-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


