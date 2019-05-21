---
title: Настройка отказов на архивацию для внешних пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться настраивать заявление об отказе в архивацию для Skype для бизнеса Server.'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278985"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="f2f80-103">Настройка отказов на архивацию для внешних пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f2f80-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="f2f80-104">**Сводка:** В этой статье рассказывается о том, как настроить заявление об отказе в архивацию для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f2f80-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="f2f80-105">В случае взаимодействия организации с внешними партнерами необходимо известить их об архивации данных, передаваемых в процессе этого взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f2f80-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="f2f80-106">При развертывании пограничного сервера и включении Федерации для организации вы получите вопрос о том, хотите ли вы автоматически отправлять заявление об отказе от архивации внешним партнерам.</span><span class="sxs-lookup"><span data-stu-id="f2f80-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="f2f80-107">Если вам нужно изменить конфигурацию, вы можете использовать панель управления Skype для бизнеса Server или командлет Windows PowerShell **Set-ксакцесседжеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="f2f80-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f2f80-108">Командлеты можно запускать либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2f80-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="f2f80-109">Чтобы обеспечить совместную работу внешних пользователей с пользователями в развертывании сервера Skype для бизнеса, необходимо также настроить по крайней мере одну политику внешнего доступа, чтобы обеспечить доступ внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2f80-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="f2f80-110">Подробные сведения можно найти в разделе Управление федеративными партнерами КСМПП для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f2f80-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="f2f80-111">Подробнее об управлении доступом к определенным федеративным доменам можно узнать в разделе Управление доступом отдельных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="f2f80-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="f2f80-112">Включение и отключение заявления об отказе от архивирования с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="f2f80-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="f2f80-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f2f80-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f2f80-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f2f80-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f2f80-115">На левой панели навигации щелкните **Федерация и внешний доступ**, а затем щелкните **Конфигурация пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="f2f80-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="f2f80-116">На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f2f80-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f2f80-117">В диалоговом окне **Изменение конфигурации пограничного доступа** в разделе **Разрешить федерацию и подключение к общедоступной системе обмена мгновенными сообщениями** разрешите или запретите автоматическую передачу заявления об отказе в связи с архивацией, установив или сняв флажок **Отправить федеративным партнерам заявление об отказе относительно архивации**.</span><span class="sxs-lookup"><span data-stu-id="f2f80-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="f2f80-118">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f2f80-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="f2f80-119">Включение и отключение заявления об отказе от архивирования в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2f80-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="f2f80-120">Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="f2f80-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="f2f80-121">Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="f2f80-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


