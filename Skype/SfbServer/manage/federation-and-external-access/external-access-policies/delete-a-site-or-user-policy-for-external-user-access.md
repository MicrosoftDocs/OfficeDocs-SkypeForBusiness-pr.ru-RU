---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Вы можете удалить любую политику сайта или пользователя, указанную в панели управления Skype для бизнеса Server на странице "Политика внешнего доступа".
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817279"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="bdded-103">Удаление сайта или пользовательской политики для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="bdded-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="bdded-104">Если были созданы или настроены политики внешнего доступа пользователей, которые больше не нужно использовать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bdded-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="bdded-105">Удалите любую созданную политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="bdded-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="bdded-p101">Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="bdded-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="bdded-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span><span class="sxs-lookup"><span data-stu-id="bdded-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="bdded-110">При удалении глобальной политики она на самом деле не удаляется, а восстанавливаются параметры по умолчанию, не включающие поддержку доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="bdded-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="bdded-111">Подробные сведения о сбросе глобальной политики см. в подзапуске глобальной политики [для доступа внешних пользователей.](reset-the-global-policy-for-external-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="bdded-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="bdded-112">Удаление политика узла или пользователя для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="bdded-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="bdded-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="bdded-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdded-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bdded-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bdded-115">Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="bdded-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="bdded-116">На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bdded-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="bdded-117">При отображении запроса на подтверждение нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bdded-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bdded-118">Удаление политик ПИН-кодов с помощью Windows PowerShell-кодов</span><span class="sxs-lookup"><span data-stu-id="bdded-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bdded-119">Политики внешнего доступа можно удалить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="bdded-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="bdded-120">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdded-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="bdded-121">Удаление определенной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="bdded-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="bdded-122">Эта команда удаляет политику внешнего доступа для узла Redmond:</span><span class="sxs-lookup"><span data-stu-id="bdded-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="bdded-123">Удаление всех политик внешнего доступа, применяемых к области на пользователя</span><span class="sxs-lookup"><span data-stu-id="bdded-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="bdded-124">Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="bdded-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="bdded-125">Удаление всех политик внешнего доступа, для которых отключен доступ внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="bdded-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="bdded-126">Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:</span><span class="sxs-lookup"><span data-stu-id="bdded-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="bdded-127">Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="bdded-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
