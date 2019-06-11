---
title: 'Lync Server 2013: удаление существующей коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1ae04-102">Удаление существующей коллекции параметров конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae04-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae04-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1ae04-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1ae04-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="1ae04-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="1ae04-106">При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="1ae04-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="1ae04-107">Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="1ae04-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="1ae04-108">Параметры, настроенные на уровне сайта, переопределяют глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="1ae04-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="1ae04-109">Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="1ae04-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="1ae04-p103">Обратите внимание, что глобальные параметры также можно "удалить", однако на самом деле они не удаляются. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, в коллекции параметров конфигурации CDR по умолчанию очистка включена. Предположим, что глобальная коллекция изменена и очистка отключена. Если удалить глобальные параметры, все свойства будут сброшены на значения по умолчанию и очистка снова будет включена.</span><span class="sxs-lookup"><span data-stu-id="1ae04-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="1ae04-117">Вы можете удалить параметры конфигурации CDR с помощью панели управления Lync Server или командлета [Remove-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1ae04-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="1ae04-118">Удаление параметров конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="1ae04-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1ae04-119">На панели управления Lync Server щелкните элемент **мониторинг и архивация**.</span><span class="sxs-lookup"><span data-stu-id="1ae04-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="1ae04-p104">На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, выберите первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.</span><span class="sxs-lookup"><span data-stu-id="1ae04-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="1ae04-122">Нажмите **Изменить**, затем кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1ae04-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="1ae04-123">В диалоговом окне "Панель управления Lync Server" нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ae04-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ae04-124">Удаление параметров конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ae04-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1ae04-125">Вы можете удалить параметры конфигурации для записи сведений о вызовах с помощью Windows PowerShell и командлета **Remove-кскдрконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="1ae04-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1ae04-126">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae04-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1ae04-127">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae04-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="1ae04-128">Удаление определенной коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="1ae04-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="1ae04-129">Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="1ae04-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="1ae04-130">Удаление всех параметров конфигурации CDR, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="1ae04-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="1ae04-131">Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="1ae04-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="1ae04-132">Удаление всех параметров конфигурации CDR, которые отключают регистрацию вызовов</span><span class="sxs-lookup"><span data-stu-id="1ae04-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="1ae04-133">Эта команда удаляет все параметры конфигурации CDR, которые отключают регистрацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="1ae04-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="1ae04-134">Дополнительные сведения можно найти в разделе справки по командлету [Remove-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1ae04-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

