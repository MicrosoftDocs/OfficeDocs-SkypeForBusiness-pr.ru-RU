---
title: Необходимые компоненты
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4f10cb1bdf5733dbe54519325475871be10564
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="546b5-102">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="546b5-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="546b5-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="546b5-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="546b5-104">Существуют различные требования к оборудованию, программному обеспечению и конфигурации системы, которые необходимы для запуска средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="546b5-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="546b5-105">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="546b5-105">Client Hardware Requirements</span></span>

<span data-ttu-id="546b5-106">Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 на каждые 4 500 пользователей, для которых требуется имитировать нагрузку, необходим по крайней мере один выделенный компьютер, отвечающий следующим минимальным требованиям к оборудованию:</span><span class="sxs-lookup"><span data-stu-id="546b5-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="546b5-107">1 гигабитный сетевой адаптер</span><span class="sxs-lookup"><span data-stu-id="546b5-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="546b5-108">8 ГБ ОЗУ</span><span class="sxs-lookup"><span data-stu-id="546b5-108">8-GB ram</span></span>

  - <span data-ttu-id="546b5-109">2 центральных процессора с двумя ядрами</span><span class="sxs-lookup"><span data-stu-id="546b5-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="546b5-110">Требования к клиентскому программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="546b5-110">Client Software Requirements</span></span>

<span data-ttu-id="546b5-111">Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 Поддерживаемые операционные системы:</span><span class="sxs-lookup"><span data-stu-id="546b5-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="546b5-112">Операционная система Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="546b5-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="546b5-113">Операционная система Windows Server 2008 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="546b5-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="546b5-114">Ваш клиентский компьютер должен отвечать следующим требованиям к программному обеспечению:</span><span class="sxs-lookup"><span data-stu-id="546b5-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="546b5-115">Необходимо установить среду выполнения [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) .</span><span class="sxs-lookup"><span data-stu-id="546b5-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="546b5-116">В Windows Server 2008/Windows Server 2012 компонент "возможности рабочего стола" должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="546b5-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="546b5-117">Необходимо установить [распространяемый пакет Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64).</span><span class="sxs-lookup"><span data-stu-id="546b5-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="546b5-118">Полностью настроенное развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="546b5-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="546b5-119">Библиотеки Microsoft Unified Communications Managed API (UCMA) 4,0 включены в пакет установки, поэтому UCMA не требуется и не должен устанавливаться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="546b5-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="546b5-120">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="546b5-120">Configuration Requirements</span></span>

<span data-ttu-id="546b5-121">Компьютеры, на которых будет работать средство нагрузки и производительности Lync Server 2013, должны быть настроены в соответствии со следующими требованиями:</span><span class="sxs-lookup"><span data-stu-id="546b5-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="546b5-122">Необходимо войти в систему с учетной записью члена группы "домен" или "Локальные администраторы".</span><span class="sxs-lookup"><span data-stu-id="546b5-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="546b5-123">Средство нагрузки и производительности Lync Server 2013 (Линкперфтул. exe) невозможно запустить на компьютере, на котором также установлены компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="546b5-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="546b5-124">На сервере переднего плана или сервере Standard Edition, на котором будут храниться учетные записи пользователей, необходимо запустить средство создания пользователей Lync Server 2013 (Усерпровисионингтул. exe).</span><span class="sxs-lookup"><span data-stu-id="546b5-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="546b5-125">При запуске средства несколько раз у каждого пользователя, для которого включена поддержка единой системы обмена сообщениями Майкрософт, должен быть уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="546b5-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="546b5-126">Размер файла подкачки должен быть управляемым системой или должен быть как минимум в 1,5 раз больше объема оперативной памяти в системе.</span><span class="sxs-lookup"><span data-stu-id="546b5-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

