---
title: 'Lync Server 2013: требования к веб-конференциям'
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
ms.openlocfilehash: 914fee9d2ddf0a7e6d6867879a197b55380d35c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Требования к веб-конференциям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Если принято решение включить функции веб-конференций, должны быть спланированы следующие компоненты:

  - <span></span>  
    Доступ к хранилищу файлов, которое используется для хранения содержимого веб-конференций.

  - <span></span>  
    Интеграция с сервером Office Web Apps, которая необходима для предоставления общего доступа к файлам PowerPoint во время конференции.

<div>

## <a name="file-store"></a>Хранилище файлов

Служба веб-конференций Lync Server 2013 хранит содержимое, доступное во время собраний в хранилище файлов. В рамках развертывания необходимо указать файловый ресурс, который будет использоваться в качестве хранилища файлов для пула переднего плана сервера Standard Edition или Enterprise Edition. Для хранилища файлов можно использовать существующий общий файловый ресурс или можно указать новый совместно используемый файловый ресурс, задав полное доменное имя файлового сервера, на котором будет находиться общий файловый ресурс, а также имя папки для этого нового файлового ресурса.Дополнительные сведения см. в разделе "Построитель топологии – определение файлового хранилища для клиентского сервера". Перед сохранением содержимого в хранилище файлов содержимое шифруется службой веб-конференций.

Lync Server 2013 поддерживает использование общих файловых ресурсов в хранилище с прямым подключением (DAS) или сети хранения (SAN), включая распределенную файловую систему (DFS) и резервный массив дисков (RAID) для хранения файлов. После определения расположения общего файлового ресурса мастером развертывания Lync Server, Lync Server создает структуру папок в общем файловом ресурсе, как показано ниже:

  - 1 — ApplicationServer – 1

  - 1 — Централмгмт – 1

  - 1 — WebService — 1
    
      - CollabContent
    
      - "Collabmetadata"
    
      - CONF

После этого содержимое, такое как слайды PowerPoint, доски, опросы и вложения, сохраняется службой веб-конференций в папках "CollabContent" и "CollabMetadata", расположенных в папке "WebServices".

Администратор должен установить разрешения для общей папки, чтобы RTC-группы обладали необходимыми правами на чтение и запись данных.

<div>


> [!WARNING]  
> Если обнаружены какие-либо ошибки, связанные с разрешениями, откройте построитель топологий, загрузите и повторно опубликуйте существующую топологию. При публикации топологии проверяются разрешения для общей папки, и при необходимости они сбрасываются в исходное состояние.



</div>

Для управления порядком хранения содержимого собраний можно использовать следующие параметры:

  - **Контентграцепериод**, расположенный в [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), определяет, как долго содержимое веб-конференций останется на сервере после завершения собрания.

  - **Максконтентсторажемб**, расположенный в [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), задает максимальный объем дискового пространства, разрешенного для хранения контента во время одного собрания.

**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App. В качестве ограничения на загрузку размера файла для Lync Web App задано значение приблизительно 30MB и оно управляется файлом IIS Web. config:\[/Датаколлабвеб/Инт\]ext/Хандлер/веб.Конфиг. Для настройки предельного размера отправляемых файлов для Lync Web App `maxRequestLength` , `maxAllowedContentLength` Update и в файле Web. config, как показано ниже.

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

Необходимо обновить файл Web. config для каждого сервера переднего плана.

</div>

<div>

## <a name="office-web-apps-server"></a>Сервер Office Web Apps

Чтобы использовать эти новые возможности, администраторы должны установить сервер Office Web Apps, и они должны настроить Lync Server 2013 для связи с сервером Office Web Apps. В этой документации представлены сведения о том, как настроить Lync Server 2013 для работы с сервером Office Web Apps. Сведения о том, как установить сервер Office Web Apps, не предоставляются в документации. Сведения об установке можно найти на веб-сайте развертывания Microsoft Office Web <http://go.microsoft.com/fwlink/p/?linkid=257525>Apps по адресу. Это руководство включает полные сведения о необходимых требованиях для сервера Office Web Apps. Обратите внимание на то, что сервер Office Web Apps должен быть установлен на автономном компьютере, на котором не работает Lync Server, SQL Server или другие серверные приложения. (На компьютере не должна быть установлена какая-либо версия Office.) На любом компьютере, используемом для запуска сервера Office Web Apps, также должен быть установлен определенный набор программного обеспечения (включая .NET Framework 4,5 и Windows PowerShell 3,0). Эти требования, а также сведения о настройке сертификатов и служб IIS, подробно обсуждаются на веб-сайте развертывания Microsoft Office Web Apps по адресу <http://go.microsoft.com/fwlink/p/?linkid=257525>.

</div>

<div>

## <a name="see-also"></a>См. также


[Обзор веб-конференций в Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Контрольный список развертывания для веб-конференций в Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

