---
title: Предварительные требования и настройка для средства работы с нагрузкой и производительностью Skype для stress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Требования или необходимые компоненты для средства нагрузки и производительности Skype для бизнеса Server 2015. Установка или Настройка средства нагрузки и производительности.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005984"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="38b8a-104">Предварительные требования и настройка для средства работы с нагрузкой и производительностью Skype для stress</span><span class="sxs-lookup"><span data-stu-id="38b8a-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="38b8a-105">Требования или необходимые компоненты для средства нагрузки и производительности Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38b8a-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="38b8a-106">Установка или Настройка средства нагрузки и производительности.</span><span class="sxs-lookup"><span data-stu-id="38b8a-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="38b8a-107">Ниже приведены требования к оборудованию, программному обеспечению и настройке системы, которые необходимо знать перед запуском средства нагрузки и производительности:</span><span class="sxs-lookup"><span data-stu-id="38b8a-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="38b8a-108">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="38b8a-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="38b8a-109">Требования к клиентскому программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="38b8a-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="38b8a-110">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="38b8a-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="38b8a-111">Кроме того, у нас также есть раздел, посвященный [установке средства нагрузочного тестирования и производительности Skype для бизнеса Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="38b8a-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="38b8a-112">Требования к оборудованию клиента</span><span class="sxs-lookup"><span data-stu-id="38b8a-112">Client hardware requirements</span></span>
<span data-ttu-id="38b8a-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="38b8a-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="38b8a-114">При использовании средства "Нагрузочное обеспечение и производительность" для развертывания Skype для бизнеса Server 2015 вы, как минимум, должны быть выполнены следующие требования к оборудованию для каждых 4500 пользователей в тесте:</span><span class="sxs-lookup"><span data-stu-id="38b8a-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="38b8a-115">1 гигабитный сетевой адаптер</span><span class="sxs-lookup"><span data-stu-id="38b8a-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="38b8a-116">ОЗУ 8 ГБ</span><span class="sxs-lookup"><span data-stu-id="38b8a-116">8 GB RAM</span></span>
    
- <span data-ttu-id="38b8a-117">2 двухъядерных процессора</span><span class="sxs-lookup"><span data-stu-id="38b8a-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="38b8a-118">Требования к клиентскому программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="38b8a-118">Client software requirements</span></span>
<span data-ttu-id="38b8a-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="38b8a-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="38b8a-120">Ниже перечислены операционные системы, поддерживаемые средством нагрузки и производительности.</span><span class="sxs-lookup"><span data-stu-id="38b8a-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="38b8a-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="38b8a-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="38b8a-122">Windows Server 2008 (64-бит)</span><span class="sxs-lookup"><span data-stu-id="38b8a-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="38b8a-123">Кроме того, компьютер должен удовлетворять следующим требованиям к программному обеспечению:</span><span class="sxs-lookup"><span data-stu-id="38b8a-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="38b8a-124">Вам потребуется установленная платформа Microsoft .NET 4,5.</span><span class="sxs-lookup"><span data-stu-id="38b8a-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="38b8a-125">Скачайте платформу .NET 4,5 Framework.</span><span class="sxs-lookup"><span data-stu-id="38b8a-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="38b8a-126">Вам потребуются возможности рабочего стола, включенные в Windows.</span><span class="sxs-lookup"><span data-stu-id="38b8a-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="38b8a-127">Вам потребуется установить Microsoft Visual C++ 2013 (x64).</span><span class="sxs-lookup"><span data-stu-id="38b8a-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="38b8a-128">Загрузите Visual C++ 2013 здесь</span><span class="sxs-lookup"><span data-stu-id="38b8a-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="38b8a-129">Вам потребуется успешно развернуть Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="38b8a-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="38b8a-130">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="38b8a-130">Configuration requirements</span></span>
<span data-ttu-id="38b8a-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="38b8a-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="38b8a-132">Для успешного запуска средства "нагрузочное тестирование и производительность" потребуется выполнить следующие дополнительные настройки:</span><span class="sxs-lookup"><span data-stu-id="38b8a-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="38b8a-133">Необходимо выполнить вход на сервер в качестве члена группы домена или локального администратора.</span><span class="sxs-lookup"><span data-stu-id="38b8a-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="38b8a-134">Вы не можете установить средство создания пользователей Skype для бизнеса Server 2015 (Усерпровисионингтул. exe) на любом сервере переднего плана или сервере Standard Edition, на котором будут храниться учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="38b8a-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="38b8a-135">Когда средство создания пользователей запускается несколько раз, каждому пользователю, для которого разрешено использовать единую систему обмена сообщениями Майкрософт, должен быть назначен уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="38b8a-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="38b8a-136">Размер файла подкачки должен быть управляемым системой, или в ином случае должен быть по крайней мере 1,5 раз превышать объем оперативной памяти в компьютерной системе.</span><span class="sxs-lookup"><span data-stu-id="38b8a-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="38b8a-137">Установка средства нагрузочного тестирования и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="38b8a-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="38b8a-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="38b8a-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="38b8a-139">Установка не может быть более простой.</span><span class="sxs-lookup"><span data-stu-id="38b8a-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="38b8a-140">Необходимо запустить файл установщика Windows ( **капаЦитипланнингтул. msi**) на каждом клиентском компьютере, который планируется использовать для имитации трафика пользователя, а также на сервере переднего плана в каждом пуле, где будут создаваться пользователи и контакты.</span><span class="sxs-lookup"><span data-stu-id="38b8a-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="38b8a-141">Чтобы скачать файл MSI, а также примеры сценариев, упомянутые в других статьях, перейдите по ссылке центр загрузки: [Skype для бизнеса Server 2015, средство нагрузочного тестирования и производительность](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="38b8a-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

