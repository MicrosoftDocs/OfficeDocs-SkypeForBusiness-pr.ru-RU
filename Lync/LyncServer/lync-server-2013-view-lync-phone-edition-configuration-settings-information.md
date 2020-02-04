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
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="84fb0-102">Просмотр сведений о параметрах конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fb0-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84fb0-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="84fb0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="84fb0-104">Вы можете просматривать сведения о конфигурации устройств, работающих под управлением Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="84fb0-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="84fb0-105">Информация организована в коллекции.</span><span class="sxs-lookup"><span data-stu-id="84fb0-105">The information is organized into collections.</span></span> <span data-ttu-id="84fb0-106">При установке сервера Lync Server вы получаете коллекцию параметров Lync Phone Edition, которые применяются ко всем устройствам, использующим Lync Phone Edition в развертывании.</span><span class="sxs-lookup"><span data-stu-id="84fb0-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="84fb0-107">Вы также можете создать новые наборы параметров для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="84fb0-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="84fb0-108">Параметры сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="84fb0-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="84fb0-109">Каждая коллекция параметров состоит из имени, области (глобального или сайта), параметров безопасности SIP, уровня ведения журнала, уровня обслуживания голоса, настройки блокировки телефона и сведений о блокировке телефона, то есть минимальной длины личной идентификации. номер (ПИН-код) и время до блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="84fb0-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="84fb0-110">Просмотр сведений о конфигурации устройств с Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="84fb0-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="84fb0-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="84fb0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84fb0-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84fb0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84fb0-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="84fb0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84fb0-114">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации устройства** .</span><span class="sxs-lookup"><span data-stu-id="84fb0-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="84fb0-115">На странице **Конфигурация устройства** выберите коллекцию параметров, сведения о которых вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="84fb0-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="84fb0-116">На главной странице указаны имя, область, параметры безопасности SIP, уровень качества голоса и параметры блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="84fb0-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="84fb0-117">Чтобы просмотреть сведения о уровне ведения журнала и блокировки телефона, щелкните меню " **Правка** ", а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="84fb0-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="84fb0-118">Просмотр сведений о конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84fb0-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="84fb0-119">Вы можете просматривать параметры конфигурации Lync Phone Edition с помощью командной консоли Lync Server Management Shell и командлета **Get-ксукфонеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="84fb0-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="84fb0-120">Этот командлет можно запустить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84fb0-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="84fb0-121">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84fb0-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="84fb0-122">Просмотр сведений о конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="84fb0-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="84fb0-123">Чтобы просмотреть сведения о всех параметрах конфигурации Lync Phone Edition, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="84fb0-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="84fb0-124">Команда возвращает данные, подобные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="84fb0-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="84fb0-125">Подробности можно найти в [статьях Get-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="84fb0-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84fb0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="84fb0-126">See Also</span></span>


[<span data-ttu-id="84fb0-127">Создание и изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fb0-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="84fb0-128">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fb0-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="84fb0-129">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fb0-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="84fb0-130">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fb0-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

