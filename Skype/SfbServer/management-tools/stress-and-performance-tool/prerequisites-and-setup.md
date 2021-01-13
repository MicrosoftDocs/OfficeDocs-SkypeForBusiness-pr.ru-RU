---
title: Prerequisites and setup for the Skype for Busines Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Требования или необходимые условия для средства Stress and Performance Skype для бизнеса Server 2015. Установка или настройка средства Stress and Performance.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814959"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="07a5f-104">Необходимые условия и настройка средства "Нагрузка и производительность Skype для шин"</span><span class="sxs-lookup"><span data-stu-id="07a5f-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="07a5f-105">Требования или необходимые условия для средства Stress and Performance Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07a5f-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="07a5f-106">Установка или настройка средства Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="07a5f-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="07a5f-107">У нас есть следующие разделы требований к оборудованию, программному обеспечению и конфигурации системы, которые необходимо знать перед запуском средства Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="07a5f-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="07a5f-108">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="07a5f-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="07a5f-109">Требования к программному обеспечению клиента</span><span class="sxs-lookup"><span data-stu-id="07a5f-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="07a5f-110">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="07a5f-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="07a5f-111">Кроме того, ниже приведен раздел об установке средства [Stress and Performance Skype для бизнеса Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="07a5f-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="07a5f-112">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="07a5f-112">Client hardware requirements</span></span>
<span data-ttu-id="07a5f-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="07a5f-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="07a5f-114">При запуске средства Stress and Performance в развертывании Skype для бизнеса Server 2015 вам, как минимум, потребуется, чтобы эти требования к оборудованию были выполнены для каждого 4500 пользователей в тесте:</span><span class="sxs-lookup"><span data-stu-id="07a5f-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="07a5f-115">1 гигабитный сетевой адаптер</span><span class="sxs-lookup"><span data-stu-id="07a5f-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="07a5f-116">ОЗУ 8 ГБ</span><span class="sxs-lookup"><span data-stu-id="07a5f-116">8 GB RAM</span></span>
    
- <span data-ttu-id="07a5f-117">2 двухъядерных ЦП</span><span class="sxs-lookup"><span data-stu-id="07a5f-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="07a5f-118">Требования к программному обеспечению клиента</span><span class="sxs-lookup"><span data-stu-id="07a5f-118">Client software requirements</span></span>
<span data-ttu-id="07a5f-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="07a5f-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="07a5f-120">Поддерживаемые операционные системы для средства Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="07a5f-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="07a5f-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="07a5f-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="07a5f-122">Windows Server 2008 (64-битная версия)</span><span class="sxs-lookup"><span data-stu-id="07a5f-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="07a5f-123">Кроме того, компьютеры должны соответствовать следующим требованиям к программному обеспечению:</span><span class="sxs-lookup"><span data-stu-id="07a5f-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="07a5f-124">Вам потребуется установить Microsoft .NET 4.5 Framework.</span><span class="sxs-lookup"><span data-stu-id="07a5f-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="07a5f-125">Скачайте .Net 4.5 Framework здесь.</span><span class="sxs-lookup"><span data-stu-id="07a5f-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="07a5f-126">Вам потребуется включить функцию "Возможности рабочего стола" в Windows.</span><span class="sxs-lookup"><span data-stu-id="07a5f-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="07a5f-127">Вам потребуется установить Microsoft Visual C++ 2013 (x64).</span><span class="sxs-lookup"><span data-stu-id="07a5f-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="07a5f-128">Скачайте Visual C++ 2013 здесь</span><span class="sxs-lookup"><span data-stu-id="07a5f-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="07a5f-129">Вам потребуется успешное развертывание Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07a5f-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="07a5f-130">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="07a5f-130">Configuration requirements</span></span>
<span data-ttu-id="07a5f-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="07a5f-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="07a5f-132">Для успешного запуска средства Stress and Performance вам потребуется выполнить указанные дополнительные настройки.</span><span class="sxs-lookup"><span data-stu-id="07a5f-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="07a5f-133">Необходимо войти на сервер в качестве члена группы "Домен" или "Локальный администратор".</span><span class="sxs-lookup"><span data-stu-id="07a5f-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="07a5f-134">Средство создания пользователей Skype для бизнеса Server 2015 (UserProvisioningTool.exe) нельзя установить на любом сервере переднего интерфейса или сервере Standard Edition, на котором будут находиться учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="07a5f-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="07a5f-135">При многократном запуске средства создания пользователей у каждого пользователя, включенного в единую систему связи Майкрософт, должен быть уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="07a5f-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="07a5f-136">Размер файла страницы должен управляться системами или должен быть по крайней мере в 1,5 раза больше объема ОЗУ в компьютерной системе.</span><span class="sxs-lookup"><span data-stu-id="07a5f-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="07a5f-137">Установка средства stress and performance Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="07a5f-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="07a5f-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="07a5f-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="07a5f-139">Установка не может быть проще.</span><span class="sxs-lookup"><span data-stu-id="07a5f-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="07a5f-140">Необходимо запустить файл установщика Windows **CapacityPlanningTool.msi** на каждом клиентский компьютер, который будет использовать для имитации пользовательского трафика, и на сервере переднего интерфейса в каждом пуле, где будут создаваться пользователи и контакты.</span><span class="sxs-lookup"><span data-stu-id="07a5f-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="07a5f-141">Чтобы скачать MSI-файл, а также примеры сценариев, упомянутые в других статьях, перейдите по ссылке Центра загрузки: Skype для бизнеса [Server 2015, stress and Performance Tool.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="07a5f-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

