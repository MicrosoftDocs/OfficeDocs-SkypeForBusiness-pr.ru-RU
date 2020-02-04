---
title: 'Lync Server 2013: Настройка узла наблюдателя для выполнения искусственных транзакций'
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
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="059d9-102">Настройка узла-наблюдателя для выполнения синтетических транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="059d9-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059d9-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="059d9-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="059d9-104">После установки файлов агента System Center вы должны затем настроить сам узел наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="059d9-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="059d9-105">Действия, которые необходимо выполнить для настройки узла-наблюдателя, варьируются в зависимости от того, входит ли компьютер-узел-наблюдатель в вашу сеть периметра или находится за пределами сети периметра.</span><span class="sxs-lookup"><span data-stu-id="059d9-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="059d9-106">При настройке узла-наблюдателя необходимо также выбрать используемый им тип метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="059d9-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="059d9-107">Lync Server 2013 позволяет выбрать один из двух способов проверки подлинности: доверенный сервер или проверка подлинности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="059d9-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="059d9-108">Различия между этими двумя методами описаны в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="059d9-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="059d9-109">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="059d9-109">Configuration</span></span></th>
<th><span data-ttu-id="059d9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="059d9-110">Description</span></span></th>
<th><span data-ttu-id="059d9-111">Поддерживаемые расположения</span><span class="sxs-lookup"><span data-stu-id="059d9-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="059d9-112">Доверенный сервер</span><span class="sxs-lookup"><span data-stu-id="059d9-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="059d9-113">Использует сертификат для олицетворения внутреннего сервера и обхода проблем, связанных с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="059d9-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="059d9-114">Это полезно для администраторов, которые предпочитают управлять единственным сертификатом вместо большого количества паролей пользователей на каждом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="059d9-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="059d9-115">На предприятии.</span><span class="sxs-lookup"><span data-stu-id="059d9-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="059d9-116">Обратите внимание, что при использовании этого метода узел наблюдателя должен находиться в том же домене, что и отслеживаемые пулы.</span><span class="sxs-lookup"><span data-stu-id="059d9-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="059d9-117">Если узел наблюдателя и отслеживаемые пулы находятся в разных доменах, вместо этого используйте проверку подлинности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="059d9-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="059d9-118">Проверка подлинности учетных данных</span><span class="sxs-lookup"><span data-stu-id="059d9-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="059d9-119">Надежно сохраняет имена пользователей и пароли в диспетчере учетных данных Windows на каждом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="059d9-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="059d9-120">Этот режим требует больше управления паролями, но является единственным вариантом для узлов наблюдения за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="059d9-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="059d9-121">Эти узлы-наблюдатели не могут рассматриваться как доверенные конечные точки при прохождении проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="059d9-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="059d9-122">Вне предприятия.</span><span class="sxs-lookup"><span data-stu-id="059d9-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="059d9-123">На предприятии.</span><span class="sxs-lookup"><span data-stu-id="059d9-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="059d9-124">Кроме того, необходимо убедиться в том, что брандмауэр имеет правила для входящих подключений для Мониторингхост. exe и PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="059d9-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="059d9-125">Если эти процессы заблокированы брандмауэром, эти транзакции не завершатся сбоем с ошибкой 504 (таймаут сервера).</span><span class="sxs-lookup"><span data-stu-id="059d9-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

