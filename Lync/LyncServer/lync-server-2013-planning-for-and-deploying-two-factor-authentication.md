---
title: 'Lync Server 2013: планирование и развертывание двухфакторной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b891f20b07f1d60be3d392ef6576e03e89ef1158
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="631e9-102">Двухфакторная проверка подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="631e9-102">Two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="631e9-103">_**Последнее изменение темы:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="631e9-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="631e9-104">Двухфакторная проверка подлинности обеспечивает повышенную безопасность, требуя от пользователей соответствия двум критериям проверки подлинности: комбинации имени пользователя и пароля, а также маркера или сертификата.</span><span class="sxs-lookup"><span data-stu-id="631e9-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="631e9-105">Это также называется "что-то известно".</span><span class="sxs-lookup"><span data-stu-id="631e9-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="631e9-106">Типичным примером двухфакторной проверки подлинности с помощью сертификата является использование смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="631e9-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="631e9-107">Смарт-карта содержит сертификат, связанный с учетной записью пользователя, и его можно проверить по сведениям о пользователях и сертификатах, хранящихся на сервере.</span><span class="sxs-lookup"><span data-stu-id="631e9-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="631e9-108">Сравнивая сведения о пользователе (имя пользователя и пароль) с предоставленным сертификатом, сервер проверяет учетные данные и выполняет проверку подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="631e9-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="631e9-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="631e9-109">In This Section</span></span>

[<span data-ttu-id="631e9-110">Планирование двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="631e9-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="631e9-111">Настройка двухфакторной проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="631e9-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="631e9-112">Применение двухфакторной проверки подлинности с клиентом Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="631e9-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

