---
title: Создание файловой папки в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Сводка. Сведения о создании файловой папки Windows Server в рамках установки Skype для бизнеса Server. Скачайте бесплатную пробную версия Skype для бизнеса Server в Центре оценки Майкрософт по https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ссылке:'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812239"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="a6301-104">Создание файловой папки в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a6301-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="a6301-105">**Сводка:** Узнайте, как создать обойму файловой папки Windows Server в рамках установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a6301-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="a6301-106">Скачайте бесплатную пробную версия Skype для бизнеса Server в Центре оценки Майкрософт по [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) ссылке:</span><span class="sxs-lookup"><span data-stu-id="a6301-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a6301-107">Для Skype для бизнеса Server требуется файловая папка, чтобы компьютеры в топологии могли обмениваться файлами.</span><span class="sxs-lookup"><span data-stu-id="a6301-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="a6301-108">Создание файлового сервера — шаг 2 из 8 в процессе установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a6301-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="a6301-109">Шаги 1-5 можно делать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="a6301-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a6301-110">Однако шаги 6, 7 и 8 необходимо делать по порядку и после шагов 1–5, как по описано на схеме.</span><span class="sxs-lookup"><span data-stu-id="a6301-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="a6301-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a6301-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Обзорная схема](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="a6301-113">Создание базового файловой папки</span><span class="sxs-lookup"><span data-stu-id="a6301-113">Create a basic file share</span></span>

<span data-ttu-id="a6301-114">В этом разделе поется о создании базовой файловой папки Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a6301-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="a6301-115">В Skype для бизнеса Server поддерживается базовая файловая папка Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a6301-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="a6301-116">Однако он не обеспечивает высокую доступность явным образом.</span><span class="sxs-lookup"><span data-stu-id="a6301-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="a6301-117">Для среды с высоким уровнем доступности рекомендуется использовать обилие файлов распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="a6301-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="a6301-118">Дополнительные сведения о файловом сервере с высоким уровнем доступности и DFS см. в плане высокой доступности и аварийного [восстановления в Skype для бизнеса Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="a6301-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6301-119">В Windows Server 2012 R2 были сделаны серьезные прыжки в предоставлении решений для файлового доступа, похожих на SAN, с помощью платформы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a6301-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="a6301-120">По сравнению с традиционным устройством на основе SAN, решение для хранения данных Windows Server 2012 R2 может сократить затраты в два раза с минимальным влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="a6301-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="a6301-121">Дополнительные сведения о параметрах файлового пространства в Windows Server 2012 R2 см. в загружаемом документе ["Хранилище Windows Server 2012 R2".](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)</span><span class="sxs-lookup"><span data-stu-id="a6301-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="a6301-122">Просмотрите видео по созданию **файловой папки:**</span><span class="sxs-lookup"><span data-stu-id="a6301-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="a6301-123">Создание базового файловой папки</span><span class="sxs-lookup"><span data-stu-id="a6301-123">Create a basic file share</span></span>

1. <span data-ttu-id="a6301-124">Войдите на компьютер, на который будет работать файловая папка.</span><span class="sxs-lookup"><span data-stu-id="a6301-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="a6301-125">Щелкните правой кнопкой мыши папку, к которая планируется поделиться, и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="a6301-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="a6301-126">Выберите **вкладку "Общий** доступ" и нажмите кнопку **"Расширенный общий доступ".**</span><span class="sxs-lookup"><span data-stu-id="a6301-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="a6301-127">Щелкните **"Поделиться этой папкой".**</span><span class="sxs-lookup"><span data-stu-id="a6301-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="a6301-128">Выберите пункт **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="a6301-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="a6301-129">Добавьте **группу** локальных администраторов сервера, на который размещена файловая папка, предоставление прав **"Разрешить: полный доступ",** "Изменение" и "Чтение" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="a6301-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="a6301-130">Нажмите **кнопку** "ОК" еще раз и заметьте сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="a6301-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="a6301-131">Нажмите **кнопку** "Готово", чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="a6301-131">Click **Done** to close the wizard.</span></span>
    
     ![Вкладка "Общий доступ" для общего доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="a6301-133">Если хранилище файлов находится в папке DFS, будет получено следующее предупреждение:</span><span class="sxs-lookup"><span data-stu-id="a6301-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="a6301-134">Предупреждение: не удается получить доступ к разрешениям для \\ <domain> \<share> ".</span><span class="sxs-lookup"><span data-stu-id="a6301-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="a6301-135">Это ожидаемо, если вы не администратор файловой сервер или это папка распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="a6301-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="a6301-136">Если разрешения на доступ уже настроены, это предупреждение можно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="a6301-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="a6301-137">Если это новая обетовка, обратитесь к документации, чтобы получить подробные сведения о настройке разрешений для совместной работы вручную.</span><span class="sxs-lookup"><span data-stu-id="a6301-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="a6301-138">Из-за невозможности доступа к разрешениям на доступ к совместной работе в папке DFS Skype для бизнеса Server не сможет явным образом настроить группы в файловом файловом файловом файле.</span><span class="sxs-lookup"><span data-stu-id="a6301-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="a6301-139">Чтобы компоненты Skype для бизнеса Server могли получать доступ к файловой папке с соответствующими разрешениями, убедитесь, что следующие группы RTC добавлены с разрешениями на чтение и изменение уровня доступа в дополнение к локальным администраторам с разрешениями "Полный доступ".</span><span class="sxs-lookup"><span data-stu-id="a6301-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="a6301-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a6301-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="a6301-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a6301-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="a6301-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a6301-142">RTCUniversalServerAdmins</span></span>
