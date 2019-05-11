---
title: Включение или отключение обнаружения федеративных партнеров
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны ли поддержка автоматического обнаружения доменов федеративного партнера.
ms.openlocfilehash: cf12190b03df30f4a15f6ed5e0499aa97c66e576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919516"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="9479c-103">Включение и отключение обнаружения федеративных партнеров в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9479c-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="9479c-104">Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны ли поддержка автоматического обнаружения доменов федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="9479c-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="9479c-105">Используйте описанную в этом разделе для изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9479c-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="9479c-106">В следующей процедуре предполагается, что вы уже включен федерации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9479c-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="9479c-107">Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9479c-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="9479c-108">Чтобы включить или отключить автоматическое обнаружение федеративных доменов для вашей организации</span><span class="sxs-lookup"><span data-stu-id="9479c-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="9479c-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9479c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9479c-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9479c-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="9479c-111">В левой панели навигации щелкните **Доступ для внешних пользователей**, **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="9479c-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="9479c-112">На странице **Настройка пограничного доступа** щелкните **Глобальная**, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9479c-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9479c-113">В разделе **Изменить настройку пограничного доступа**, в разделе **Разрешить связь с федеративными пользователями**установите или снимите флажок **Разрешить обнаружение домена партнера** , чтобы включить или отключить автоматическое обнаружение доменов партнеров.</span><span class="sxs-lookup"><span data-stu-id="9479c-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="9479c-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9479c-114">Click **Commit**.</span></span>

<span data-ttu-id="9479c-115">Чтобы разрешить федеративным пользователям совместно работать с пользователями в вашей Скайп для развертывания Business Server, необходимо также настроить по крайней мере одной политики внешнего доступа для поддержки доступа федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9479c-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="9479c-116">Дополнительные сведения см [Включить или отключить федерацию и общедоступные службы обмена Мгновенными сообщениями](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9479c-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="9479c-117">Для получения дополнительных сведений о контроле доступа для определенных федеративных доменов видеть [Управление SIP федеративных доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и [Управление SIP федеративных поставщиков](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="9479c-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9479c-118">Включение или отключение обнаружения федеративных партнеров с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9479c-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9479c-119">Обнаружение федеративных партнеров можно управлять с помощью командлета Set-CsAccessEdgeConfiguration и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9479c-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="9479c-120">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9479c-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="9479c-121">Чтобы включить обнаружение федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="9479c-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="9479c-122">Чтобы включить обнаружение федеративных партнеров, задайте значение свойства **EnablePartnerDiscovery** значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="9479c-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="9479c-123">Обратите внимание на то, что необходимо включить DNS SRV маршрутизации, чтобы изменить значение этого свойства.</span><span class="sxs-lookup"><span data-stu-id="9479c-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="9479c-124">Чтобы отключить обнаружение федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="9479c-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="9479c-125">Чтобы отключить обнаружение федеративных партнеров, задайте значение свойства **EnablePartnerDiscovery** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="9479c-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

