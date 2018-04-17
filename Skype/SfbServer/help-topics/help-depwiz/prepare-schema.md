---
title: Подготовка схемы
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard. Click Run to begin the preparation of the schema. The Prepare Schema step reads the supplied schema definition files in the /Program Files/Microsoft Lync Server 2013/Deployment/Setup directory on the system that the Deployment Wizard is running on. These files are also available on the installation media in the Support/Schema directory. На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса. Пользователь получает уведомление о завершении процесса. На экране сводки можно просмотреть журналы процесса. Просмотрите журналы для проверки успешного завершения подготовки.
ms.openlocfilehash: 190ee654984916e1f3417769ea65863f82566853
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-schema"></a>Подготовка схемы
 
To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard. Для запуска подготовки схемы нажмите кнопку **Выполнить**. На шаге "Подготовка схемы" считываются предоставленные файлы определений схемы из каталога \Program Files\Microsoft Lync Server 2013\Deployment\Setup в системе, где работает мастер развертывания. Эти файлы имеются также на установочном носителе в каталоге \Support\Schema. На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса. Пользователь получает уведомление о завершении процесса. На экране сводки можно просмотреть журналы процесса. Просмотрите журналы для проверки успешного завершения подготовки.
  
> [!IMPORTANT]
> Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия. 
  
Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects. Перед расширением схемы следует создать резервную копию состояния системы для контроллера домена, выполняющего роль хозяина схемы. For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> Расширение схемы необратимо. Необходимо приложить все усилия для успешного расширения схемы и ограничения возможных последствий в случае его сбоя. Это особенно важно в случае потери связи или любого другого сбоя на сервере. You should perform a backup of the schema master domain controller and a complete backup of Active Directory. 
  
To perform a backup of the schema master domain controller and a complete backup of Active Directory:
  
1. Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.
    
2. Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.
    
3. Выполните расширение схемы.
    
4. Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.
    
5. In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.
    
> [!NOTE]
> If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step. For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

