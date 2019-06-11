---
title: 'Lync Server 2013: удаление параметров конфигурации качества взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9515186ab28a6d6085a01ee6785aa1d95914b1f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="89f04-102">Удаление параметров конфигурации качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f04-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f04-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89f04-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89f04-p101">Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.</span><span class="sxs-lookup"><span data-stu-id="89f04-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="89f04-106">При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации QoE.</span><span class="sxs-lookup"><span data-stu-id="89f04-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="89f04-107">Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="89f04-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="89f04-108">Параметрам, заданным на уровне сайта, назначен более высокий приоритет, чем параметрам, заданным на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="89f04-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="89f04-109">Если параметры уровня сайта удалены, управление качеством взаимодействия на этом сайте осуществляется на основе глобальных параметров.</span><span class="sxs-lookup"><span data-stu-id="89f04-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="89f04-p103">Помните, что вы также можете "удалить" глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию в коллекции параметров конфигурации качества взаимодействия включена очистка. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.</span><span class="sxs-lookup"><span data-stu-id="89f04-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of QoE configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="89f04-117">Вы можете удалять параметры конфигурации QoE с помощью панели управления Lync Server или с помощью командлета [Remove-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="89f04-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="89f04-118">Удаление параметров конфигурации QoE с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="89f04-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89f04-119">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="89f04-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="89f04-120">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="89f04-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="89f04-121">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f04-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89f04-122">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89f04-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89f04-123">На левой панели навигации щелкните **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="89f04-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="89f04-124">На странице **Данные о качестве взаимодействия** щелкните требуемую политику и выберите **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="89f04-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="89f04-125">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89f04-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89f04-126">Удаление параметров конфигурации QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89f04-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89f04-127">Вы можете удалить параметры конфигурации QoE с помощью Windows PowerShell и командлета **Remove-кскоеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="89f04-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="89f04-128">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89f04-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89f04-129">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89f04-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="89f04-130">Удаление указанной коллекции параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="89f04-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="89f04-131">Эта команда удаляет параметры конфигурации качества взаимодействия, примененные к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="89f04-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="89f04-132">Удаление всех параметров конфигурации качества взаимодействия, примененных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="89f04-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="89f04-133">Эта команда удаляет все параметры конфигурации качества взаимодействия, примененные на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="89f04-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="89f04-134">Удаление всех параметров конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия</span><span class="sxs-lookup"><span data-stu-id="89f04-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="89f04-135">Эта команда удаляет все параметры конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="89f04-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="89f04-136">Подробности можно найти в разделе [Remove-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="89f04-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

