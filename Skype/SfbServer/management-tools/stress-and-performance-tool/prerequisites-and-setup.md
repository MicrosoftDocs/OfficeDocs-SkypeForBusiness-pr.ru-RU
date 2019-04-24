---
title: Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Требования и необходимые компоненты для средства Stress and Performance Skype для бизнеса Server 2015. Установка и настройка средства Stress and Performance.
ms.openlocfilehash: 840891a7a356866755e89a7ef63e23fb62bfa12f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197999"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="065b5-104">Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="065b5-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="065b5-p102">Требования и необходимые компоненты для средства Stress and Performance Skype для бизнеса Server 2015. Установка и настройка средства Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="065b5-p102">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool. How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="065b5-107">Прежде чем запускать средство Stress and Performance, ознакомьтесь со следующими разделами, содержащими требования к конфигурации оборудования, программного обеспечения и системы:</span><span class="sxs-lookup"><span data-stu-id="065b5-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="065b5-108">требования к оборудованию клиента;</span><span class="sxs-lookup"><span data-stu-id="065b5-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="065b5-109">требования к программному обеспечению клиента;</span><span class="sxs-lookup"><span data-stu-id="065b5-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="065b5-110">требования к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="065b5-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="065b5-111">Также ознакомьтесь с разделом [Установка средства Stress and Performance Skype для бизнеса Server 2015](prerequisites-and-setup.md#Installing).</span><span class="sxs-lookup"><span data-stu-id="065b5-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="065b5-112">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="065b5-112">Client hardware requirements</span></span>
<span data-ttu-id="065b5-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="065b5-113"></span></span>

<span data-ttu-id="065b5-114">Для работы средства Stress and Performance в развертывании Skype для бизнеса Server 2015 на каждые 4500 пользователей, включаемых в тестирование, должны соблюдаться следующие минимальные требования к оборудованию:</span><span class="sxs-lookup"><span data-stu-id="065b5-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="065b5-115">гигабитный сетевой адаптер;</span><span class="sxs-lookup"><span data-stu-id="065b5-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="065b5-116">8 ГБ ОЗУ;</span><span class="sxs-lookup"><span data-stu-id="065b5-116">8 GB RAM</span></span>
    
- <span data-ttu-id="065b5-117">2 двухъядерных процессора.</span><span class="sxs-lookup"><span data-stu-id="065b5-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="065b5-118">Требования к программному обеспечению клиента</span><span class="sxs-lookup"><span data-stu-id="065b5-118">Client software requirements</span></span>
<span data-ttu-id="065b5-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="065b5-119"></span></span>

<span data-ttu-id="065b5-120">Средство Stress and Performance поддерживает следующие операционные системы:</span><span class="sxs-lookup"><span data-stu-id="065b5-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="065b5-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="065b5-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="065b5-122">Windows Server 2008 (64-разрядная).</span><span class="sxs-lookup"><span data-stu-id="065b5-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="065b5-123">Кроме того, компьютеры должны удовлетворять следующим минимальным требованиям к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="065b5-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="065b5-124">Установленная платформа Microsoft .NET 4.5 Framework.</span><span class="sxs-lookup"><span data-stu-id="065b5-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="065b5-125">Загрузить .net 4.5 Framework здесь.</span><span class="sxs-lookup"><span data-stu-id="065b5-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="065b5-126">Включенная функция возможностей рабочего стола в Windows.</span><span class="sxs-lookup"><span data-stu-id="065b5-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="065b5-127">Установленная среда Microsoft Visual C++ 2013 (x64).</span><span class="sxs-lookup"><span data-stu-id="065b5-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="065b5-128">Загрузите Visual C++ 2013 здесь</span><span class="sxs-lookup"><span data-stu-id="065b5-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="065b5-129">Успешное развертывание Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="065b5-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="065b5-130">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="065b5-130">Configuration requirements</span></span>
<span data-ttu-id="065b5-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="065b5-131"></span></span>

<span data-ttu-id="065b5-132">Для работы средства Stress and Performance необходимо выполнить следующие дополнительные настройки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="065b5-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="065b5-133">Выполните вход на сервер в качестве участника домена или группы локальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="065b5-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="065b5-134">Средство создания пользователей Skype для бизнеса Server 2015 (UserProvisioningTool.exe) нельзя устанавливать на сервер переднего плана или сервер Standard Edition, где будут размещаться учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="065b5-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="065b5-135">При многократном запуске средства создания пользователей каждому пользователю, для которого включена поддержка объединенных коммуникаций Майкрософт, должен быть назначен уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="065b5-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="065b5-136">Размер файла подкачки должен задаваться системой или должен как минимум в 1,5 раза превышать объем ОЗУ в системе компьютера.</span><span class="sxs-lookup"><span data-stu-id="065b5-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="065b5-137">Установка средства Stress and Performance Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="065b5-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="065b5-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="065b5-138"></span></span>

<span data-ttu-id="065b5-p105">Установка этого средства максимально упрощена. Запустите файл установщика Windows **CapacityPlanningTool.msi** на каждом клиентском компьютере, где планируется моделирование трафика пользователей, а также на сервере переднего плана в каждом пуле, где будут создаваться пользователи и контакты.</span><span class="sxs-lookup"><span data-stu-id="065b5-p105">Installing couldn't be simpler. You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="065b5-141">Чтобы загрузить MSI-файла, а также примеры сценариев, упомянутые в других статьях, перейдите к ссылку центра загрузки: [Скайп для Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="065b5-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

