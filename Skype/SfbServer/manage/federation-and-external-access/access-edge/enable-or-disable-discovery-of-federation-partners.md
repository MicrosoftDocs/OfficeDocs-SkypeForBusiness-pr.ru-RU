---
title: Включение или отключение обнаружения федеративных партнеров
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817429"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="175e0-103">Enable or disable discovery of federation partners in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="175e0-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="175e0-p101">Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="175e0-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="175e0-106">В следующей процедуре предполагается, что федерация уже включена для организации.</span><span class="sxs-lookup"><span data-stu-id="175e0-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="175e0-107">Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="175e0-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="175e0-108">Включение или отключение автоматического обнаружения федеративных доменов для организации</span><span class="sxs-lookup"><span data-stu-id="175e0-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="175e0-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="175e0-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="175e0-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="175e0-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="175e0-111">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="175e0-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="175e0-112">На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="175e0-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="175e0-113">В разделе **Изменить настройку пограничного доступа** в области **Разрешить взаимодействие с федеративными пользователями** установите или снимите флажок **Разрешить обнаружение домена партнера**, чтобы включить или отключить автоматическое обнаружение доменов партнеров.</span><span class="sxs-lookup"><span data-stu-id="175e0-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="175e0-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="175e0-114">Click **Commit**.</span></span>

<span data-ttu-id="175e0-115">Чтобы позволить федератным пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа федераированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="175e0-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="175e0-116">Подробные сведения см. в [подключите или отключите федерацию и подключение к общедоступным системам im.](enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="175e0-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="175e0-117">Подробные сведения об управлении доступом для определенных федераированных доменов см. в подтипе "Управление федератными [доменами SIP"](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и "Управление федератными [поставщиками SIP".](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="175e0-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="175e0-118">Включение или отключение обнаружения партнеров федерации с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="175e0-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="175e0-119">Обнаружением партнеров федерации можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="175e0-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="175e0-120">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="175e0-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="175e0-121">Чтобы включить обнаружение федератных партнеров</span><span class="sxs-lookup"><span data-stu-id="175e0-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="175e0-p105">Чтобы включить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="175e0-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="175e0-124">Отключение обнаружения федератных партнеров</span><span class="sxs-lookup"><span data-stu-id="175e0-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="175e0-125">Чтобы отключить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="175e0-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

