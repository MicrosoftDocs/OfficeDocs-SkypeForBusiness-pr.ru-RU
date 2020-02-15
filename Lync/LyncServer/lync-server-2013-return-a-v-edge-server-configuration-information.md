---
title: 'Lync Server 2013: возврат сведений о конфигурации пограничного сервера аудио-и видеоданных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d301febef9454a6f43362c245324b019aa60ea1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="4c1db-102">Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1db-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c1db-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4c1db-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4c1db-p101">Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).</span><span class="sxs-lookup"><span data-stu-id="4c1db-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="4c1db-106">Чтобы получить сведения о параметрах конфигурации пограничного сервера аудио-и видеосвязи, используемых в Организации, необходимо использовать Windows PowerShell и командлет Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4c1db-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4c1db-107">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4c1db-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="4c1db-108">Сведения, возвращаемые командлетом Get-CsAVEdgeConfiguration, выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4c1db-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="4c1db-109">Возврат сведений о всех параметрах конфигурации пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="4c1db-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4c1db-110">Следующая команда возвращает сведения о всех параметрах конфигурации пограничной службы обработки аудио- и видеоданных, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="4c1db-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="4c1db-111">Возврат сведений о параметрах конфигурации пограничного сервера аудио-и видеоданных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="4c1db-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4c1db-p103">Чтобы получить сведения об определенном наборе параметров конфигурации для пограничной службы обработки аудио- и видеоданных, укажите идентификатор этого набора при выполнении командлета Get-CsAVEdgeConfiguration. Например, следующая команда возвращает сведения только о тех параметрах, которые применяются к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="4c1db-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="4c1db-114">Возврат сведений о параметрах конфигурации пограничного сервера аудио-и видеоданных на уровне службы</span><span class="sxs-lookup"><span data-stu-id="4c1db-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4c1db-115">Эта команда возвращает сведения только о тех параметрах, которые применяются к определенному пограничному серверу аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="4c1db-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c1db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4c1db-116">See Also</span></span>


[<span data-ttu-id="4c1db-117">Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1db-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="4c1db-118">Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1db-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="4c1db-119">Пограничные серверы аудио/видео (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1db-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

