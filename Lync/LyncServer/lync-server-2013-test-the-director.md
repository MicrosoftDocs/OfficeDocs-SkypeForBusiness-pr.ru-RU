---
title: 'Lync Server 2013: проверка директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82b8b7e494a66cf38fd27e37f322c79e95f801c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="e33cf-102">Проверка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33cf-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e33cf-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e33cf-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e33cf-104">На этом этапе вы настроили режиссер или режиссер, но ваши записи SRV доменных имен (DNS) по-прежнему указывают клиентам на необходимость входа в систему с помощью пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e33cf-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="e33cf-105">Перед изменением записи DNS для автоматического входа пользователей Lync 2013 с помощью режиссера протестируйте клиент, указав его вручную.</span><span class="sxs-lookup"><span data-stu-id="e33cf-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="e33cf-106">Тестирование развертывания</span><span class="sxs-lookup"><span data-stu-id="e33cf-106">To test the deployment</span></span>

1.  <span data-ttu-id="e33cf-107">Войдите в систему на компьютере, на котором установлена панель управления Lync Server, с учетной записью домена, которая входит в состав группы **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="e33cf-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="e33cf-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e33cf-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e33cf-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e33cf-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e33cf-110">В области навигации щелкните **топология**и в столбце **состояние** убедитесь, что у вас есть зеленый сервер со стрелкой (то есть ![с зеленой стрелкой](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Значок сервера с зеленой стрелкой")) для вашего директора или режиссера.</span><span class="sxs-lookup"><span data-stu-id="e33cf-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="e33cf-111">Подключите два клиентских компьютера, на которых установлен клиент Lync Server 2013, и войдите в систему с помощью учетной записи, которая включена для Lync Server 2013 на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="e33cf-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="e33cf-112">На одном из клиентских компьютеров откройте меню **Параметры** , выберите пункт Группа **личных** параметров, нажмите **Дополнительно**, выберите **Конфигурация вручную**, а затем укажите в качестве **имени внутреннего сервера или IP-адреса** полное доменное имя (FQDN) нового директора или режиссера.</span><span class="sxs-lookup"><span data-stu-id="e33cf-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="e33cf-113">Войдите в систему обоих клиентов и убедитесь в том, что клиент, войдя в систему с помощью режиссера, может войти в систему успешно, просмотреть состояние присутствия другого пользователя, а также обмениваться мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e33cf-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

