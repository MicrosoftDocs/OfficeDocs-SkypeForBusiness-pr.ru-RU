---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Вы можете удалить любые сайты и политики пользователей, указанные на панели управления "Skype для бизнеса" на сервере, на странице политики внешней доступа.
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818290"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="8dcc6-103">Удаление сайта или пользовательской политики для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8dcc6-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="8dcc6-104">Если вы создали или настроили политики доступа внешних пользователей, которые вы больше не хотите использовать, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="8dcc6-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="8dcc6-105">Удалите все созданные вами сайты и политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="8dcc6-106">Восстановление параметров глобальной политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="8dcc6-107">Параметры глобальной политики по умолчанию запрещают доступ к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="8dcc6-108">Невозможно удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="8dcc6-109">Вы можете удалить любые сайты и политики пользователей, указанные на панели управления "Skype для бизнеса" на сервере, на странице **политики внешней доступа** .</span><span class="sxs-lookup"><span data-stu-id="8dcc6-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="8dcc6-110">При удалении глобальной политики фактически она не удаляется, но только восстанавливает параметры, заданные по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="8dcc6-111">Дополнительные сведения о сбросе глобальной политики см. [в разделе Восстановление глобальной политики для внешнего доступа пользователей](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8dcc6-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="8dcc6-112">Удаление политики сайта или пользователя для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8dcc6-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="8dcc6-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8dcc6-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8dcc6-115">Выберите **внешний доступ пользователей**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="8dcc6-116">На вкладке **внешняя политика доступа** выберите сайт или политику пользователей, которые вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="8dcc6-117">Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8dcc6-118">Удаление политик закрепления с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dcc6-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8dcc6-119">Внешние политики доступа можно удалить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="8dcc6-120">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="8dcc6-121">Удаление особой политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="8dcc6-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="8dcc6-122">Эта команда удаляет политику внешней политики доступа, примененную к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="8dcc6-123">Чтобы удалить все внешние политики доступа, примененные к области "на пользователя"</span><span class="sxs-lookup"><span data-stu-id="8dcc6-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="8dcc6-124">Эта команда удаляет все политики внешней доступа, настроенные для области "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="8dcc6-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="8dcc6-125">Удаление всех внешних политик доступа, для которых отключен доступ за пределами пользователей</span><span class="sxs-lookup"><span data-stu-id="8dcc6-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="8dcc6-126">Эта команда удаляет все внешние политики доступа, в которых отключен доступ за пределы пользователей.</span><span class="sxs-lookup"><span data-stu-id="8dcc6-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="8dcc6-127">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="8dcc6-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
