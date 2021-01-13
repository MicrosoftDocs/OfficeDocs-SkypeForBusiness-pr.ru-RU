---
title: Подготовка схемы
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы подготовить схему для доменных служб Active Directory, запустите этап подготовки схемы в мастере развертывания Skype для бизнеса Server. Нажмите кнопку Выполнить, чтобы начать подготовку схемы.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833779"
---
# <a name="prepare-schema"></a>Подготовка схемы
 
Чтобы подготовить схему для доменных служб Active Directory, запустите этап подготовки схемы в мастере развертывания Skype для бизнеса Server. Нажмите кнопку **Выполнить**, чтобы начать подготовку схемы. The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on. Эти файлы имеются также на установочном носителе в каталоге \Support\Schema. Шаг "Подготовка схемы" осуществляет расширение схемы и сообщает о состоянии процесса. Вы получите уведомление, когда процесс завершится. На экране сводки можно просмотреть журналы процесса. Просмотрите журналы и убедитесь, что подготовка была успешно завершена.
  
> [!IMPORTANT]
> Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия. 
  
Классы и атрибуты добавляются для расширения схемы доменных служб Active Directory для поддержки серверов, служб и пользовательских объектов Skype для бизнеса Server. Перед расширением схемы создайте резервную копию состояния системы контроллера домена, содержащего роль хозяина схемы. 
  
> [!CAUTION]
> Расширение схемы необратимо. Вы должны постараться максимально ограничить возможные последствия неудачного расширения схемы и приложить все усилия, чтобы это расширение было успешным. В частности, это критично при потере соединения или любом другом сбое сервера. Необходимо выполнить резервное копирование контроллера домена хозяина схемы и полную резервную копию Active Directory. 
  
Чтобы выполнить резервное копирование контроллера домена хозяина схемы и полную резервную копию Active Directory:
  
1. Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.
    
2. Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.
    
3. Выполните расширение схемы.
    
4. Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.
    
5. В маловероятном случае сбоя расширения схемы восстановите состояние систем контроллера домена и Active Directory с помощью резервной копии состояния системы, которую вы использовали ранее.
    
> [!NOTE]
> If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step. Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

