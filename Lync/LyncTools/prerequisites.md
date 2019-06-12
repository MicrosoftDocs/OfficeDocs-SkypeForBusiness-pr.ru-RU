---
title: Необходимые компоненты
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="a37ff-102">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="a37ff-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37ff-103">_**Тема последнего изменения:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="a37ff-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="a37ff-104">Существуют различные требования к оборудованию, программному обеспечению и конфигурации системы, которые необходимы для работы с инструментом "выгрузка и производительность" Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ff-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="a37ff-105">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="a37ff-105">Client Hardware Requirements</span></span>

<span data-ttu-id="a37ff-106">Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 для каждых пользователей 4 500 для каждого пользователя, у которого вы хотите смоделировать, вам потребуется по крайней мере один выделенный компьютер, отвечающий указанным ниже минимальным требованиям к оборудованию.</span><span class="sxs-lookup"><span data-stu-id="a37ff-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="a37ff-107">гигабитный сетевой адаптер;</span><span class="sxs-lookup"><span data-stu-id="a37ff-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="a37ff-108">8 ГБ ОЗУ</span><span class="sxs-lookup"><span data-stu-id="a37ff-108">8-GB ram</span></span>

  - <span data-ttu-id="a37ff-109">два двухъядерных процессора (ЦП)</span><span class="sxs-lookup"><span data-stu-id="a37ff-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="a37ff-110">Требования к клиентскому программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="a37ff-110">Client Software Requirements</span></span>

<span data-ttu-id="a37ff-111">Для запуска средства нагрузки и производительности Lync Server 2013 при развертывании Lync Server 2013 поддерживаются следующие операционные системы:</span><span class="sxs-lookup"><span data-stu-id="a37ff-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="a37ff-112">Операционная система Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a37ff-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="a37ff-113">Операционная система Windows Server 2008 (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="a37ff-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="a37ff-114">Клиентский компьютер должен соответствовать следующим требованиям к программному обеспечению:</span><span class="sxs-lookup"><span data-stu-id="a37ff-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="a37ff-115">На вашем компьютере должна быть установлена среда выполнения [Microsoft .NET Framework 4,5](http://go.microsoft.com/fwlink/?linkid=143212) .</span><span class="sxs-lookup"><span data-stu-id="a37ff-115">You must have the [Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="a37ff-116">В Windows Server 2008 и Windows Server 2012 функция "возможности рабочего стола" должна быть включена.</span><span class="sxs-lookup"><span data-stu-id="a37ff-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="a37ff-117">На вашем компьютере должен быть установлен [распространяемый пакет Microsoft Visual C++ 2012](http://go.microsoft.com/fwlink/?linkid=143216) (x64).</span><span class="sxs-lookup"><span data-stu-id="a37ff-117">You must have the [Microsoft Visual C++ 2012 redistributable package](http://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="a37ff-118">Полностью настроенное развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ff-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a37ff-119">Библиотеки 4,0 API единой системы обмена сообщениями (УКМА) входят в пакет установки, поэтому УКМА не требуется и не должен устанавливаться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a37ff-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="a37ff-120">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="a37ff-120">Configuration Requirements</span></span>

<span data-ttu-id="a37ff-121">Компьютеры, на которых будет работать средство нагрузки и производительности Lync Server 2013, должны быть настроены в соответствии с приведенными ниже требованиями.</span><span class="sxs-lookup"><span data-stu-id="a37ff-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="a37ff-122">Вы должны войти в систему как член группы домен или локальная группа администраторов.</span><span class="sxs-lookup"><span data-stu-id="a37ff-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="a37ff-123">Приложение Lync Server 2013 (Линкперфтул. exe) не может быть запущено на компьютере, на котором также запущены компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a37ff-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="a37ff-124">Вы должны запустить средство создания пользователей Lync Server 2013 (Усерпровисионингтул. exe) на сервере переднего плана или на сервере Standard Edition, где будут храниться учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="a37ff-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="a37ff-125">Если средство запускается несколько, каждый пользователь, для которого включена единая связь с Microsoft, должен иметь уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a37ff-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="a37ff-126">Размер файла подкачки должен быть управляемым системой или не менее 1,5, чем объем оперативной памяти в системе.</span><span class="sxs-lookup"><span data-stu-id="a37ff-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

