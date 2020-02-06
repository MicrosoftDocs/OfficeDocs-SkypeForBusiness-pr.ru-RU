---
title: Сброс глобальной политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Вы не можете полностью удалить глобальную политику. Параметр " **Удалить** " в глобальной политике используется только для сброса глобальной политики в параметры по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818270"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="f9d9e-104">Сброс глобальной политики доступа внешних пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f9d9e-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="f9d9e-105">Если вы создали или настроили политики доступа внешних пользователей, которые вы больше не хотите использовать, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="f9d9e-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="f9d9e-106">Удалите все созданные вами сайты и политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="f9d9e-107">Восстановление параметров глобальной политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="f9d9e-108">Параметры глобальной политики по умолчанию запрещают доступ к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="f9d9e-109">Невозможно удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="f9d9e-110">Вы не можете полностью удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="f9d9e-111">Параметр " **Удалить** " в глобальной политике используется только для сброса глобальной политики в параметры по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="f9d9e-112">Восстановление параметров глобальной политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f9d9e-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="f9d9e-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9d9e-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="f9d9e-115">На панели навигации слева выберите **внешний пользовательский доступ**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f9d9e-116">На вкладке **внешняя политика доступа** выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f9d9e-117">Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="f9d9e-118">В верхней части страницы появится сообщение о том, что была выполнена сброс глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9d9e-119">Сброс глобальной политики внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9d9e-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9d9e-120">Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f9d9e-121">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="f9d9e-122">Сброс глобальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="f9d9e-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="f9d9e-123">Эта команда сбрасывает глобальную политику внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="f9d9e-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="f9d9e-124">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f9d9e-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


