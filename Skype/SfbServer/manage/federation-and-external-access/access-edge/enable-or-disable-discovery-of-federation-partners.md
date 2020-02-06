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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли поддерживать автоматическое обнаружение доменов федеративных партнеров.
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818400"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="130f7-103">Включение и отключение обнаружения партнеров Федерации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="130f7-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="130f7-104">На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли поддерживать автоматическое обнаружение доменов федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="130f7-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="130f7-105">Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="130f7-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="130f7-106">В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="130f7-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="130f7-107">Дополнительные сведения о включении Федерации можно найти в разделе [Включение и отключение удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="130f7-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="130f7-108">Включение и отключение автоматического обнаружения федеративных доменов для Организации</span><span class="sxs-lookup"><span data-stu-id="130f7-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="130f7-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="130f7-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="130f7-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="130f7-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="130f7-111">На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="130f7-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="130f7-112">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="130f7-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="130f7-113">В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **включить обнаружение домена партнера** , чтобы включить или отключить автоматическое обнаружение доменных партнеров.</span><span class="sxs-lookup"><span data-stu-id="130f7-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="130f7-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="130f7-114">Click **Commit**.</span></span>

<span data-ttu-id="130f7-115">Чтобы пользователи федеративных пользователей могли работать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="130f7-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="130f7-116">Дополнительные сведения можно найти в разделе [Включение и отключение подключения к службам федерации и общедоступных мгновенных сообщений](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="130f7-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="130f7-117">Дополнительные сведения об управлении доступом для определенных федеративных доменов можно найти в разделе [Управление федеративными доменами SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и [Управление поставщиками SIP Федерации](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="130f7-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="130f7-118">Включение и отключение обнаружения партнеров Федерации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="130f7-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="130f7-119">Для управления партнерами Федерации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="130f7-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="130f7-120">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="130f7-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="130f7-121">Включение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="130f7-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="130f7-122">Чтобы включить обнаружение партнеров Федерации, задайте для свойства **енаблепартнердисковери** значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="130f7-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="130f7-123">Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="130f7-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="130f7-124">Отключение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="130f7-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="130f7-125">Чтобы отключить обнаружение партнеров Федерации, установите для свойства **енаблепартнердисковери** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="130f7-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

