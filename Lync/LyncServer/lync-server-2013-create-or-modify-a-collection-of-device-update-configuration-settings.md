---
title: Создание или изменение коллекции параметров конфигурации обновления устройств
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f58e67a0d1fc8f6b01fecfbab7c7ff7dd8f31d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="15f12-102">Создание или изменение коллекции параметров конфигурации обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15f12-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15f12-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="15f12-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="15f12-104">Параметры конфигурации обновления устройств можно создать (только на уровне сайта) с помощью Windows PowerShell и командлета **New-CsDeviceUpdateConfiguration** , а затем изменить с помощью командлета **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="15f12-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="15f12-105">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15f12-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="15f12-106">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="15f12-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="15f12-107">Создание параметров конфигурации обновления устройств, использующих значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="15f12-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="15f12-108">Эта команда создает новый набор параметров конфигурации обновления устройств для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="15f12-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="15f12-109">Так как в предыдущей команде не были указаны никакие параметры, кроме обязательного параметра Identity, Новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="15f12-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="15f12-110">Изменение значения отдельного свойства при создании параметров конфигурации обновления устройств</span><span class="sxs-lookup"><span data-stu-id="15f12-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="15f12-111">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="15f12-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="15f12-112">Например, чтобы создать коллекцию параметров конфигурации обновления устройств, которые по умолчанию удаляют старые файлы журнала каждые 21 дня, используйте команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="15f12-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="15f12-113">Изменение значений нескольких свойств при создании параметров конфигурации обновления устройств</span><span class="sxs-lookup"><span data-stu-id="15f12-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="15f12-114">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="15f12-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="15f12-115">Например, эта команда задает для интервала очистки журнала значение 21 дня, а в качестве значения интервала сброса журнала — 30 минут:</span><span class="sxs-lookup"><span data-stu-id="15f12-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="15f12-116">Для получения дополнительных сведений об изменении параметров конфигурации устройств обратитесь к разделу "Справка" для командлета [Set – CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="15f12-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="15f12-117">Для получения дополнительных сведений о создании коллекций параметров конфигурации обратитесь к разделу "Справка" для командлета [New – CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="15f12-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

