---
title: Удаление существующей коллекции параметров конфигурации магистралей SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="370b7-102">Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="370b7-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="370b7-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="370b7-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="370b7-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="370b7-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="370b7-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="370b7-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="370b7-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="370b7-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="370b7-107">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="370b7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="370b7-108">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="370b7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="370b7-109">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="370b7-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="370b7-110">Этот глобальный набор параметров нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="370b7-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="370b7-111">Тем не менее, вы можете использовать панель управления Lync Server или командлет [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) для восстановления значений по умолчанию для свойств в глобальной коллекции.</span><span class="sxs-lookup"><span data-stu-id="370b7-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="370b7-112">Например, если для свойства Enable3pccRefer задано значение "true", при сбросе глобальной коллекции к значению по умолчанию для свойства Enable3pccRefer будет возвращено значение false.</span><span class="sxs-lookup"><span data-stu-id="370b7-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="370b7-113">Кроме того, администраторы могут создавать пользовательские параметры для настройки магистрали в области сайта или в области обслуживания (для отдельного шлюза PSTN); Эти пользовательские параметры можно удалить.</span><span class="sxs-lookup"><span data-stu-id="370b7-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="370b7-114">При удалении этих настраиваемых параметров следует учитывать указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="370b7-114">When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="370b7-115">Если вы удалите параметры области службы, то магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к своему сайту (если они существуют).</span><span class="sxs-lookup"><span data-stu-id="370b7-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="370b7-116">Если параметр "Параметры сайта" не существует, эти магистрали будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="370b7-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="370b7-117">После удаления параметров уровня сайта все магистральные элементы SIP, управляемые этими параметрами, теперь будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="370b7-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="370b7-118">Удаление параметров конфигурации канала с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="370b7-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="370b7-119">На панели управления Lync Server щелкните **Маршрутизация голосовой связи** и выберите **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="370b7-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="370b7-120">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистральной магистрали, которые нужно удалить, и нажмите кнопку **изменить** , а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="370b7-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="370b7-121">Чтобы удалить несколько коллекций в одной операции, щелкните первую из них, которую нужно удалить, а затем, удерживая нажатой клавишу CTRL, щелкните все дополнительные коллекции, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="370b7-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="370b7-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="370b7-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="370b7-124">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="370b7-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="370b7-125">В диалоговом окне " **Панель управления" Microsoft Lync Server 2013** нажмите кнопку " **ОК**".</span><span class="sxs-lookup"><span data-stu-id="370b7-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="370b7-126">Если вы передумали и решили не удалять коллекцию, нажмите кнопку **сохранить** , а затем — **отменить все незафиксированные изменения**.</span><span class="sxs-lookup"><span data-stu-id="370b7-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="370b7-127">Когда появится диалоговое окно " **Панель управления Microsoft Lync Server 2013** , нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="370b7-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="370b7-128">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="370b7-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="370b7-129">Вы можете удалить параметры конфигурации канала с помощью Windows PowerShell и командлета **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="370b7-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="370b7-130">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="370b7-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="370b7-131">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="370b7-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="370b7-132">Удаление заданной коллекции параметров</span><span class="sxs-lookup"><span data-stu-id="370b7-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="370b7-133">Следующая команда удаляет параметры конфигурации магистрали, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="370b7-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="370b7-134">Удаление всех коллекций, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="370b7-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="370b7-135">Эта команда удаляет все параметры конфигурации канала, примененные к области обслуживания.</span><span class="sxs-lookup"><span data-stu-id="370b7-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="370b7-136">Удаление всех коллекций с включенным обходом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="370b7-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="370b7-137">Следующая команда удаляет все параметры конфигурации канала, в которых включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="370b7-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="370b7-138">Дополнительные сведения можно найти в разделе справки по командлету [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="370b7-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

