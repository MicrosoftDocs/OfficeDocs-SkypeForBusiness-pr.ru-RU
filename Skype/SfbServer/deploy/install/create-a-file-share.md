---
title: Создание общего файлового ресурса в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Summary: Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: db2f92bd921acb8fc4784c6f485a74105c632d9a
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a>Создание общего файлового ресурса в Skype для бизнеса Server 2015
 
**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server requires a file share so that computers throughout the topology can exchange files. Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015. Шаги 1–5 можно выполнять в любом порядке. Однако шаги 6, 7 и 8 выполняются по порядку и после шагов 1–5, как показано на схеме. For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![Обзорная схема](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Создание базового общего файлового ресурса

В этом разделе приведены пошаговые инструкции по созданию базового общего файлового ресурса Windows Server. A basic Windows Server file share is supported with Skype for Business Server. However, it does not explicitly provide high availability. Для среды с высокой доступностью рекомендуется общий файловый ресурс распределенной файловой системы (DFS). For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> В Windows Server 2012 R2 значительно усовершенствованы общие файловые ресурсы на платформе Windows Server, сходные с сетями хранения данных. По сравнению с традиционном устройством на основе сети хранения данных, система хранения данных в Windows Server 2012 R2 обеспечивает двукратное сокращение затрат при незначительном снижении производительности. For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Посмотрите видео с инструкциями по **созданию общего файлового ресурса**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Создание базового общего файлового ресурса

1. Войдите в систему на компьютере, где будет размещен общий файловый ресурс.
    
2. Щелкните правой кнопкой мыши на папке, к которой планируется предоставить общий доступ, и выберите **Свойства**.
    
3. Перейдите на вкладку **Общий доступ** и щелкните **Расширенная настройка общего доступа**.
    
4. Щелкните **Общий доступ к папке**.
    
5. Щелкните **Разрешения**.
    
6. На сервере, где размещен общий файловый ресурс, добавьте группу **Администраторы**, предоставьте ей права **Разрешить: полный доступ, изменение и чтение**, затем нажмите **ОК**.
    
7. Снова нажмите кнопку **ОК** и обратите внимание на сетевой путь.
    
8. Чтобы закрыть мастер, щелкните **Готово**.
    
     ![Вкладка общего доступа для предоставления доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

