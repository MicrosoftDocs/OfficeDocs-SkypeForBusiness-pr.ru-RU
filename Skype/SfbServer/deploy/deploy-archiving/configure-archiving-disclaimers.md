---
title: Настройка архивации заявления об отказе для внешних пользователей в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Сводка: Сведения в этой статье описывается настройка отказа от архивирования для Скайп для Business Server.'
ms.openlocfilehash: 9511dacb23773a4cd411844abd1d38216026019e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881753"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="28201-103">Настройка архивации заявления об отказе для внешних пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="28201-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="28201-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как настройка отказа от архивирования для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="28201-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="28201-105">В случае взаимодействия организации с внешними партнерами необходимо известить их об архивации данных, передаваемых в процессе этого взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="28201-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="28201-106">При развертывании пограничного сервера и включение федерации для вашей организации запрос, следует ли автоматически отправлять отказа от архивирования для внешних партнеров.</span><span class="sxs-lookup"><span data-stu-id="28201-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="28201-107">Если необходимо изменить эту конфигурацию, можно использовать Скайп для панели управления Business Server или командлета Windows PowerShell **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="28201-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="28201-108">Командлеты можно запустить из Скайп оболочки управления Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28201-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="28201-109">Предоставление внешним пользователям совместно работать с пользователями в вашей Скайп для развертывания Business Server, необходимо также настроить по крайней мере одна политика внешнего доступа для поддержки доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="28201-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="28201-110">Дополнительные сведения см управление федеративных партнеров XMPP для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="28201-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="28201-111">Для получения дополнительных сведений о контроле доступа для определенных федеративных доменов видеть Control Access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="28201-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="28201-112">Включение и отключение заявления об отказе от архивирования с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="28201-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="28201-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="28201-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="28201-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="28201-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="28201-115">На левой панели навигации щелкните **Федерация и внешний доступ**, а затем щелкните **Конфигурация пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="28201-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="28201-116">На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="28201-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="28201-117">В диалоговом окне **Изменение конфигурации пограничного доступа** в разделе **Разрешить федерацию и подключение к общедоступной системе обмена мгновенными сообщениями** разрешите или запретите автоматическую передачу заявления об отказе в связи с архивацией, установив или сняв флажок **Отправить федеративным партнерам заявление об отказе относительно архивации**.</span><span class="sxs-lookup"><span data-stu-id="28201-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="28201-118">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="28201-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="28201-119">Включение и отключение заявления об отказе от архивирования в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28201-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="28201-120">Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="28201-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="28201-121">Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="28201-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


