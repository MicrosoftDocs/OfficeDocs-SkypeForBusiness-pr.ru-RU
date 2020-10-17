---
title: Предварительные условия
description: Наличия.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560105"
---
# <a name="prerequisites"></a><span data-ttu-id="cdb11-103">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="cdb11-103">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdb11-104">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="cdb11-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="cdb11-105">Существуют различные требования к оборудованию, программному обеспечению и конфигурации системы, которые необходимы для запуска средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdb11-105">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="cdb11-106">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="cdb11-106">Client Hardware Requirements</span></span>

<span data-ttu-id="cdb11-107">Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 на каждые 4 500 пользователей, для которых требуется имитировать нагрузку, необходим по крайней мере один выделенный компьютер, отвечающий следующим минимальным требованиям к оборудованию:</span><span class="sxs-lookup"><span data-stu-id="cdb11-107">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="cdb11-108">1 гигабитный сетевой адаптер</span><span class="sxs-lookup"><span data-stu-id="cdb11-108">1 gigabit network adapter</span></span>

  - <span data-ttu-id="cdb11-109">8 ГБ ОЗУ</span><span class="sxs-lookup"><span data-stu-id="cdb11-109">8-GB ram</span></span>

  - <span data-ttu-id="cdb11-110">2 центральных процессора с двумя ядрами</span><span class="sxs-lookup"><span data-stu-id="cdb11-110">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="cdb11-111">Требования к клиентскому программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="cdb11-111">Client Software Requirements</span></span>

<span data-ttu-id="cdb11-112">Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 Поддерживаемые операционные системы:</span><span class="sxs-lookup"><span data-stu-id="cdb11-112">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="cdb11-113">Операционная система Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cdb11-113">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="cdb11-114">Операционная система Windows Server 2008 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="cdb11-114">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="cdb11-115">Ваш клиентский компьютер должен отвечать следующим требованиям к программному обеспечению:</span><span class="sxs-lookup"><span data-stu-id="cdb11-115">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="cdb11-116">Необходимо установить среду выполнения [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) .</span><span class="sxs-lookup"><span data-stu-id="cdb11-116">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="cdb11-117">В Windows Server 2008/Windows Server 2012 компонент "возможности рабочего стола" должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="cdb11-117">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="cdb11-118">Необходимо установить [распространяемый пакет Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64).</span><span class="sxs-lookup"><span data-stu-id="cdb11-118">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="cdb11-119">Полностью настроенное развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdb11-119">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cdb11-120">Библиотеки Microsoft Unified Communications Managed API (UCMA) 4,0 включены в пакет установки, поэтому UCMA не требуется и не должен устанавливаться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cdb11-120">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="cdb11-121">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="cdb11-121">Configuration Requirements</span></span>

<span data-ttu-id="cdb11-122">Компьютеры, на которых будет работать средство нагрузки и производительности Lync Server 2013, должны быть настроены в соответствии со следующими требованиями:</span><span class="sxs-lookup"><span data-stu-id="cdb11-122">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="cdb11-123">Необходимо войти в систему с учетной записью члена группы "домен" или "Локальные администраторы".</span><span class="sxs-lookup"><span data-stu-id="cdb11-123">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="cdb11-124">Средство нагрузочного тестирования и производительности Lync Server 2013 (LyncPerfTool.exe) не может выполняться на компьютере, на котором также установлены компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdb11-124">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="cdb11-125">На сервере переднего плана или сервере Standard Edition, на котором будут храниться учетные записи пользователей, необходимо запустить средство создания пользователей Lync Server 2013 (UserProvisioningTool.exe).</span><span class="sxs-lookup"><span data-stu-id="cdb11-125">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="cdb11-126">При запуске средства несколько раз у каждого пользователя, для которого включена поддержка единой системы обмена сообщениями Майкрософт, должен быть уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="cdb11-126">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="cdb11-127">Размер файла подкачки должен быть управляемым системой или должен быть как минимум в 1,5 раз больше объема оперативной памяти в системе.</span><span class="sxs-lookup"><span data-stu-id="cdb11-127">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

