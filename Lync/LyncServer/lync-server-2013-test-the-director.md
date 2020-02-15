---
title: 'Lync Server 2013: тестирование директора'
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
ms.openlocfilehash: 1da9d365b42e0d8c78de48ac9ffa9a96c51ebc9f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="bfec0-102">Проверка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfec0-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfec0-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bfec0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="bfec0-104">На данном этапе у вас уже есть настроенный директор или пул директоров, но в соответствии с записями SRV системы доменных имен (DNS) клиенты должны входить в систему с использованием пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bfec0-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="bfec0-105">Перед изменением записи DNS для автоматического входа клиентов Lync 2013 с помощью директории протестируйте клиент, указав его вручную.</span><span class="sxs-lookup"><span data-stu-id="bfec0-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="bfec0-106">Тестирование развертывания</span><span class="sxs-lookup"><span data-stu-id="bfec0-106">To test the deployment</span></span>

1.  <span data-ttu-id="bfec0-107">Войдите на компьютер, на котором установлена панель управления Lync Server, с учетной записью домена, которая является частью группы **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="bfec0-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="bfec0-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfec0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfec0-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfec0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfec0-110">В области навигации щелкните **топология**, а в столбце **состояние** подтвердите, что имеется зеленый сервер со стрелкой (то есть ![значок сервера с зеленой стрелкой](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Значок сервера с зеленой стрелкой")) для директора или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="bfec0-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="bfec0-111">Подключите два клиентских компьютера, на которых установлен клиент Lync Server 2013, и войдите в систему с использованием другой учетной записи пользователя, включенной для Lync Server 2013, на каждый компьютер.</span><span class="sxs-lookup"><span data-stu-id="bfec0-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="bfec0-112">На одном из клиентских компьютеров щелкните меню **Параметры**, выберите группу параметров **Личные**, щелкните **Дополнительно**, щелкните **Настроить вручную**, а затем задайте для параметра **Имя или IP-адрес внутреннего сервера** полное доменное имя нового директора или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="bfec0-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="bfec0-113">Выполните вход в систему на обоих клиентских компьютерах и убедитесь, что клиент, которой выполняет вход с помощью директора, может успешно входить в систему, просмотрите состояние присутствия другого пользователя и убедитесь, что они могут обмениваться мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bfec0-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

