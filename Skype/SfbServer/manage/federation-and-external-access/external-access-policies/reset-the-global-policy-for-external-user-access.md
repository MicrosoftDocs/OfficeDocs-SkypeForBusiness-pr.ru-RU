---
title: Сброс глобальной политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Вы не можете полностью удалить глобальную политику. При использовании команды **Удалить** для глобальной политики восстанавливаются параметры по умолчанию, не поддерживающие какие-либо параметры доступа внешних пользователей.
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817249"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="e8024-104">Сброс глобальной политики доступа внешних пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8024-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="e8024-105">Если были созданы или настроены политики внешнего доступа пользователей, которые больше не нужно использовать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e8024-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="e8024-106">Удалите любую созданную политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8024-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="e8024-p102">Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="e8024-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="e8024-p103">Вы не можете полностью удалить глобальную политику. При использовании команды **Удалить** для глобальной политики восстанавливаются параметры по умолчанию, не поддерживающие какие-либо параметры доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e8024-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="e8024-112">Восстановление параметров глобальной политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e8024-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="e8024-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e8024-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8024-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e8024-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="e8024-115">В левой панели навигации щелкните элемент **Доступ внешних пользователей**, а затем выберите **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="e8024-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e8024-116">На вкладке **Политика внешнего доступа** щелкните глобальную политику, нажмите кнопку **Изменить** (Изменить) и затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e8024-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e8024-p104">При отображении запроса на подтверждение нажмите кнопку **ОК**. В верхней части страницы появится сообщение о сбросе глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="e8024-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8024-119">Сброс глобальной политики внешнего доступа с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8024-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8024-120">Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="e8024-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e8024-121">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8024-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="e8024-122">Сброс глобальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="e8024-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="e8024-123">Следующая команда сбрасывает глобальную политику внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="e8024-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="e8024-124">Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="e8024-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


