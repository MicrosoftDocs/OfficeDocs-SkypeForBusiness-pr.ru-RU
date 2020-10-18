---
title: Создание или изменение коллекции параметров конфигурации Lync Phone Edition
description: Создание или изменение коллекции параметров конфигурации Lync Phone Edition.
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
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578255"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="54924-103">Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54924-103">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54924-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="54924-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="54924-105">При установке Lync Server вы получаете глобальную коллекцию параметров Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="54924-105">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="54924-106">Эти параметры применяются ко всем устройствам с Lync Phone Edition в развертывании.</span><span class="sxs-lookup"><span data-stu-id="54924-106">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="54924-107">Вы можете изменить эти настройки в любое время.</span><span class="sxs-lookup"><span data-stu-id="54924-107">You can change these settings at any time.</span></span> <span data-ttu-id="54924-108">Вы также можете настроить новую коллекцию параметров, которая применяется к устройствам в определенном узле.</span><span class="sxs-lookup"><span data-stu-id="54924-108">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="54924-109">Параметры узла имеют более высокий приоритет, чем глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="54924-109">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="54924-110">Параметры конфигурации состоят из имени коллекции, области (глобальная или узел), параметра безопасности SIP, уровня ведения журнала, уровня качества обслуживания (QoS) голосовой связи, параметра блокировки телефона и сведений о блокировке, т. е. а) каким по длине должен быть ПИН-код для разблокировки и б) как долго телефон может быть неактивным до автоматической блокировки.</span><span class="sxs-lookup"><span data-stu-id="54924-110">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="54924-111">Создание коллекции параметров конфигурации Lync Phone Edition или изменение параметров для существующей коллекции</span><span class="sxs-lookup"><span data-stu-id="54924-111">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="54924-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54924-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54924-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54924-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54924-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54924-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54924-115">На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Конфигурация устройства**.</span><span class="sxs-lookup"><span data-stu-id="54924-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="54924-116">На странице **Конфигурация устройства** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="54924-116">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="54924-117">Чтобы создать новую коллекцию параметров конфигурации Lync Phone Edition, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, просмотрите параметры по умолчанию и, если необходимо, внесите изменения.</span><span class="sxs-lookup"><span data-stu-id="54924-117">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="54924-118">Чтобы изменить параметры существующей коллекции, щелкните ее, откройте меню **Правка**, щелкните **Показать подробности** и внесите изменения.</span><span class="sxs-lookup"><span data-stu-id="54924-118">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="54924-p103">Чтобы вернуться к параметрам глобальной коллекции по умолчанию, откройте меню <STRONG>Правка</STRONG>, щелкните <STRONG>Удалить</STRONG> и нажмите кнопку <STRONG>ОК</STRONG>. При этом глобальная коллекция не удаляется, просто восстанавливаются настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54924-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="54924-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="54924-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54924-122">Создание новых параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54924-122">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="54924-123">Вы можете создать параметры конфигурации Lync Phone Edition (только на уровне сайта) с помощью Windows PowerShell и командлета **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="54924-123">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="54924-124">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54924-124">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="54924-125">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="54924-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="54924-126">Создание новых параметров конфигурации Lync Phone Edition, использующих значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="54924-126">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="54924-127">Эта команда создает новый набор параметров конфигурации телефона UC для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="54924-127">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="54924-128">Так как в предыдущей команде не были указаны параметры (кроме обязательного параметра Identity), новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="54924-128">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="54924-129">Изменение значения отдельного свойства при создании новых параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="54924-129">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="54924-p105">Чтобы создать параметры, использующие разные значения свойств, просто укажите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации телефона UC, которые требуют блокировки телефона по умолчанию, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54924-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="54924-132">Изменение значений нескольких свойств при создании новых параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="54924-132">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="54924-p106">Значения нескольких свойств можно изменить, указав несколько параметров. Например, следующая команда применяет блокировку телефона и также задает минимальную длину ПИН-кода (8 разрядов):</span><span class="sxs-lookup"><span data-stu-id="54924-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="54924-135">Дополнительные сведения см. в разделе [New – CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="54924-135">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54924-136">См. также</span><span class="sxs-lookup"><span data-stu-id="54924-136">See Also</span></span>


[<span data-ttu-id="54924-137">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54924-137">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="54924-138">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54924-138">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="54924-139">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54924-139">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

