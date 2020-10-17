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
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518716"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e3f38-102">Проверка доступа через обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3f38-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3f38-103">_**Последнее изменение темы:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="e3f38-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="e3f38-p101">Используйте следующую процедуру, чтобы удостовериться, что пользователи могут получать доступ к информации на обратном прокси-сервере. Вам может потребоваться завершить настройку брандмауэра и DNS, чтобы обеспечить доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="e3f38-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="e3f38-106">Проверка доступа к веб-сайту через Интернет</span><span class="sxs-lookup"><span data-stu-id="e3f38-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="e3f38-107">Откройте браузер, введите в строке **адреса** URL-адреса, которые клиенты будут использовать для доступа к файлам адресной книги, и адрес веб-сайта для проведения конференций следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3f38-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="e3f38-108">В поле адрес сервера адресной книги введите URL-адрес, подобный следующему: **https://externalwebfarmFQDN/abs** где екстерналвебфармфкдн — это внешнее полное доменное имя внешних веб-служб, в которых размещаются службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="e3f38-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="e3f38-109">Пользователь должен получить HTTP-запрос, поскольку безопасность каталогов в папке адресной книги настроена для использования проверки подлинности Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3f38-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="e3f38-110">Для конференции введите URL-адрес, подобный следующему: **https://externalwebfarmFQDN/meet** где екстерналвебфармфкдн — это внешнее полное доменное имя веб-фермы, в которой размещается содержимое собраний.</span><span class="sxs-lookup"><span data-stu-id="e3f38-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="e3f38-111">Этот URL-адрес должен отображать страницу устранения неисправностей для конференций.</span><span class="sxs-lookup"><span data-stu-id="e3f38-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="e3f38-112">Или же убедитесь, что простой URL-адрес для конференций работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e3f38-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="e3f38-113">Например, простой URL-адрес для присоединения к Конференции может быть https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e3f38-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="e3f38-114">Для расширения группы рассылки введите URL-адрес, подобный следующему: **https://externalwebfarmFQDN/GroupExpansion/service.svc** .</span><span class="sxs-lookup"><span data-stu-id="e3f38-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="e3f38-115">Пользователь должен получить HTTP-запрос, поскольку безопасность каталогов для службы расширения группы рассылки настроена для использования проверки подлинности Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3f38-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="e3f38-116">Для телефонного подключения введите простой URL-адрес, подобный приведенному ниже, **https://externalwebfarmFQDN/dialin** где екстерналвебфармфкдн — это внешнее полное доменное имя веб-фермы, в которой размещается страница для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e3f38-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="e3f38-117">Пользователь должен направляться на страницу конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e3f38-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="e3f38-118">Или же убедитесь, что простой URL-адрес для конференций работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e3f38-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="e3f38-119">Например, простой URL-адрес для телефонного подключения может быть https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e3f38-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="e3f38-120">Чтобы убедиться, что URL-адрес службы автообнаружения работает, введите https://lyncdiscover .</span><span class="sxs-lookup"><span data-stu-id="e3f38-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="e3f38-121">Екстерналдомаинфкдн.</span><span class="sxs-lookup"><span data-stu-id="e3f38-121">externaldomainFQDN.</span></span> <span data-ttu-id="e3f38-122">Браузер должен предложить открыть файл.</span><span class="sxs-lookup"><span data-stu-id="e3f38-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="e3f38-123">Выберите "Блокнот", чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="e3f38-123">Select Notepad to open it.</span></span> <span data-ttu-id="e3f38-124">Типичный ответ будет похож на следующий:</span><span class="sxs-lookup"><span data-stu-id="e3f38-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

