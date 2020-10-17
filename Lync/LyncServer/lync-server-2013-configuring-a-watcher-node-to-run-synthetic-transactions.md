---
title: 'Lync Server 2013: Настройка узла-наблюдателя для запуска искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9514099b3981dafdbb34911d0cedd249221c5621
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499106"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="534d0-102">Настройка узла-наблюдателя для запуска искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="534d0-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="534d0-103">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="534d0-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="534d0-p101">После установки файлов агента System Center необходимо настроить узел-наблюдатель. Действия, выполняемые при настройке узла-наблюдателя, зависят от того, относится ли компьютер, являющийся узлом-наблюдателем, к сети периметра или находится за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="534d0-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="534d0-106">При настройке узла-наблюдателя необходимо также выбрать тип метода проверки подлинности для развертывания этим узлом.</span><span class="sxs-lookup"><span data-stu-id="534d0-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="534d0-107">Lync Server 2013 позволяет выбрать один из двух способов проверки подлинности: доверенный сервер или проверка подлинности с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="534d0-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="534d0-108">Различия между этими двумя методами указаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="534d0-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="534d0-109">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="534d0-109">Configuration</span></span></th>
<th><span data-ttu-id="534d0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="534d0-110">Description</span></span></th>
<th><span data-ttu-id="534d0-111">Поддерживаемые местоположения</span><span class="sxs-lookup"><span data-stu-id="534d0-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="534d0-112">Доверенный сервер</span><span class="sxs-lookup"><span data-stu-id="534d0-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="534d0-113">Использует сертификат для олицетворения внутреннего сервера и обхода проблем, связанных с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="534d0-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="534d0-114">Этот метод подходит для администраторов, которые предпочитают управлять одним сертификатом вместо множества пользовательских паролей на каждом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="534d0-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="534d0-115">На предприятии.</span><span class="sxs-lookup"><span data-stu-id="534d0-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="534d0-p103">Обратите внимание, что при использовании этого метода узел-наблюдатель должен находиться в том же самом домене, что и отслеживаемые пулы. Если узел-наблюдатель и отслеживаемые пулы находятся в разных доменах, используйте метод проверки подлинности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="534d0-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="534d0-118">Проверка подлинности учетных данных</span><span class="sxs-lookup"><span data-stu-id="534d0-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="534d0-119">Надежно сохраняет имена пользователей и пароли в диспетчере учетных данных Windows на каждом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="534d0-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="534d0-p104">При использовании этого режима требуется управление паролями, но это единственный вариант, который можно использовать в том случае, если узлы-наблюдатели находятся за пределами предприятия. Эти узлы-наблюдатели не могут рассматриваться как доверенные конечные точки при прохождении проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="534d0-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="534d0-122">Вне предприятия.</span><span class="sxs-lookup"><span data-stu-id="534d0-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="534d0-123">На предприятии.</span><span class="sxs-lookup"><span data-stu-id="534d0-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="534d0-124">Кроме того, необходимо убедиться, что брандмауэр имеет правила для входящих подключений как для MonitoringHost.exe, так и для PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="534d0-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="534d0-125">Если брандмауэр блокирует эти процессы, искусственные транзакции завершатся с ошибкой 504 (время ожидания сервера).</span><span class="sxs-lookup"><span data-stu-id="534d0-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

