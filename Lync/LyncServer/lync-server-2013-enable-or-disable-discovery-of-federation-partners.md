---
title: 'Lync Server 2013: включение или отключение обнаружения федеративных партнеров'
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
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="88b55-102">Включение или отключение обнаружения федеративных партнеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b55-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b55-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="88b55-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="88b55-104">На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли поддерживать автоматическое обнаружение доменов федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="88b55-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="88b55-105">Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="88b55-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88b55-106">В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="88b55-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="88b55-107">Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="88b55-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="88b55-108">Включение и отключение автоматического обнаружения федеративных доменов для Организации</span><span class="sxs-lookup"><span data-stu-id="88b55-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="88b55-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="88b55-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88b55-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88b55-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88b55-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88b55-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88b55-112">На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="88b55-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="88b55-113">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="88b55-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="88b55-114">В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **включить обнаружение домена партнера** , чтобы включить или отключить автоматическое обнаружение доменных партнеров.</span><span class="sxs-lookup"><span data-stu-id="88b55-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="88b55-115">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="88b55-115">Click **Commit**.</span></span>

<span data-ttu-id="88b55-116">Чтобы включить Федеративные пользователи для совместной работы с пользователями в развертывании Lync Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="88b55-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="88b55-117">Дополнительные сведения можно найти [в разделе Включение и отключение подключения к службам интеграции и обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="88b55-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="88b55-118">Дополнительные сведения об управлении доступом для определенных федеративных доменов можно найти [в разделе Управление федеративными доменами SIP для Организации в](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)lync Server 2013, [управлять ФЕДЕРАТИВНЫМИ поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) и [управлять КСМПП федеративных партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="88b55-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="88b55-119">Включение и отключение обнаружения партнеров Федерации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88b55-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="88b55-120">Для управления партнерами Федерации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="88b55-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="88b55-121">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88b55-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="88b55-122">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88b55-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="88b55-123">Включение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="88b55-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="88b55-124">Чтобы включить обнаружение партнеров Федерации, задайте для свойства **енаблепартнердисковери** значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="88b55-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="88b55-125">Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="88b55-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="88b55-126">Отключение обнаружения партнеров Федерации</span><span class="sxs-lookup"><span data-stu-id="88b55-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="88b55-127">Чтобы отключить обнаружение партнеров Федерации, установите для свойства **енаблепартнердисковери** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="88b55-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

