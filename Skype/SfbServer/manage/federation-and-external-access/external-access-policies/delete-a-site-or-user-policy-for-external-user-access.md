---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно удалить любой политику узла или пользователя, который указан в Скайп для панели управления Business Server на странице политика внешнего доступа.
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889806"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="2bb2f-103">Удаление сайта или пользовательской политики для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="2bb2f-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="2bb2f-104">Если были созданы или настроены политики доступа внешних пользователей, которые больше не хотите использовать, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="2bb2f-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="2bb2f-105">Удалите политику узла или пользователя, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="2bb2f-106">Сброс глобальной политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="2bb2f-107">Параметры глобальной политики по умолчанию запретить доступ внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="2bb2f-108">Не удается удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="2bb2f-109">Можно удалить любой политику узла или пользователя, который указан в Скайп для панели управления Business Server на странице **Политика внешнего доступа** .</span><span class="sxs-lookup"><span data-stu-id="2bb2f-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="2bb2f-110">Удаление глобальной политики не приводит к удалению фактически, но только сбрасывает параметры по умолчанию, которые не поддерживают функцию для параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="2bb2f-111">Для получения дополнительных сведений о Сброс глобальной политики видеть [Сброс глобальной политики для доступа внешних пользователей](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2bb2f-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="2bb2f-112">Чтобы удалить политику сайта или пользователя для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="2bb2f-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="2bb2f-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2bb2f-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2bb2f-115">**Доступ внешних пользователей**, щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="2bb2f-116">На вкладке **Политика внешнего доступа** щелкните в политике сайта или пользователя, которые необходимо удалить, нажмите кнопку **Изменить**и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="2bb2f-117">При появлении запроса на подтверждение нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2bb2f-118">Удаление политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bb2f-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2bb2f-119">Политики внешнего доступа можно удалить с помощью Windows PowerShell и командлет Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="2bb2f-120">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="2bb2f-121">Чтобы удалить политику внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="2bb2f-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="2bb2f-122">Эта команда удаляет политику внешнего доступа, применяемых к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="2bb2f-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="2bb2f-123">Удаление всех внешний доступ к политик, применяемых на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="2bb2f-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="2bb2f-124">Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="2bb2f-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="2bb2f-125">Удаление всех политик внешнего доступа, где отключена доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="2bb2f-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="2bb2f-126">Эта команда удаляет все политики внешнего доступа, где внешних пользователей доступ был отключен:</span><span class="sxs-lookup"><span data-stu-id="2bb2f-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="2bb2f-127">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="2bb2f-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
