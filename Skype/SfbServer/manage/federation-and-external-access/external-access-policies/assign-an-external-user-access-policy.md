---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если для пользователя включена служба Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями в панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям.
ms.openlocfilehash: 25e9a63363dc4f982e142defd2164c2423471961
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826629"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="00d35-103">Назначение политики доступа внешних пользователей пользователю, включенного в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="00d35-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="00d35-104">Если для пользователя включена служба Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями в панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="00d35-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="00d35-105">Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю, прежде чем пользователь сможет подключаться к Skype для бизнеса Server из удаленного расположения и взаимодействовать с внутренними пользователями из удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="00d35-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="00d35-106">Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии.</span><span class="sxs-lookup"><span data-stu-id="00d35-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="00d35-107">Подробные сведения см. в [управлении федерацией и внешним доступом к Skype для бизнеса Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="00d35-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="00d35-108">Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="00d35-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="00d35-109">Применение политики доступа внешних пользователей к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="00d35-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="00d35-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="00d35-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00d35-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="00d35-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="00d35-112">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="00d35-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="00d35-113">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="00d35-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="00d35-114">In **Edit Skype for Business Server User** under External access **policy,** select the user policy that you want to apply.</span><span class="sxs-lookup"><span data-stu-id="00d35-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="00d35-115">Параметры **\<Automatic>** применяют сервер по умолчанию или параметры глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="00d35-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="00d35-116">Назначение политик Per-User внешнего доступа с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00d35-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="00d35-117">Политики внешнего доступа для каждого пользователя можно начертать с помощью Windows PowerShell и Grant-CsExternalAccessPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="00d35-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="00d35-118">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00d35-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="00d35-119">Назначение политики внешнего доступа для отдельного пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="00d35-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="00d35-120">Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="00d35-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="00d35-121">Назначение политики внешнего доступа на пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="00d35-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="00d35-122">Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="00d35-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="00d35-123">Дополнительные сведения о параметре OU, используемом в этой команде, см. в документации по командлету [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)</span><span class="sxs-lookup"><span data-stu-id="00d35-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="00d35-124">Чтобы отоименовать политику внешнего доступа на пользователя</span><span class="sxs-lookup"><span data-stu-id="00d35-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="00d35-p105">Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="00d35-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="00d35-128">Дополнительные сведения см. в разделе справки по [cmdlet Grant-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="00d35-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


