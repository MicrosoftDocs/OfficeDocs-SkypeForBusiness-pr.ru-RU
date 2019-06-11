---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9364f3562c837b949ef589fc7c5cbd2bc4a2b4cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="05f63-102">Включение и отключение отправки отказа от архивирования федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05f63-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05f63-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="05f63-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="05f63-104">На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="05f63-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="05f63-105">При архивации внешних данных необходимо включить отправку сообщений об отказе в архивацию.</span><span class="sxs-lookup"><span data-stu-id="05f63-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="05f63-106">Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="05f63-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05f63-107">В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="05f63-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="05f63-108">Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="05f63-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="05f63-109">Включение и отключение отправки запроса на архивацию федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="05f63-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="05f63-110">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="05f63-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="05f63-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05f63-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="05f63-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05f63-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="05f63-113">На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="05f63-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="05f63-114">На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="05f63-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="05f63-115">В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **отправлять заявление** об отказе от работы федеративным партнерам, чтобы включить или отключить автоматическую отправку архивации отказ от.</span><span class="sxs-lookup"><span data-stu-id="05f63-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="05f63-116">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="05f63-116">Click **Commit**.</span></span>

<span data-ttu-id="05f63-117">Чтобы пользователи федеративных пользователей могли работать с пользователями в Lync Server 2013, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="05f63-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="05f63-118">Подробные сведения можно найти [в разделе Управление федеративными партнерами КСМПП в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="05f63-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="05f63-119">Подробнее об управлении доступом для определенных федеративных доменов можно узнать в разделе [Настройка поддержки разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="05f63-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="05f63-120">Включение и отключение отказа от архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f63-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="05f63-121">Для управления использованием отказа в архивации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="05f63-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="05f63-122">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f63-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="05f63-123">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f63-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="05f63-124">Включение отказа в архивации</span><span class="sxs-lookup"><span data-stu-id="05f63-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="05f63-125">Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="05f63-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="05f63-126">Отключение отказа от архивации</span><span class="sxs-lookup"><span data-stu-id="05f63-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="05f63-127">Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="05f63-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

