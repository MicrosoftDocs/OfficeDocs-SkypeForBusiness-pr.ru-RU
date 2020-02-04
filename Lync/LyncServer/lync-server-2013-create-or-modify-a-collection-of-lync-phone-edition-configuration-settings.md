---
title: Создание и изменение коллекции параметров конфигурации Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="52462-102">Создание и изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52462-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52462-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="52462-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="52462-104">При установке сервера Lync Server вы получаете глобальную коллекцию параметров Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="52462-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="52462-105">Эти параметры применяются ко всем устройствам, на которых работает Lync Phone Edition в развертывании.</span><span class="sxs-lookup"><span data-stu-id="52462-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="52462-106">Вы можете в любое время изменить эти параметры.</span><span class="sxs-lookup"><span data-stu-id="52462-106">You can change these settings at any time.</span></span> <span data-ttu-id="52462-107">Вы также можете настроить новый набор параметров, которые применяются к устройствам на определенном сайте.</span><span class="sxs-lookup"><span data-stu-id="52462-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="52462-108">Параметры сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="52462-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="52462-109">Параметры конфигурации включают имя коллекции, область (Global или site), параметр безопасности SIP, уровень ведения журнала, уровень обслуживания голоса (QoS), параметр блокировки телефона и данные блокировки телефона, то есть как долго a) разблокировки персональный идентификационный номер ( ПИН-код) должен быть и b) телефон не оставался бездействиям, прежде чем он будет заблокирован.</span><span class="sxs-lookup"><span data-stu-id="52462-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="52462-110">Создание коллекции параметров конфигурации Lync Phone Edition или изменение параметров для существующей коллекции</span><span class="sxs-lookup"><span data-stu-id="52462-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="52462-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="52462-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="52462-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52462-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52462-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52462-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52462-114">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации устройства** .</span><span class="sxs-lookup"><span data-stu-id="52462-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="52462-115">На странице **Конфигурация устройства** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="52462-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="52462-116">Чтобы создать коллекцию параметров конфигурации Lync Phone Edition, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="52462-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="52462-117">Чтобы изменить параметры в существующей коллекции, щелкните ее, выберите в меню **Правка** команду **Показать подробности**и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="52462-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="52462-118">Чтобы вернуться к использованию параметров по умолчанию для глобальной коллекции, щелкните глобальную коллекцию, выберите в меню <STRONG>Правка</STRONG> команду <STRONG>Удалить</STRONG>, а затем нажмите кнопку <STRONG>ОК</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="52462-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="52462-119">Это не приведет к удалению глобальной коллекции; оно просто восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52462-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="52462-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="52462-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="52462-121">Создание новых параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52462-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="52462-122">Вы можете создавать параметры конфигурации Lync Phone Edition (только на уровне сайта) с помощью Windows PowerShell и командлета **New-ксукфонеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="52462-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="52462-123">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52462-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="52462-124">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52462-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="52462-125">Создание новых параметров конфигурации Lync Phone Edition, использующих значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="52462-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="52462-126">Эта команда создает новый набор параметров конфигурации телефона в UC для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="52462-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="52462-127">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="52462-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="52462-128">Изменение одного значения свойства при создании новых параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="52462-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="52462-129">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="52462-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="52462-130">Например, чтобы создать коллекцию параметров настройки телефонной связи UC, которая по умолчанию требует блокировки на телефоне, используйте такую команду:</span><span class="sxs-lookup"><span data-stu-id="52462-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="52462-131">Изменение нескольких значений свойства при создании новых параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="52462-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="52462-132">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="52462-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="52462-133">Например, эта команда обеспечивает принудительную блокировку телефона, а также задает минимальную длину ПИН-кода в 8 цифр.</span><span class="sxs-lookup"><span data-stu-id="52462-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="52462-134">Подробности можно найти в разделе [New-ксукфонеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="52462-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52462-135">См. также</span><span class="sxs-lookup"><span data-stu-id="52462-135">See Also</span></span>


[<span data-ttu-id="52462-136">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52462-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="52462-137">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52462-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="52462-138">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52462-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

