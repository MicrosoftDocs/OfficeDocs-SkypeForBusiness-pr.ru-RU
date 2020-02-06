---
title: Создание общего файлового файла в Skype для бизнеса Server
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
description: 'Сводка: сведения о том, как создать общий файл Windows Server в рамках установки Skype для бизнеса Server. Скачайте бесплатную пробную версию Skype для бизнеса Server из центра оценки Майкрософт по адресу: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 57d1bc348d1fed7a0dc8297723d41d3d90888710
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790187"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="cc2c8-104">Создание общего файлового файла в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cc2c8-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="cc2c8-105">**Сводка:** Сведения о том, как создать общий файл Windows Server в рамках установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="cc2c8-106">Загрузите бесплатную пробную версию Skype для бизнеса на сервере Microsoft Evaluation Center по адресу[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="cc2c8-107">В Skype для бизнеса Server требуется файловый общий доступ, чтобы компьютеры в рамках топологии могли обмениваться файлами.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="cc2c8-108">Создание общего файлового файла — шаг 2 из 8 в процессе установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="cc2c8-109">Шаги 1–5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="cc2c8-110">Однако шаги 6, 7 и 8 выполняются по порядку и после шагов 1–5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="cc2c8-111">Сведения о планировании общего доступа к файлам можно найти в статьях [требования к окружающей среде для сервера Skype для бизнеса Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) или [сервера в Skype для бизнеса Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc2c8-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Обзорная схема](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="cc2c8-113">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="cc2c8-113">Create a basic file share</span></span>

<span data-ttu-id="cc2c8-114">В этом разделе приведены пошаговые инструкции по созданию базового общего файлового ресурса Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="cc2c8-115">В Skype для бизнеса Server поддерживается простая общедоступная файловая система Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="cc2c8-116">Однако он не обеспечивает явное предоставление высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="cc2c8-117">Для среды с высокой доступностью рекомендуется общий файловый ресурс распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="cc2c8-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="cc2c8-118">Дополнительные сведения о совместном доступе к файлам высокой доступности и DFS можно найти [в разделе Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="cc2c8-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc2c8-119">В Windows Server 2012 R2 значительно усовершенствованы общие файловые ресурсы на платформе Windows Server, сходные с сетями хранения данных.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="cc2c8-120">По сравнению с традиционном устройством на основе сети хранения данных, система хранения данных в Windows Server 2012 R2 обеспечивает двукратное сокращение затрат при незначительном снижении производительности.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="cc2c8-121">Дополнительные сведения о параметрах общего доступа к файлам в Windows Server 2012 R2 можно найти в техническом описании [Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)для загружаемого документа.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="cc2c8-122">Посмотрите видео с инструкциями по **созданию общего файлового ресурса**:</span><span class="sxs-lookup"><span data-stu-id="cc2c8-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="cc2c8-123">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="cc2c8-123">Create a basic file share</span></span>

1. <span data-ttu-id="cc2c8-124">Войдите в систему на компьютере, где будет размещен общий файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="cc2c8-125">Щелкните правой кнопкой мыши на папке, к которой планируется предоставить общий доступ, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="cc2c8-126">Перейдите на вкладку **Общий доступ** и щелкните **Расширенная настройка общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="cc2c8-127">Щелкните **Общий доступ к папке**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="cc2c8-128">Щелкните **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="cc2c8-129">На сервере, где размещен общий файловый ресурс, добавьте группу **Администраторы**, предоставьте ей права **Разрешить: полный доступ, изменение и чтение**, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="cc2c8-130">Снова нажмите кнопку **ОК** и обратите внимание на сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="cc2c8-131">Чтобы закрыть мастер, щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-131">Click **Done** to close the wizard.</span></span>
    
     ![Вкладка общего доступа для предоставления доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="cc2c8-133">Если хранилище файлов размещено в общей папке DFS, будет получено следующее предупреждение:</span><span class="sxs-lookup"><span data-stu-id="cc2c8-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="cc2c8-134">Предупреждение: не удается получить доступ к разрешениям общего доступа для "\\<domain>\<общий доступ>".</span><span class="sxs-lookup"><span data-stu-id="cc2c8-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="cc2c8-135">Это может происходить, если вы не являетесь администратором на файловом сервере или общим доступом к распределенной файловой системе (DFS).</span><span class="sxs-lookup"><span data-stu-id="cc2c8-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="cc2c8-136">Если разрешения для общего доступа уже настроены, это предупреждение можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="cc2c8-137">Если это новый общий доступ, ознакомьтесь с документацией, чтобы получить подробные сведения о настройке разрешений для общего доступа вручную.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="cc2c8-138">Из-за невозможности получить доступ к разрешениям общего доступа в общей папке DFS, сервер Skype для бизнеса не сможет явно задать группы в общей папке.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="cc2c8-139">Чтобы убедиться, что компоненты сервера Skype для бизнеса могут получить доступ к общей папке с необходимыми разрешениями, убедитесь в том, что указанные ниже группы часов добавлены с разрешениями на чтение и изменение разрешений на доступ к общим ресурсам в дополнение к локальным администраторам с полным доступом. правами.</span><span class="sxs-lookup"><span data-stu-id="cc2c8-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="cc2c8-140">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="cc2c8-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="cc2c8-141">ртккомпонентуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="cc2c8-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="cc2c8-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc2c8-142">RTCUniversalServerAdmins</span></span>
