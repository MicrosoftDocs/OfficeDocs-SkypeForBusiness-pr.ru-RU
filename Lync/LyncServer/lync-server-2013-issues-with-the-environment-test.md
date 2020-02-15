---
title: 'Lync Server 2013: проблемы с тестом среды'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7d077b22c147dd677a5db68636b2c68bfafcf23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="ffb02-102">Проблемы, связанные с проверкой среды в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffb02-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffb02-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ffb02-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ffb02-104">Анализатор соответствия рекомендациям позволяет убедиться, что ваша среда Lync Server 2013 является поддерживаемой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ffb02-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="ffb02-105">В рамках проверки доменных служб Active Directory анализатор соответствия рекомендациям выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ffb02-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="ffb02-106">проверяет лес доменных служб Active Directory и подготовку схемы;</span><span class="sxs-lookup"><span data-stu-id="ffb02-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="ffb02-107">определяет число сайтов и доменов доменных служб Active Directory в развертывании;</span><span class="sxs-lookup"><span data-stu-id="ffb02-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="ffb02-108">проверяет уровни лесов и доменов;</span><span class="sxs-lookup"><span data-stu-id="ffb02-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="ffb02-109">проверяет версию контроллера домена;</span><span class="sxs-lookup"><span data-stu-id="ffb02-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="ffb02-110">определяет домен, конфигурацию и контекст именования схемы;</span><span class="sxs-lookup"><span data-stu-id="ffb02-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="ffb02-111">определяет число пользователей с включенной поддержкой;</span><span class="sxs-lookup"><span data-stu-id="ffb02-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="ffb02-112">проверяет место хранения глобальных параметров доменных служб Active Directory;</span><span class="sxs-lookup"><span data-stu-id="ffb02-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="ffb02-113">Проверяет наличие точек подключения службы (Скпс) для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffb02-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="ffb02-114">определяет версию базы данных.</span><span class="sxs-lookup"><span data-stu-id="ffb02-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="ffb02-115">Устранение проблем со средой</span><span class="sxs-lookup"><span data-stu-id="ffb02-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="ffb02-p102">Если тестирование среды выявило неполадки, вероятно, они вызваны проблемами с конфигурацией Active Directory или уровнем программного обеспечения, запущенного на конкретных серверах. Например, если анализатор соответствия рекомендациям обнаруживает в среде контроллеры домена, работающие под управлением Windows Server 2000, он выдает предупреждение, и вам потребуется обновить такие контроллеры до поддерживаемой версии Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ffb02-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

