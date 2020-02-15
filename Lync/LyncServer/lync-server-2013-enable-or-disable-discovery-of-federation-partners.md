---
title: 'Lync Server 2013: Включение или отключение обнаружения партнеров Федерации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6fd924d4aef6a9a6657829fa225da9595f52fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="4d90a-102">Включение и отключение обнаружения партнеров Федерации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d90a-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d90a-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d90a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d90a-p101">Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d90a-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d90a-106">В следующей процедуре предполагается, что федерация уже включена для организации.</span><span class="sxs-lookup"><span data-stu-id="4d90a-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="4d90a-107">Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4d90a-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="4d90a-108">Включение или отключение автоматического обнаружения федеративных доменов для организации</span><span class="sxs-lookup"><span data-stu-id="4d90a-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="4d90a-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d90a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d90a-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d90a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d90a-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d90a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d90a-112">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="4d90a-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4d90a-113">На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="4d90a-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4d90a-114">В разделе **Изменить настройку пограничного доступа** в области **Разрешить взаимодействие с федеративными пользователями** установите или снимите флажок **Разрешить обнаружение домена партнера**, чтобы включить или отключить автоматическое обнаружение доменов партнеров.</span><span class="sxs-lookup"><span data-stu-id="4d90a-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="4d90a-115">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4d90a-115">Click **Commit**.</span></span>

<span data-ttu-id="4d90a-116">Чтобы разрешить федеративным пользователям совместно работать с пользователями в развертывании Lync Server, вам также необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="4d90a-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="4d90a-117">Дополнительные сведения: [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4d90a-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4d90a-118">Сведения об управлении доступом для определенных федеративных доменов приведены в статье [Manage федеративные домены SIP для Организации в Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Управление ФЕДЕРАТИВНЫМИ поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) и [Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4d90a-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d90a-119">Включение или отключение обнаружения партнеров Федерации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d90a-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d90a-120">Можно управлять обнаружением партнеров Федерации с помощью Windows PowerShell и командлета Set – CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4d90a-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4d90a-121">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d90a-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d90a-122">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="4d90a-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="4d90a-123">Включение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="4d90a-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="4d90a-p106">Чтобы включить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="4d90a-p106">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="4d90a-126">Отключение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="4d90a-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="4d90a-127">Чтобы отключить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="4d90a-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

