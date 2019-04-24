---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если пользователь включен для Скайп для сервера, можно настроить федерацию SIP, удаленного доступа пользователей и общедоступных служб обмена мгновенными сообщениями (IM) в Скайп для панели управления Business Server путем применения соответствующих политик к определенным пользователям.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197634"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="3fd20-103">Назначьте политику доступа внешних пользователей Скайп для пользователя с поддержкой бизнеса</span><span class="sxs-lookup"><span data-stu-id="3fd20-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="3fd20-104">Если пользователь включен для Скайп для сервера, можно настроить федерацию SIP, удаленного доступа пользователей и общедоступных служб обмена мгновенными сообщениями (IM) в Скайп для панели управления Business Server путем применения соответствующих политик к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="3fd20-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="3fd20-105">Например при создании политики для поддержки доступа удаленных пользователей, необходимо применить его для пользователя перед пользователь может подключаться к Скайп для Business Server на удаленном компьютере и совместно работать с внутренними пользователями из удаленного местоположения.</span><span class="sxs-lookup"><span data-stu-id="3fd20-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="3fd20-106">Для поддержки доступа внешних пользователей, необходимо включить поддержку для каждого типа доступа внешних пользователей, которые вы хотите обеспечить поддержку и настройки соответствующих политик и других параметров для управления его использования.</span><span class="sxs-lookup"><span data-stu-id="3fd20-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="3fd20-107">Дополнительные сведения см [Управление Федерация и внешний доступ к Скайп для Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="3fd20-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="3fd20-108">Используйте описанную в этом разделе для применения политики доступа ранее созданной внешних пользователей для одного или нескольких учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="3fd20-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="3fd20-109">Для применения политики доступа внешних пользователей к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3fd20-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="3fd20-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3fd20-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3fd20-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3fd20-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3fd20-112">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="3fd20-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="3fd20-113">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="3fd20-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3fd20-114">В **Скайп изменение для пользователя Business Server** в разделе **Политика внешнего доступа**выберите пользовательскую политику, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="3fd20-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="3fd20-115">\*\* \<Automatic>\*\* применяются параметры сервера по умолчанию или параметров глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="3fd20-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3fd20-116">Назначение политик внешнего доступа на уровне пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fd20-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3fd20-117">Может быть назначен политик внешнего доступа на уровне пользователя с помощью командлета Grant-CsExternalAccessPolicy и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fd20-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="3fd20-118">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fd20-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="3fd20-119">Назначение политики внешнего доступа пользователя к отдельному пользователю</span><span class="sxs-lookup"><span data-stu-id="3fd20-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="3fd20-120">Эта команда назначает индивидуальную пользовательскую политику внешнего доступа RedmondExternalAccessPolicy пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3fd20-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="3fd20-121">Назначение политики внешнего доступа пользователя к нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="3fd20-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="3fd20-122">Эта команда назначает политику внешнего доступа пользователя USAExternalAccessPolicy для всех пользователей, имеющих учетные записи в Соединенных Штатах Америки Подразделения в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3fd20-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="3fd20-123">Дополнительные сведения о Подразделении параметр, используемый в этой команде командлет [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) см.</span><span class="sxs-lookup"><span data-stu-id="3fd20-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="3fd20-124">Отмена назначения индивидуальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="3fd20-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="3fd20-125">Эта команда unassigns все политики внешнего доступа пользователя, ранее назначенную пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3fd20-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="3fd20-126">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="3fd20-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="3fd20-127">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="3fd20-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="3fd20-128">Для получения дополнительных сведений см раздел справки для командлета [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="3fd20-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


