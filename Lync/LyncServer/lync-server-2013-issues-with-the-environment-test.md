---
title: 'Lync Server 2013: проблемы с проверкой среды'
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
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="66720-102">Проблемы, связанные с проверкой среды в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66720-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66720-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="66720-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="66720-104">Анализатор соответствия рекомендациям позволяет удостовериться в том, что ваша среда Lync Server 2013 является поддерживаемой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="66720-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="66720-105">В рамках проверки доменных служб Active Directory анализатор соответствия рекомендациям делает следующее:</span><span class="sxs-lookup"><span data-stu-id="66720-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="66720-106">Проверка леса доменных служб Active Directory и подготовки схемы.</span><span class="sxs-lookup"><span data-stu-id="66720-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="66720-107">Определяет количество сайтов и доменов доменных служб Active Directory в развертывании.</span><span class="sxs-lookup"><span data-stu-id="66720-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="66720-108">Проверка уровней леса и домена.</span><span class="sxs-lookup"><span data-stu-id="66720-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="66720-109">Проверяет версию контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="66720-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="66720-110">Определяет контекст именования домена, конфигурации и схемы.</span><span class="sxs-lookup"><span data-stu-id="66720-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="66720-111">Определяет количество включенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="66720-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="66720-112">Проверка хранения глобальных параметров доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="66720-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="66720-113">Проверка точек соединения службы (Скпс) для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66720-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="66720-114">Определяет версию базы данных.</span><span class="sxs-lookup"><span data-stu-id="66720-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="66720-115">Устранение проблем с окружающей средой</span><span class="sxs-lookup"><span data-stu-id="66720-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="66720-116">Если при тестировании среды обнаружены проблемы с вашей средой, это может быть вызвано проблемами с конфигурацией Active Directory или уровнем программного обеспечения, запущенного на определенных серверах.</span><span class="sxs-lookup"><span data-stu-id="66720-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="66720-117">Например, если анализатор соответствия рекомендациям определяет контроллеры домена в среде под управлением Windows Server 2000, он выдаст предупреждение, и вам потребуется обновить эти контроллеры домена до поддерживаемой версии Windows Server.</span><span class="sxs-lookup"><span data-stu-id="66720-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

