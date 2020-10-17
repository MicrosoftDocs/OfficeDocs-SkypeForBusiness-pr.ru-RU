---
title: 'Lync Server 2013: выполнение искусственных транзакций'
description: 'Lync Server 2013: выполнение искусственных транзакций.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569355"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="c69b6-103">Выполнение искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69b6-103">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c69b6-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="c69b6-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="c69b6-105">Искусственные транзакции обычно выполняются двумя способами.</span><span class="sxs-lookup"><span data-stu-id="c69b6-105">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="c69b6-106">Командлеты CsHealthMonitoringConfiguration можно использовать для настройки тестовых пользователей для каждого из пулов регистраторов.</span><span class="sxs-lookup"><span data-stu-id="c69b6-106">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="c69b6-107">Эти тестовые пользователи являются пользователями, предварительно настроенными для использования с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="c69b6-107">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="c69b6-108">(Как правило, это тестовые учетные записи, а не учетные записи, принадлежащие реальным пользователям.) При использовании тестовых пользователей, настроенных для пула, можно выполнить искусственную транзакцию для этого пула без необходимости указывать удостоверения (и предоставлять учетные данные) для учетных записей пользователей, участвующих в тестировании.</span><span class="sxs-lookup"><span data-stu-id="c69b6-108">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="c69b6-109">Вы также можете выполнить искусственную транзакцию с помощью фактических учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="c69b6-109">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="c69b6-110">Например, если два пользователя не могут обмениваться мгновенными сообщениями, можно выполнить искусственную транзакцию с использованием этих двух учетных записей пользователей (а не из двух тестовых учетных записей), а затем попробовать диагностировать и устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c69b6-110">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="c69b6-111">Если вы решили провести искусственную транзакцию с использованием фактических учетных записей пользователей, необходимо указать имена и пароли для входа для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c69b6-111">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c69b6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c69b6-112">See Also</span></span>


[<span data-ttu-id="c69b6-113">Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69b6-113">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="c69b6-114">Специальные инструкции по настройке для искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69b6-114">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

