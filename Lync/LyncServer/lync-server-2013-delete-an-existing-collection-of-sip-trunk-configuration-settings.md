---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP
description: Удаление существующей коллекции параметров конфигурации магистрали SIP.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98acede458d34eb30202d898414b2e17076d32d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572825"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0922e-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0922e-103">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0922e-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0922e-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0922e-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="0922e-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="0922e-107">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="0922e-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="0922e-108">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="0922e-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="0922e-109">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="0922e-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="0922e-110">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="0922e-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="0922e-111">Эта глобальная коллекция параметров не подлежит удалению.</span><span class="sxs-lookup"><span data-stu-id="0922e-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="0922e-112">Однако с помощью панели управления Lync Server или командлета [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) можно сбросить свойства в глобальной коллекции на значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0922e-112">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="0922e-113">Например, если задать свойство Enable3pccRefer как True, то при сбросе глобальной коллекции для свойства Enable3pccRefer возвращается значение по умолчанию False.</span><span class="sxs-lookup"><span data-stu-id="0922e-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="0922e-p103">Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="0922e-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="0922e-p104">Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="0922e-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="0922e-118">Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="0922e-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="0922e-119">Удаление параметров конфигурации магистрали с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0922e-119">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0922e-120">В панели управления Lync Server щелкните **Маршрутизация голосовой связи** , а затем щелкните **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="0922e-120">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="0922e-p105">На вкладке **Настройка линии связи** выберите коллекцию параметров конфигурации магистральной линии SIP, которую следует удалить, щелкните **Изменить**, затем нажмите **Удалить**. Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.</span><span class="sxs-lookup"><span data-stu-id="0922e-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="0922e-p106">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="0922e-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="0922e-125">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0922e-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="0922e-126">В диалоговом окне **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0922e-126">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="0922e-p107">Если решено не удалять коллекцию, щелкните **Сохранить**, затем **Отменить все несохраненные изменения**. При появлении диалогового окна **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0922e-p107">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0922e-129">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0922e-129">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0922e-130">Параметры конфигурации магистрали можно удалить с помощью Windows PowerShell и командлета **Remove – CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0922e-130">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="0922e-131">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0922e-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0922e-132">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0922e-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="0922e-133">Удаление заданной коллекции параметров</span><span class="sxs-lookup"><span data-stu-id="0922e-133">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="0922e-134">Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="0922e-134">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="0922e-135">Удаление всех коллекций, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="0922e-135">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="0922e-136">Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="0922e-136">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="0922e-137">Удаление всех коллекций, где включен обход сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0922e-137">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="0922e-138">Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="0922e-138">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="0922e-139">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0922e-139">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

