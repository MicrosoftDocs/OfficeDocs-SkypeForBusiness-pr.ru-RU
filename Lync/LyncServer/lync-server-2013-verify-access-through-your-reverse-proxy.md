---
title: 'Lync Server 2013: Проверка доступа через обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Проверка доступа через обратный прокси-сервер в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-29_

Используйте следующую процедуру, чтобы удостовериться, что пользователи могут получать доступ к информации на обратном прокси-сервере. Вам может потребоваться завершить настройку брандмауэра и DNS, чтобы обеспечить доступ к данным.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Проверка доступа к веб-сайту через Интернет

  - Откройте браузер, введите в строке **адреса** URL-адреса, которые клиенты будут использовать для доступа к файлам адресной книги, и адрес веб-сайта для проведения конференций следующим образом:
    
      - В поле адрес сервера адресной книги введите URL-адрес, подобный **https://externalwebfarmFQDN/abs** следующему: где екстерналвебфармфкдн — это внешнее полное доменное имя внешних веб-служб, в которых размещаются службы адресной книги. Пользователь должен получить HTTP-запрос, поскольку безопасность каталогов в папке адресной книги настроена для использования проверки подлинности Windows по умолчанию.
    
      - Для конференции введите URL-адрес, подобный следующему: **https://externalwebfarmFQDN/meet** где екстерналвебфармфкдн — это внешнее полное доменное имя веб-фермы, в которой размещается содержимое собраний. Этот URL-адрес должен отображать страницу устранения неисправностей для конференций. Или же убедитесь, что простой URL-адрес для конференций работает правильно. Например, простой URL-адрес для присоединения к Конференции может бытьhttps://meet.contoso.com
    
      - Для расширения группы рассылки введите URL-адрес, подобный следующему: **https://externalwebfarmFQDN/GroupExpansion/service.svc**. Пользователь должен получить HTTP-запрос, поскольку безопасность каталогов для службы расширения группы рассылки настроена для использования проверки подлинности Windows по умолчанию.
    
      - Для телефонного подключения введите простой URL-адрес, подобный приведенному ниже **https://externalwebfarmFQDN/dialin** , где екстерналвебфармфкдн — это внешнее полное доменное имя веб-фермы, в которой размещается страница для конференц-связи с телефонным подключением. Пользователь должен направляться на страницу конференц-связи с телефонным подключением. Или же убедитесь, что простой URL-адрес для конференций работает правильно. Например, простой URL-адрес для телефонного подключения может бытьhttps://dialin.contoso.com
    
      - Чтобы убедиться, что URL-адрес службы автообнаружения работает https://lyncdiscover, введите. Екстерналдомаинфкдн. Браузер должен предложить открыть файл. Выберите "Блокнот", чтобы открыть его. Типичный ответ будет похож на следующий:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

