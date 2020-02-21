---
title: 'Lync Server 2013: выполнение искусственных транзакций'
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
ms.openlocfilehash: 476223c1c81f6927a1b5f96a78091e0f3c57ea12
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="f2488-102">Выполнение искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2488-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2488-103">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f2488-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f2488-104">Искусственные транзакции обычно выполняются двумя способами.</span><span class="sxs-lookup"><span data-stu-id="f2488-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="f2488-105">Командлеты CsHealthMonitoringConfiguration можно использовать для настройки тестовых пользователей для каждого из пулов регистраторов.</span><span class="sxs-lookup"><span data-stu-id="f2488-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="f2488-106">Эти тестовые пользователи являются пользователями, предварительно настроенными для использования с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="f2488-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="f2488-107">(Как правило, это тестовые учетные записи, а не учетные записи, принадлежащие реальным пользователям.) При использовании тестовых пользователей, настроенных для пула, можно выполнить искусственную транзакцию для этого пула без необходимости указывать удостоверения (и предоставлять учетные данные) для учетных записей пользователей, участвующих в тестировании.</span><span class="sxs-lookup"><span data-stu-id="f2488-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="f2488-108">Вы также можете выполнить искусственную транзакцию с помощью фактических учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2488-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="f2488-109">Например, если два пользователя не могут обмениваться мгновенными сообщениями, можно выполнить искусственную транзакцию с использованием этих двух учетных записей пользователей (а не из двух тестовых учетных записей), а затем попробовать диагностировать и устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="f2488-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="f2488-110">Если вы решили провести искусственную транзакцию с использованием фактических учетных записей пользователей, необходимо указать имена и пароли для входа для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f2488-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f2488-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f2488-111">See Also</span></span>


[<span data-ttu-id="f2488-112">Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2488-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="f2488-113">Специальные инструкции по настройке для искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2488-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

