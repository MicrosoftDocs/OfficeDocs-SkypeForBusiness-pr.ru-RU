---
title: Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576fcb445eb37b92356ad9fdf36de716581ca6fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="283cf-102">Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283cf-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="283cf-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="283cf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="283cf-p101">Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).</span><span class="sxs-lookup"><span data-stu-id="283cf-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="283cf-106">При установке Lync Server создается глобальная коллекция параметров конфигурации пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="283cf-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="283cf-107">Кроме того, с помощью командлета Windows PowerShell и командлета New-CsAVEdgeConfiguration можно создавать новые параметры на уровне сайта или на уровне службы (то есть для отдельного пограничного сервера аудио-и видеоданных).</span><span class="sxs-lookup"><span data-stu-id="283cf-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="283cf-108">При создании новых параметров следует помнить о следующем.</span><span class="sxs-lookup"><span data-stu-id="283cf-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="283cf-109">Параметры, настроенные на уровне службы (то есть на каждом отдельном сервере), имеют самый высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="283cf-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="283cf-p103">Параметры, настроенные на уровне сайта, имеют приоритет над параметрами, настроенными на глобальном уровне. Однако они переопределяются параметрами на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="283cf-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="283cf-112">Параметры глобального уровня будут использоваться, только если отсутствуют параметры служб, настроенные на отдельном сервере, а также отсутствуют параметры сайта, в котором расположен тот или иной сервер.</span><span class="sxs-lookup"><span data-stu-id="283cf-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="283cf-113">Любой из параметров может быть изменен с помощью командлета Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="283cf-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="283cf-114">Для получения дополнительных сведений обратитесь к разделам справки для командлетов [New – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) и [Set – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="283cf-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="283cf-115">Создание новых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="283cf-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="283cf-116">Следующая команда создает коллекцию параметров конфигурации пограничного сервера аудио- и видеоданных для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="283cf-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="283cf-117">Создание настраиваемых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="283cf-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="283cf-p105">Так как дополнительных параметров не было включено, эти новые параметры будут использовать значения по умолчанию для пограничной службы звука и видео. Кроме того, можно добавить дополнительные параметры и значения параметров для создания пользовательской коллекции. Например, следующая команда задает для свойства MaxTokenLifetime значение 4 часа (04 ч : 00 мин. : 00 сек.):</span><span class="sxs-lookup"><span data-stu-id="283cf-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="283cf-121">Создание настраиваемых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне службы</span><span class="sxs-lookup"><span data-stu-id="283cf-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="283cf-122">Эта команда создает аналогичную коллекцию, примененную к пограничному серверу звука и видео atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="283cf-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="283cf-123">Изменение существующих параметров конфигурации пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="283cf-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="283cf-124">В этом примере командлет Set-CsAVEdgeConfiguration используется для изменения максимального срока жизни маркера для сайта Redmond на 12 часов:</span><span class="sxs-lookup"><span data-stu-id="283cf-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="283cf-125">См. также</span><span class="sxs-lookup"><span data-stu-id="283cf-125">See Also</span></span>


[<span data-ttu-id="283cf-126">Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283cf-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="283cf-127">Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283cf-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="283cf-128">Пограничные серверы аудио/видео (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283cf-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="283cf-129">[New — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="283cf-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="283cf-130">[Set — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="283cf-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

