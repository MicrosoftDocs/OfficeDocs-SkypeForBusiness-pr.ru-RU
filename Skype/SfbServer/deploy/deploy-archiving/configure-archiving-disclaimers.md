---
title: Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: Сводка. В этом разделе вы узнаете, как настроить заявление об отказе от архива для Skype для бизнеса Server.
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820669"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="b2af3-103">Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b2af3-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="b2af3-104">**Сводка:** В этом разделе вы узнаете, как настроить заявление об отказе от архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b2af3-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="b2af3-105">Если ваша организация взаимодействует с внешними партнерами, необходимо сообщить им о том, что с ними архивироваться.</span><span class="sxs-lookup"><span data-stu-id="b2af3-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="b2af3-106">При развертывании edge Server и включите федерацию для организации, вам будет предложено автоматически отправить заявление об отказе от архива внешним партнерам.</span><span class="sxs-lookup"><span data-stu-id="b2af3-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="b2af3-107">Если необходимо изменить эту конфигурацию, можно использовать панель управления Skype для бизнеса Server или Windows PowerShell **Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b2af3-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="b2af3-108">Можно запускать команды из оболочки управления Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2af3-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="b2af3-109">Чтобы позволить внешним пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2af3-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="b2af3-110">Подробные сведения см. в под управлением федераированных партнеров XMPP для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b2af3-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="b2af3-111">Подробные сведения об управлении доступом для определенных федераированных доменов см. в подконтролированном доступе отдельных федераированных доменов.</span><span class="sxs-lookup"><span data-stu-id="b2af3-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="b2af3-112">Включить или отключить заявление об отказе от архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="b2af3-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="b2af3-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="b2af3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b2af3-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b2af3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b2af3-115">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).</span><span class="sxs-lookup"><span data-stu-id="b2af3-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="b2af3-116">На **вкладке "Конфигурация края доступа"** щелкните **"Глобальная",** **"Изменить"** и **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="b2af3-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b2af3-117">In **Edit Access Edge Configuration**, under Enable federation and public IM **connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span><span class="sxs-lookup"><span data-stu-id="b2af3-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="b2af3-118">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b2af3-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="b2af3-119">Включить или отключить заявление об отказе от архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2af3-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="b2af3-120">Чтобы включить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="b2af3-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="b2af3-121">Чтобы отключить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="b2af3-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


