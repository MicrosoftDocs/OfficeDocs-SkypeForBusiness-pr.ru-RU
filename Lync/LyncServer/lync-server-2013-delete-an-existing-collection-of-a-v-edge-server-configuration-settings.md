---
title: Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="507de-102">Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507de-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="507de-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="507de-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="507de-p101">Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).</span><span class="sxs-lookup"><span data-stu-id="507de-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="507de-106">При установке Lync Server создается глобальная коллекция параметров конфигурации пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="507de-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="507de-107">Эта глобальная коллекция не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="507de-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="507de-108">Тем не менее, вы можете использовать командлеты Windows PowerShell и Remove-CsAVEdgeConfiguration, чтобы сбросить глобальную коллекцию; Это означает, что все значения свойств в глобальной коллекции будут сброшены в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="507de-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="507de-109">Например, если для свойства MaxTokenLifetime было задано значение 16 часов, для свойства будет возвращено значение по умолчанию, равное 8 часам.</span><span class="sxs-lookup"><span data-stu-id="507de-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="507de-p103">Однако коллекции пользовательских параметров, созданных на уровне сайта или службы, могут быть удалены с помощью командлета Remove-CsAVEdgeConfiguration. Если удалить параметры сайта, пограничные серверы звука и видео в этом сайте будут  управляться глобальными параметрами. Если удалить параметры уровня службы, соответствующий сервер будет управляться параметрами своего сайта, если таковые существуют, или глобальными параметрами, если параметры сайта отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="507de-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="507de-113">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="507de-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="507de-114">Сброс глобальной коллекции</span><span class="sxs-lookup"><span data-stu-id="507de-114">To reset the global collection</span></span>

  - <span data-ttu-id="507de-115">Следующая команда сбрасывает глобальную коллекцию параметров конфигурации пограничного сервера звука и видео:</span><span class="sxs-lookup"><span data-stu-id="507de-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="507de-116">Удаление коллекции из области сайта</span><span class="sxs-lookup"><span data-stu-id="507de-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="507de-117">Данная команда удаляет параметры конфигурации пограничного сервера аудио и видео для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="507de-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="507de-118">Удаление коллекции из области службы</span><span class="sxs-lookup"><span data-stu-id="507de-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="507de-119">Эта команда удаляет параметры, примененные к пограничному серверу звука и видео atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="507de-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="507de-120">См. также</span><span class="sxs-lookup"><span data-stu-id="507de-120">See Also</span></span>


[<span data-ttu-id="507de-121">Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507de-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="507de-122">Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507de-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="507de-123">Пограничные серверы аудио/видео (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507de-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="507de-124">[Remove — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="507de-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

