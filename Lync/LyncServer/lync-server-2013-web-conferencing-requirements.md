---
title: 'Lync Server 2013: требования для веб-конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Требования для веб-конференций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

Если принято решение включить функции веб-конференций, должны быть спланированы следующие компоненты:

  - <span></span>  
    Доступ к хранилищу файлов, которое используется для хранения содержимого веб-конференций.

  - <span></span>  
    Взаимодействие с сервером с Office Web Apps, необходимое для предоставления доступа к файлам PowerPoint во время конференции.

<div>

## <a name="file-store"></a>файлов

Служба веб-конференций Lync Server 2013 хранит содержимое, к которому предоставлен общий доступ во время собраний в хранилище файлов. В рамках развертывания необходимо указать общую файловую группу, которая будет использоваться в качестве хранилища файлов для пула стандартных интерфейсов сервера Standard Edition или Enterprise Edition. Вы можете использовать существующую общую папку для хранения файлов или задать новую общую папку, указав полное доменное имя (FQDN) файлового сервера, для которого нужно найти общую папку, и имя папки для нового общего файлового файла.Дополнительные сведения можно найти в разделе Topology Builder — определение хранилища файлов для интерфейса пользователя. Перед сохранением материалов в хранилище файлов службы веб-конференций эти материалы шифруются.

Lync Server 2013 поддерживает использование общих папок в хранилище с прямым подключением (DAS) или в сети хранения данных (SAN), включая распределенную файловую систему (DFS) и на избыточный массив независимых дисков (RAID) для хранения файлов. После того как мастер развертывания Lync Server заопределил расположение общего файлового ресурса, Lync Server создаст структуру папок в общей папке, как показано ниже.

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

После этого содержимое, такое как слайды PowerPoint, доски, опросы и вложения, сохраняется службой веб-конференций в папках "CollabContent" и "CollabMetadata", расположенных в папке "WebServices".

Администратор должен установить разрешения на доступ к общему файловому файлу, чтобы группы на часах имели необходимые права на чтение и запись.

<div>


> [!WARNING]  
> Если у вас возникли ошибки с разрешениями, откройте конфигуратор топологии, скачайте и повторно опубликуйте существующую топологию. При публикации топологии будут проверены разрешения на доступ к файлам и при необходимости сбросить их.



</div>

Ниже перечислены параметры, которые можно использовать для управления хранением контента для собраний.

  - **Контентграцепериод**, который находится в [Set-ксконференЦингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), задает время, в течение которого содержимое веб-конференций останется на сервере после завершения собрания.

  - **Максконтентсторажемб**, расположенная в [Set-ксконференЦингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), задает максимальный объем дискового пространства, разрешенного для хранения содержимого во время одного собрания.

**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App. Для приложения Lync Web App задано значение "примерно 30MB", а управление IIS Web. config —/Датаколлабвеб/Инт\[ext\]/Хандлер/веб.Конфиг.. Чтобы настроить предельный размер для отправки файлов в Lync Web App `maxRequestLength` , `maxAllowedContentLength` Update и в файле Web. config, как показано ниже.

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

Вы должны обновить файл Web. config для каждого сервера переднего плана.

</div>

<div>

## <a name="office-web-apps-server"></a>Сервер Office Web Apps

Для использования этих новых возможностей администраторы должны установить Office Web Apps Server, и они должны настроить Lync Server 2013 для взаимодействия с сервером Office Web Apps. В этой документации содержатся сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps. Сведения о том, как установить Office Web Apps, приведены в этой документации. Дополнительные сведения об установке можно найти на веб-сайте развертывания Microsoft Office <http://go.microsoft.com/fwlink/p/?linkid=257525>Web Apps по адресу. Это руководство содержит полные сведения о предварительных требованиях для сервера Office Web Apps. Обратите внимание на то, что сервер Office Web Apps необходимо установить на отдельном компьютере, на котором не установлен Lync Server, SQL Server или другое серверное приложение. (На компьютере не должна быть установлена какая-либо версия Office.) На любом компьютере, который использовался для запуска Office Web Apps, должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0). Эти требования, а также сведения о настройке сертификатов и информационных служб Интернета (IIS) подробно описаны на веб-сайте развертывания Microsoft Office Web Apps по адресу <http://go.microsoft.com/fwlink/p/?linkid=257525>.

</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения о веб-конференциях в Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Контрольный список развертывания для веб-конференций в Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

