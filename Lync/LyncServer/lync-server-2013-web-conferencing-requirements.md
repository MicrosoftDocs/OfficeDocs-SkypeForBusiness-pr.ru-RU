---
title: 'Lync Server 2013: требования к веб-конференциям'
description: 'Lync Server 2013: требования к веб-конференциям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576395"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="e96af-103">Требования к веб-конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e96af-103">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e96af-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e96af-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e96af-105">Если принято решение включить функции веб-конференций, должны быть спланированы следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="e96af-105">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="e96af-106">Доступ к хранилищу файлов, которое используется для хранения содержимого веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="e96af-106">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="e96af-107">Интеграция с сервером Office Web Apps, которая необходима для предоставления общего доступа к файлам PowerPoint во время конференции.</span><span class="sxs-lookup"><span data-stu-id="e96af-107">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="e96af-108">Хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="e96af-108">File Store</span></span>

<span data-ttu-id="e96af-109">Служба веб-конференций Lync Server 2013 хранит содержимое, доступное во время собраний в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="e96af-109">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="e96af-110">В рамках развертывания необходимо указать файловый ресурс, который будет использоваться в качестве хранилища файлов для пула переднего плана сервера Standard Edition или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e96af-110">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="e96af-111">Для хранилища файлов можно использовать существующий общий файловый ресурс или можно указать новый совместно используемый файловый ресурс, задав полное доменное имя файлового сервера, на котором будет находиться общий файловый ресурс, а также имя папки для этого нового файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="e96af-111">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="e96af-112">Дополнительные сведения см. в разделе "Построитель топологии – определение файлового хранилища для клиентского сервера".</span><span class="sxs-lookup"><span data-stu-id="e96af-112">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="e96af-113">Перед сохранением содержимого в хранилище файлов содержимое шифруется службой веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="e96af-113">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="e96af-114">Lync Server 2013 поддерживает использование общих файловых ресурсов в хранилище с прямым подключением (DAS) или сети хранения (SAN), включая распределенную файловую систему (DFS) и резервный массив дисков (RAID) для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="e96af-114">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="e96af-115">После определения расположения общего файлового ресурса мастером развертывания Lync Server, Lync Server создает структуру папок в общем файловом ресурсе, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e96af-115">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="e96af-116">1 — ApplicationServer – 1</span><span class="sxs-lookup"><span data-stu-id="e96af-116">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="e96af-117">1 — Централмгмт – 1</span><span class="sxs-lookup"><span data-stu-id="e96af-117">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="e96af-118">1 — WebService — 1</span><span class="sxs-lookup"><span data-stu-id="e96af-118">1-WebServices-1</span></span>
    
      - <span data-ttu-id="e96af-119">CollabContent</span><span class="sxs-lookup"><span data-stu-id="e96af-119">CollabContent</span></span>
    
      - <span data-ttu-id="e96af-120">"Collabmetadata"</span><span class="sxs-lookup"><span data-stu-id="e96af-120">CollabMetadata</span></span>
    
      - <span data-ttu-id="e96af-121">CONF</span><span class="sxs-lookup"><span data-stu-id="e96af-121">DataConf</span></span>

<span data-ttu-id="e96af-122">После этого содержимое, такое как слайды PowerPoint, доски, опросы и вложения, сохраняется службой веб-конференций в папках "CollabContent" и "CollabMetadata", расположенных в папке "WebServices".</span><span class="sxs-lookup"><span data-stu-id="e96af-122">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="e96af-123">Администратор должен установить разрешения для общей папки, чтобы RTC-группы обладали необходимыми правами на чтение и запись данных.</span><span class="sxs-lookup"><span data-stu-id="e96af-123">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e96af-p103">Если обнаружены какие-либо ошибки, связанные с разрешениями, откройте построитель топологий, загрузите и повторно опубликуйте существующую топологию. При публикации топологии проверяются разрешения для общей папки, и при необходимости они сбрасываются в исходное состояние.</span><span class="sxs-lookup"><span data-stu-id="e96af-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="e96af-126">Для управления порядком хранения содержимого собраний можно использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e96af-126">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="e96af-127">**Контентграцепериод**, расположенный в [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), определяет, как долго содержимое веб-конференций останется на сервере после завершения собрания.</span><span class="sxs-lookup"><span data-stu-id="e96af-127">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="e96af-128">**Максконтентсторажемб**, расположенный в [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), задает максимальный объем дискового пространства, разрешенного для хранения контента во время одного собрания.</span><span class="sxs-lookup"><span data-stu-id="e96af-128">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="e96af-129">**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="e96af-129">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="e96af-130">В качестве ограничения на загрузку размера файла для Lync Web App задано значение приблизительно 30MB и оно управляется файлом IIS web.config:/Датаколлабвеб/Инт \[ ext \] /Хандлер/web.config. Для настройки ограничения на загрузку размера файлов для Lync Web App, обновления `maxRequestLength` и `maxAllowedContentLength` в файле web.config, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e96af-130">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="e96af-131">Необходимо обновить файл web.config для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e96af-131">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="e96af-132">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e96af-132">Office Web Apps Server</span></span>

<span data-ttu-id="e96af-133">Чтобы использовать эти новые возможности, администраторы должны установить сервер Office Web Apps, и они должны настроить Lync Server 2013 для связи с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e96af-133">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="e96af-134">В этой документации представлены сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e96af-134">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="e96af-135">Сведения о том, как установить сервер Office Web Apps, не предоставляются в документации.</span><span class="sxs-lookup"><span data-stu-id="e96af-135">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="e96af-136">Сведения об установке можно найти на веб-сайте развертывания Microsoft Office Web Apps по адресу <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="e96af-136">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="e96af-137">Это руководство включает полные сведения о необходимых требованиях для сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e96af-137">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="e96af-138">Обратите внимание на то, что сервер Office Web Apps должен быть установлен на автономном компьютере, на котором не работает Lync Server, SQL Server или другие серверные приложения.</span><span class="sxs-lookup"><span data-stu-id="e96af-138">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="e96af-139">(На компьютере не должна быть установлена какая-либо версия Office.) На любом компьютере, используемом для запуска сервера Office Web Apps, также должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="e96af-139">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="e96af-140">Эти требования, а также сведения о настройке сертификатов и служб IIS, подробно обсуждаются на веб-сайте развертывания Microsoft Office Web Apps по адресу <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="e96af-140">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e96af-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e96af-141">See Also</span></span>


[<span data-ttu-id="e96af-142">Обзор веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e96af-142">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="e96af-143">Контрольный список развертывания для веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e96af-143">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

