---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
description: Разрешите или запретите отправку заявления об отказе от архивации федеративным партнерам.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1523a19bc2758e170c044a306398bef45ec33f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563515"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="a1f4f-103">Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1f4f-103">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1f4f-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a1f4f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a1f4f-105">При развертывании пограничных серверов и включении Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-105">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="a1f4f-106">При архивации внешних коммуникаций необходимо включить отправку заявления об отказе от архивации.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-106">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="a1f4f-107">Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-107">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a1f4f-108">В следующей процедуре предполагается, что федерация уже включена для организации.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-108">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="a1f4f-109">Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-109">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="a1f4f-110">Включение или отключение отправки заявления об отказе от архивации федеративным партнерам</span><span class="sxs-lookup"><span data-stu-id="a1f4f-110">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="a1f4f-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1f4f-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1f4f-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1f4f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1f4f-114">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-114">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a1f4f-115">На вкладке **Настройка пограничного доступа** нажмите кнопку **Глобальная**, выберите команду **изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-115">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a1f4f-116">В разделе **изменение конфигурации пограничного сервера доступа**в разделе **Разрешить взаимодействие с федеративными пользователями**установите или снимите флажок **отправлять заявление об отказе от прав для федеративных партнеров** , чтобы включить или отключить автоматическую отправку заявления об отказе от архивации.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-116">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="a1f4f-117">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-117">Click **Commit**.</span></span>

<span data-ttu-id="a1f4f-118">Чтобы разрешить федеративным пользователям совместно работать с пользователями в развертывании Lync Server 2013, вам также необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-118">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="a1f4f-119">Дополнительные сведения: [Manage XMPP Федеративные партнеры в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-119">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="a1f4f-120">Подробные сведения об управлении доступом для определенных федеративных доменов приведены в статье [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-120">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1f4f-121">Включение или отключение заявления об отказе от архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1f4f-121">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1f4f-122">С помощью Windows PowerShell и командлета Set-CsAccessEdgeConfiguration можно управлять использованием заявления об отказе в архивации.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-122">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a1f4f-123">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1f4f-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1f4f-124">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a1f4f-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="a1f4f-125">Включение заявления об отказе от архивации</span><span class="sxs-lookup"><span data-stu-id="a1f4f-125">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="a1f4f-126">Чтобы включить заявление об отказе в архивации, присвойте свойству **EnableArchivingDisclaimer** значение True ($true):</span><span class="sxs-lookup"><span data-stu-id="a1f4f-126">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="a1f4f-127">Отключение заявления об отказе от архивации</span><span class="sxs-lookup"><span data-stu-id="a1f4f-127">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="a1f4f-128">Чтобы отключить заявление об отказе в архивации, присвойте свойству **EnableArchivingDisclaimer** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="a1f4f-128">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

