---
title: 'Lync Server 2013: Просмотр сведений о параметрах конфигурации Lync Phone Edition'
description: 'Lync Server 2013: Просмотр сведений о параметрах конфигурации Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576435"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="0624a-103">Просмотр сведений о параметрах конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0624a-103">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0624a-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0624a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0624a-105">Вы можете просмотреть сведения о конфигурации устройств, на которых работает Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="0624a-105">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="0624a-106">Эти данные объединены в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0624a-106">The information is organized into collections.</span></span> <span data-ttu-id="0624a-107">При установке Lync Server вы получаете коллекцию параметров Lync Phone Edition, которые применяются ко всем устройствам с Lync Phone Edition в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0624a-107">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="0624a-108">Также можно создать новые коллекции настройки для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="0624a-108">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="0624a-109">Настройки сайта имеют приоритет перед глобальными настройками.</span><span class="sxs-lookup"><span data-stu-id="0624a-109">Site settings take precedence over global settings.</span></span> <span data-ttu-id="0624a-110">Каждая коллекция настроек содержит имя, область (глобальная область или область сайта), параметр безопасности SIP, уровень ведения журнала, уровень качества обслуживания при использовании голосовой связи, данные о блокировке телефона, минимальную длину персонального идентификационного номера (ПИН-кода), а также интервал автоматической блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="0624a-110">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="0624a-111">Просмотр сведений о конфигурации устройств с Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0624a-111">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="0624a-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0624a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0624a-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0624a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0624a-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0624a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0624a-115">На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.</span><span class="sxs-lookup"><span data-stu-id="0624a-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="0624a-p103">На странице **Конфигурация устройства** щелкните коллекцию настроек, данные о которых требуется просмотреть. Имя, область, параметр безопасности SIP, уровень качества голосовой связи и параметры блокировки телефона перечислены на главной странице. Для просмотра данных об уровне ведения журнала и сведений о блокировке телефона щелкните меню **Правка** и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="0624a-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0624a-119">Просмотр сведений о конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0624a-119">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0624a-120">Параметры конфигурации Lync Phone Edition можно просмотреть с помощью командной консоли Lync Server и командлета **Get – CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0624a-120">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="0624a-121">Вы можете запустить этот командлет из командной консоли Lync Server 2013 Management Shell или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0624a-121">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0624a-122">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0624a-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="0624a-123">Просмотр сведений о конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0624a-123">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="0624a-124">Чтобы просмотреть сведения обо всех параметрах конфигурации Lync Phone Edition, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="0624a-124">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="0624a-125">Команда возвращает данные в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="0624a-125">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="0624a-126">Дополнительные сведения см. в статье [Get – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0624a-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0624a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0624a-127">See Also</span></span>


[<span data-ttu-id="0624a-128">Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0624a-128">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="0624a-129">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0624a-129">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="0624a-130">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0624a-130">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="0624a-131">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0624a-131">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

