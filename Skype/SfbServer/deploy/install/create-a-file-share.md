---
title: Создание общего файлового ресурса в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Сводка: Сведения о создании общего файлового ресурса сервера Windows в ходе установки Скайп для Business Server 2015. Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 5f91a18a744e73cd65f58efef071978604653b27
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="a1f4a-104">Создание общего файлового ресурса в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1f4a-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a1f4a-105">**Сводка:** Сведения о создании общего файлового ресурса сервера Windows в ходе установки Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="a1f4a-106">Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a1f4a-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a1f4a-107">Скайп для Business Server требуется в общей папке, чтобы компьютеров в топологии могут обмениваться файлами.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="a1f4a-108">Создание общей папки — шаг 2 из 8 в процессе установки для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="a1f4a-109">Шаги 1–5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a1f4a-110">Однако шаги 6, 7 и 8 выполняются по порядку и после шагов 1–5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="a1f4a-111">Планирование подробные сведения об общей папке, см [окружающей среды Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f4a-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![Обзорная схема](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="a1f4a-113">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="a1f4a-113">Create a basic file share</span></span>

<span data-ttu-id="a1f4a-114">В этом разделе приведены пошаговые инструкции по созданию базового общего файлового ресурса Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="a1f4a-115">Базовая общей папке Windows Server поддерживается с Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="a1f4a-116">Тем не менее он не поддерживает явным образом высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="a1f4a-117">Для среды с высокой доступностью рекомендуется общий файловый ресурс распределенной файловой системы (DFS).</span><span class="sxs-lookup"><span data-stu-id="a1f4a-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="a1f4a-118">Дополнительные сведения о распределенной файловой системы и высокой доступности общей папки в разделе [Планирование высокой доступности и аварийного восстановления в Скайп для Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a1f4a-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1f4a-119">В Windows Server 2012 R2 значительно усовершенствованы общие файловые ресурсы на платформе Windows Server, сходные с сетями хранения данных.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="a1f4a-120">По сравнению с традиционном устройством на основе сети хранения данных, система хранения данных в Windows Server 2012 R2 обеспечивает двукратное сокращение затрат при незначительном снижении производительности.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="a1f4a-121">Дополнительные сведения о параметрах файла совместный доступ в Windows Server 2012 R2 см загружаемом техническом документе [Windows Server 2012 R2 хранилища](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="a1f4a-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="a1f4a-122">Посмотрите видео с инструкциями по **созданию общего файлового ресурса**:</span><span class="sxs-lookup"><span data-stu-id="a1f4a-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="a1f4a-123">Создание базового общего файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="a1f4a-123">Create a basic file share</span></span>

1. <span data-ttu-id="a1f4a-124">Войдите в систему на компьютере, где будет размещен общий файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="a1f4a-125">Щелкните правой кнопкой мыши на папке, к которой планируется предоставить общий доступ, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="a1f4a-126">Перейдите на вкладку **Общий доступ** и щелкните **Расширенная настройка общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="a1f4a-127">Щелкните **Общий доступ к папке**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="a1f4a-128">Щелкните **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="a1f4a-129">На сервере, где размещен общий файловый ресурс, добавьте группу **Администраторы**, предоставьте ей права **Разрешить: полный доступ, изменение и чтение**, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="a1f4a-130">Снова нажмите кнопку **ОК** и обратите внимание на сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="a1f4a-131">Чтобы закрыть мастер, щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a1f4a-131">Click **Done** to close the wizard.</span></span>
    
     ![Вкладка общего доступа для предоставления доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

