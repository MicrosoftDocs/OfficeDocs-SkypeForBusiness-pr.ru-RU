---
title: Создание общего файлового ресурса в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Сводка. сведения о том, как создать файловый ресурс Windows Server в рамках установки Skype для бизнеса Server. Скачайте бесплатную пробную версию Skype для бизнеса Server в центре оценки Майкрософт по адресу https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028300"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="e01f6-104">Создание общего файлового ресурса в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e01f6-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="e01f6-105">**Сводка:** Узнайте, как создать файловый ресурс Windows Server в рамках установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e01f6-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="e01f6-106">Скачайте бесплатную пробную версию Skype для бизнеса Server в центре оценки Майкрософт по адресу[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="e01f6-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="e01f6-107">В Skype для бизнеса Server требуется файловый ресурс, чтобы компьютеры в пределах топологии могли обмениваться файлами.</span><span class="sxs-lookup"><span data-stu-id="e01f6-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="e01f6-108">Создание общей папки — шаг 2 из 8 в процессе установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e01f6-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="e01f6-109">Шаги с 1 по 5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="e01f6-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="e01f6-110">Однако шаги 6, 7 и 8 необходимо выполнять по порядку и после шагов 1 – 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="e01f6-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="e01f6-111">Сведения о планировании общего файлового ресурса приведены в статье [требования к окружающей среде для Skype для бизнеса Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) или [серверных требований Skype для бизнеса Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e01f6-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Обзорная схема](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="e01f6-113">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="e01f6-113">Create a basic file share</span></span>

<span data-ttu-id="e01f6-114">В этом разделе рассказывается, как создать базовую общую папку Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e01f6-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="e01f6-115">Базовый файловый ресурс Windows Server поддерживается в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e01f6-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="e01f6-116">Однако он явно не обеспечивает высокую доступность.</span><span class="sxs-lookup"><span data-stu-id="e01f6-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="e01f6-117">Для среды с высокой доступностью рекомендуется использовать общий файловый ресурс распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="e01f6-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="e01f6-118">Для получения дополнительных сведений о файловом ресурсе высокой доступности и распределенной файловой системе DFS ознакомьтесь со статьей [Планирование обеспечения высокой доступности и аварийного восстановления в Skype для бизнеса Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e01f6-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e01f6-119">В Windows Server 2012 R2 сделаны основные LEAP-решения для обеспечения общего доступа к файлам в сети хранения данных (SAN) с помощью платформы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e01f6-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="e01f6-120">По сравнению с традиционным устройством на основе SAN, решение для хранения данных Windows Server 2012 R2 может снизить затраты в половину с минимальным влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="e01f6-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="e01f6-121">Дополнительные сведения о параметрах совместного использования файлов в Windows Server 2012 R2 можно найти в техническом документе [хранения данных Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf), доступный для загрузки.</span><span class="sxs-lookup"><span data-stu-id="e01f6-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="e01f6-122">Просмотрите видео шаги для **создания общей папки**:</span><span class="sxs-lookup"><span data-stu-id="e01f6-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="e01f6-123">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="e01f6-123">Create a basic file share</span></span>

1. <span data-ttu-id="e01f6-124">Войдите на компьютер, на котором будет размещаться файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="e01f6-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="e01f6-125">Щелкните правой кнопкой мыши папку, к которой планируется предоставить общий доступ, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e01f6-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="e01f6-126">Перейдите на вкладку **Общий** доступ и нажмите **Расширенный общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="e01f6-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="e01f6-127">Щелкните **общий доступ к этой папке**.</span><span class="sxs-lookup"><span data-stu-id="e01f6-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="e01f6-128">Выберите пункт **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="e01f6-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="e01f6-129">Добавьте локальную группу **администраторов** на сервере, на котором размещается файловый ресурс, предоставьте **разрешение: полный доступ, изменение и чтение** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e01f6-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e01f6-130">Снова нажмите кнопку **ОК** и запишите сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="e01f6-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="e01f6-131">Нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="e01f6-131">Click **Done** to close the wizard.</span></span>
    
     ![Вкладка "общий доступ" для предоставления общего доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="e01f6-133">Если хранилище файлов размещается в общей папке DFS, будет получено следующее предупреждение:</span><span class="sxs-lookup"><span data-stu-id="e01f6-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="e01f6-134">Предупреждение: не удается получить доступ к разрешениям общего доступа для "\\<domain>\<Share>".</span><span class="sxs-lookup"><span data-stu-id="e01f6-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="e01f6-135">Это может происходить, если вы не являетесь администратором файлового сервера, или если это общий ресурс распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="e01f6-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="e01f6-136">Если разрешения на доступ к общему ресурсу уже настроены, это предупреждение можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="e01f6-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="e01f6-137">Если это новый общий ресурс, обратитесь к документации для получения сведений о настройке разрешений общего доступа вручную.</span><span class="sxs-lookup"><span data-stu-id="e01f6-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="e01f6-138">Из-за невозможности получить доступ к разрешениям общего доступа в общем ресурсе DFS, Skype для бизнеса Server не сможет явно задавать группы в общем файловом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="e01f6-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="e01f6-139">Чтобы убедиться, что компоненты Skype для бизнеса Server могут получить доступ к общему файловому ресурсу с соответствующими разрешениями, убедитесь, что следующие группы RTC добавляются с разрешениями на чтение и изменение разрешений на уровне, а также локальных администраторов с полным доступом к файлам. правах.</span><span class="sxs-lookup"><span data-stu-id="e01f6-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="e01f6-140">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="e01f6-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="e01f6-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e01f6-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="e01f6-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e01f6-142">RTCUniversalServerAdmins</span></span>
