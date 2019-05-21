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
localization_priority: Normal
description: Если для пользователя разрешено использование Skype для бизнеса Server, вы можете настроить федерацию SIP, удаленный доступ пользователей и общедоступную службу обмена мгновенными сообщениями (IM) на панели управления "Skype для бизнеса" на сервере, применив соответствующие политики для конкретных пользователей.
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280175"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="8f53b-103">Назначение внешней политики доступа пользователю, поддерживающему Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8f53b-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="8f53b-104">Если для пользователя разрешено использование Skype для бизнеса Server, вы можете настроить федерацию SIP, удаленный доступ пользователей и общедоступную службу обмена мгновенными сообщениями (IM) на панели управления "Skype для бизнеса" на сервере, применив соответствующие политики для конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f53b-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="8f53b-105">Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю, прежде чем пользователь сможет подключиться к серверу Skype для бизнеса Server из удаленного местоположения и будет работать совместно с другими пользователями из удаленного местоположения.</span><span class="sxs-lookup"><span data-stu-id="8f53b-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="8f53b-106">Для поддержки внешнего доступа пользователей необходимо включить поддержку для каждого типа внешних пользователей, которые будут поддерживаться, и настроить соответствующие политики и другие параметры для управления его использованием.</span><span class="sxs-lookup"><span data-stu-id="8f53b-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="8f53b-107">Подробности можно найти [в разделе Управление интеграцией и внешним доступом к Skype для бизнеса Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f53b-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="8f53b-108">В этой статье описана процедура применения ранее созданной политики доступа внешних пользователей к одной или нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f53b-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="8f53b-109">Применение политики внешних пользователей к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="8f53b-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="8f53b-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8f53b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f53b-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8f53b-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8f53b-112">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="8f53b-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="8f53b-113">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="8f53b-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8f53b-114">В диалоговом окне **изменение пользователя сервера Skype для бизнеса Server** в разделе **Политика внешнего доступа**выберите политику пользователей, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="8f53b-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="8f53b-115">Параметры \*\* \<аутоматик_гт_\*\* применяются к параметрам сервера или глобальной политики, используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8f53b-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f53b-116">Назначение политик внешнего доступа для каждого пользователя с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f53b-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8f53b-117">Политики внешнего доступа для каждого пользователя можно назначить с помощью Windows PowerShell и командлета Grant-Ксекстерналакцессполици.</span><span class="sxs-lookup"><span data-stu-id="8f53b-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="8f53b-118">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f53b-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="8f53b-119">Назначение политики внешнего доступа для отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="8f53b-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="8f53b-120">Эта команда назначает политику внешнего доступа для каждого пользователя, Редмондекстерналакцессполици пользователю Кен мер.</span><span class="sxs-lookup"><span data-stu-id="8f53b-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="8f53b-121">Назначение политики внешнего доступа для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="8f53b-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="8f53b-122">Эта команда назначает политику внешнего доступа "на пользователя" Усаекстерналакцессполици всем пользователям, у которых есть учетные записи в подразделении "США" в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f53b-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="8f53b-123">Дополнительные сведения о параметре OU, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="8f53b-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="8f53b-124">Отмена назначения политики внешнего доступа для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="8f53b-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="8f53b-125">Эта команда отменяет назначение любой пользовательской политики внешнего доступа, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="8f53b-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="8f53b-126">После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует.</span><span class="sxs-lookup"><span data-stu-id="8f53b-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="8f53b-127">Политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="8f53b-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="8f53b-128">Дополнительные сведения можно найти в разделе справки о командлете [Grant-ксекстерналакцессполици](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="8f53b-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


