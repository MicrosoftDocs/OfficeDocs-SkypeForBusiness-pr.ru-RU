---
title: Создание доли файлов в Skype для бизнеса Server
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Сводка. Сведения о создании Windows сервера в рамках установки Skype для бизнеса Server. Скачайте бесплатную пробную Skype для бизнеса Server из Центра оценки Майкрософт по ссылке: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: b7d766a38791a7fc21b4e86844684ed174769e60
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727968"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Создание доли файлов в Skype для бизнеса Server
 
**Сводка:** Узнайте, как создать Windows сервера в рамках установки Skype для бизнеса Server. Скачайте бесплатную пробную Skype для бизнеса Server из Центра оценки Майкрософт по ссылке: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Skype для бизнеса Server требуется файл, чтобы компьютеры в топологии могли обмениваться файлами. Создание доли файлов — шаг 2 из 8 в процессе установки Skype для бизнеса Server. Вы можете сделать шаги от 1 до 5 в любом порядке. Однако необходимо сделать шаги 6, 7 и 8 в порядке и после шагов 1-5, как описано на схеме. Сведения о планировании совместной деятельности с файлами см. в Skype для бизнеса Server требования к Skype для бизнеса Server [сервера.](../../../SfBServer2019/plan/system-requirements.md) [](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
  
![Схема обзора.](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Создание базовой папки

В этом разделе вы можете создать базовую Windows сервера. Базовая Windows сервера поддерживается с помощью Skype для бизнеса Server. Однако он явно не обеспечивает высокую доступность. Для среды с высокой доступностью рекомендуется использовать файл распределенной файловой системы (DFS). Дополнительные сведения о файле с высокой доступностью и DFS см. в [разделе Plan for high availability and disaster recovery in Skype для бизнеса Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> Windows Server 2012 R2 совершила серьезные скачки в предоставлении решений служба хранилища области (SAN)like file share solutions using the Windows Server platform. По сравнению с традиционным устройством на основе SAN решение для хранения Windows Server 2012 R2 может сократить затраты в два раза с минимальным влиянием на производительность. Дополнительные сведения о параметрах обмена файлами в Windows Server 2012 R2 см. в загружаемом белом документе Windows Server 2012 [R2 служба хранилища.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf) 
  
Просмотрите действия видео для **создания файла:**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Создание базовой папки

1. Войдите на компьютер, на который будет входить файл.
    
2. Щелкните правой кнопкой мыши папку, в которая вы планируете делиться, и выберите **Свойства**.
    
3. Выберите **вкладку "Общий** доступ" и нажмите **кнопку Расширенный общий доступ**.
    
4. Нажмите **кнопку Share this folder**.
    
5. Выберите пункт **Разрешения**.
    
6. Добавьте **локализовую** группу администраторов сервера, на который размещена файлообменная часть, дайте разрешение: полный **контроль,** изменение и чтение прав, а затем нажмите **кнопку ОК**.
    
7. Нажмите **кнопку ОК** снова и обратите внимание на сетевой путь.
    
8. Нажмите **кнопку Готово,** чтобы закрыть мастера.
    
     ![Обмен вкладками для общего доступа к папке.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Если хранилище файлов находится на DFS-файле, будет получено следующее предупреждение:

Предупреждение. Не удается получить доступ к разрешениям на совместное использование для \\ <domain> \<share> ".

>Это ожидается, если вы не администратор на файловом сервере или это доля распределенной файловой системы (DFS). Если разрешения на доступ к акциям уже настроены, это предупреждение можно игнорировать. Если это новая доля, обратитесь к документации для получения сведений о ручной настройке разрешений на доступ к данным.

>Из-за невозможности получить доступ к разрешениям на доступ к совместной акции DFS Skype для бизнеса Server не смогут явно устанавливать группы в файле. Чтобы убедиться Skype для бизнеса Server компоненты могут получать доступ к файлу с соответствующими разрешениями, убедитесь, что следующие группы RTC добавляются с разрешениями на совместное чтение и изменение уровня, а также локальными администраторами с разрешениями на совместное использование полного контроля.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
