---
title: Установка необходимых условий для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Сводка. Сведения о серверах и ролях сервера, которые необходимо настроить перед установкой Skype для бизнеса Server. Скачайте бесплатную пробную Skype для бизнеса Server из Центра оценки Майкрософт по ссылке: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 8b646ea95b13454d1b025cfbfdae186c927859e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751158"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Установка необходимых условий для Skype для бизнеса Server
 
**Сводка:** Узнайте о роли серверов и серверов, которые необходимо настроить перед установкой Skype для бизнеса Server. Скачайте бесплатную пробную Skype для бизнеса Server из [Центра оценки Майкрософт.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Установка необходимых условий состоит в настройке Windows Server путем установки необходимых ролей и функций на каждом из серверов топологии. Требования основаны на роли, которую будет выполнять сервер в топологии. Вы можете сделать шаги от 1 до 5 в любом порядке. Однако необходимо сделать шаги 6, 7 и 8 в порядке и после шагов 1-5, как описано на схеме. Установка необходимых условий — шаг 1 из 8.
  
![Схема обзора — установка необходимых условий.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Настройка Windows Server

Skype для бизнеса Server для установки Windows Server и ряд необходимых условий. Сведения о планировании необходимых условий см. в материале [Server requirements for Skype для бизнеса Server.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> Эта процедура использует Windows Server 2012 R2. Если вы используете другую версию Windows Server, процедура может немного отличаться. 
  
> [!IMPORTANT]
> Перед началом работы убедитесь, что Windows Server обновлен с помощью Windows Update. 
  
![Windows Сервер в курсе.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Просмотрите видео действия по **установке необходимых условий:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Установка необходимых ролей и функций для серверов переднего плана

Необходимые роли и функции можно установить с помощью Server Manager. 
    
1. Установите необходимые функции программного обеспечения, указанные в [требованиях к серверу для Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md). Необходимое программное обеспечение должно быть на сервере, который будет работать Skype для бизнеса Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 не устанавливает все исходные файлы для необходимых функций по умолчанию. Если сервер не подключен к Интернету, необходимо вставить Windows Server 2012 R2 и  выбрать альтернативный исходный путь, чтобы установить необходимые функции. Исходные файлы находятся в каталоге sources\sxs. Например, если носите Windows Server 2012 R2 находится в диске D, вы установите путь `d:\sources\sxs` к . Важно, чтобы у вас были последние обновления из Windows Update. Если вы не подключены к Интернету, вам потребуется вручную установить все соответствующие обновления, а также все необходимые условия для необходимых обновлений. 
  
1. Когда диалоговое окно указывает, что установка завершена, для завершения процесса потребуется перезагрузать сервер.
    
1. Запустите **Windows обновление,** чтобы проверить, есть ли какие-либо обновления ролей и служб, которые были установлены.
    
1. Если вы будете использовать панель Skype для бизнеса Server на этом сервере, необходимо также установить Silverlight. Чтобы установить Silverlight, см. [в веб-сайте Microsoft Silverlight.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> Необходимые условия для серверов, исполняющих роли, не относяющиеся к серверу переднего плана, такие как роль Director, Persistent Chat или Edge, имеют свои собственные предпосылки. Дополнительные сведения о точных требованиях, необходимых для каждого типа сервера, см. в материале [Server requirements for Skype для бизнеса Server.](../../../SfBServer2019/plan/system-requirements.md) 
  

