---
title: 'Lync Server 2013: выполнение искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="0fdd4-102">Выполнение виртуальных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fdd4-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fdd4-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="0fdd4-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="0fdd4-104">Синтетические транзакции обычно выполняются двумя способами.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="0fdd4-105">Вы можете использовать командлеты Кшеалсмониторингконфигуратион, чтобы настроить пользователей для каждого из своих пулов регистраторов.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="0fdd4-106">Эти тестовые пользователи — это пары пользователей, которые были предварительно настроены для использования с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="0fdd4-107">(Как правило, они являются тестовыми учетными записями, а не учетными записями, принадлежащими реальным пользователям.) При использовании тестовых пользователей, настроенных для пула, вы можете выполнить искусственную транзакцию для этого пула, не задавая удостоверения (и учетные данные для) учетных записей пользователей, участвующих в тестировании.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="0fdd4-108">Вы также можете выполнить искусственную транзакцию с помощью реальных учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="0fdd4-109">Например, если два пользователя не могут обмениваться мгновенными сообщениями, вы можете выполнить искусственную транзакцию с помощью этих двух учетных записей пользователей (а не для пары тестовых учетных записей), а затем попробовать диагностировать и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="0fdd4-110">Если вы решите провести искусственную транзакцию с использованием фактических учетных записей пользователей, необходимо указать имена для входа и пароли для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fdd4-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0fdd4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0fdd4-111">See Also</span></span>


[<span data-ttu-id="0fdd4-112">Настройка пользователей и параметров конфигурации для проверки узла-наблюдателя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fdd4-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="0fdd4-113">Специальные инструкции по настройке для виртуальных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fdd4-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

