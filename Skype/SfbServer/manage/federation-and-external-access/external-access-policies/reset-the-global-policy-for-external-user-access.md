---
title: Сброс глобальной политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Не удается полностью удалить глобальную политику. Только с помощью параметра **Удалить** на глобальную политику сбрасывает глобальную политику параметры по умолчанию, которые не поддерживают функцию для параметров доступа внешних пользователей.
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877876"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="96b2d-104">Сброс глобальной политики для доступа внешних пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="96b2d-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="96b2d-105">Если были созданы или настроены политики доступа внешних пользователей, которые больше не хотите использовать, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="96b2d-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="96b2d-106">Удалите политику узла или пользователя, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="96b2d-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="96b2d-107">Сброс глобальной политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96b2d-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="96b2d-108">Параметры глобальной политики по умолчанию запретить доступ внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="96b2d-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="96b2d-109">Не удается удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="96b2d-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="96b2d-110">Не удается полностью удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="96b2d-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="96b2d-111">Только с помощью параметра **Удалить** на глобальную политику сбрасывает глобальную политику параметры по умолчанию, которые не поддерживают функцию для параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="96b2d-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="96b2d-112">Сброс глобальной политики значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="96b2d-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="96b2d-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="96b2d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96b2d-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="96b2d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="96b2d-115">В левой панели навигации щелкните **Доступ для внешних пользователей**, щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="96b2d-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="96b2d-116">На вкладке **Политика внешнего доступа** щелкните глобальную политику, нажмите кнопку **Изменить**и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="96b2d-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="96b2d-117">При появлении запроса на подтверждение нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="96b2d-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="96b2d-118">В верхней части страницы, информирующее о том, что выполнен сброс глобальной политики отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="96b2d-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="96b2d-119">Сброс глобальной политики внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b2d-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="96b2d-120">С помощью Windows PowerShell и командлет Remove-CsExternalAccessPolicy можно Сброс глобальной политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="96b2d-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="96b2d-121">Этот командлет можно выполнять с Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96b2d-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="96b2d-122">Сброс глобальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="96b2d-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="96b2d-123">Эта команда сбрасывает глобальную политику внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="96b2d-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="96b2d-124">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="96b2d-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


