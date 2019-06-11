---
title: 'Lync Server 2013: планирование и развертывание двухфакторной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c902a3abd0035cbffa5bb10ed05cad6fa7bcc6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="df54c-102">Двухфакторная проверка подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df54c-102">Two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df54c-103">_**Тема последнего изменения:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="df54c-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="df54c-104">Двухфакторная проверка подлинности обеспечивает повышенную безопасность, требуя пользователей отвечать на два условия проверки подлинности: сочетание имени пользователя и пароля и маркер или сертификат.</span><span class="sxs-lookup"><span data-stu-id="df54c-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="df54c-105">Это сочетание иногда называют "то, что знаешь" и "то, что имеешь".</span><span class="sxs-lookup"><span data-stu-id="df54c-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="df54c-106">Типичным примером двухфакторной проверки подлинности с помощью сертификата может послужить использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="df54c-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="df54c-107">Смарт-карта включает в себя сертификат, связанный с учетной записью пользователя, и проверяется с помощью информации о пользователе и сертификате, хранящейся на сервере.</span><span class="sxs-lookup"><span data-stu-id="df54c-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="df54c-108">Сервер сравнивает информацию о пользователе (имя пользователя и пароль) с представленным сертификатом, в результате чего происходит проверка учетных данных и определяется подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="df54c-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df54c-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="df54c-109">In This Section</span></span>

[<span data-ttu-id="df54c-110">Планирование двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df54c-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="df54c-111">Настройка двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df54c-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="df54c-112">Использование двухфакторной проверки подлинности в клиенте Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df54c-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

