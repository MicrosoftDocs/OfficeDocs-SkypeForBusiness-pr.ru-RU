---
title: 'Lync Server 2013: Просмотр сведений о параметрах конфигурации Lync Phone Edition'
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
ms.openlocfilehash: 64d6bca76586f6a4b9636a92f2026658b77a9382
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="973e4-102">Просмотр сведений о параметрах конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="973e4-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="973e4-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="973e4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="973e4-104">Вы можете просмотреть сведения о конфигурации устройств, на которых работает Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="973e4-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="973e4-105">Эти данные объединены в коллекции.</span><span class="sxs-lookup"><span data-stu-id="973e4-105">The information is organized into collections.</span></span> <span data-ttu-id="973e4-106">При установке Lync Server вы получаете коллекцию параметров Lync Phone Edition, которые применяются ко всем устройствам с Lync Phone Edition в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="973e4-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="973e4-107">Также можно создать новые коллекции настройки для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="973e4-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="973e4-108">Настройки сайта имеют приоритет перед глобальными настройками.</span><span class="sxs-lookup"><span data-stu-id="973e4-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="973e4-109">Каждая коллекция настроек содержит имя, область (глобальная область или область сайта), параметр безопасности SIP, уровень ведения журнала, уровень качества обслуживания при использовании голосовой связи, данные о блокировке телефона, минимальную длину персонального идентификационного номера (ПИН-кода), а также интервал автоматической блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="973e4-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="973e4-110">Просмотр сведений о конфигурации устройств с Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="973e4-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="973e4-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="973e4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="973e4-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="973e4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="973e4-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="973e4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="973e4-114">На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.</span><span class="sxs-lookup"><span data-stu-id="973e4-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="973e4-p103">На странице **Конфигурация устройства** щелкните коллекцию настроек, данные о которых требуется просмотреть. Имя, область, параметр безопасности SIP, уровень качества голосовой связи и параметры блокировки телефона перечислены на главной странице. Для просмотра данных об уровне ведения журнала и сведений о блокировке телефона щелкните меню **Правка** и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="973e4-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="973e4-118">Просмотр сведений о конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="973e4-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="973e4-119">Параметры конфигурации Lync Phone Edition можно просмотреть с помощью командной консоли Lync Server и командлета **Get – CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="973e4-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="973e4-120">Вы можете запустить этот командлет из командной консоли Lync Server 2013 Management Shell или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="973e4-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="973e4-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="973e4-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="973e4-122">Просмотр сведений о конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="973e4-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="973e4-123">Чтобы просмотреть сведения обо всех параметрах конфигурации Lync Phone Edition, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="973e4-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="973e4-124">Команда возвращает данные в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="973e4-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="973e4-125">Дополнительные сведения см. в статье [Get – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="973e4-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="973e4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="973e4-126">See Also</span></span>


[<span data-ttu-id="973e4-127">Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="973e4-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="973e4-128">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="973e4-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="973e4-129">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="973e4-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="973e4-130">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="973e4-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

