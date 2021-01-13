---
title: Подготовка текущего домена
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete Step 5: Prepare Current Domain, as described in the topic Using Setup to Run Domain Preparation. Для выполнения этого шага необходимо войти в систему как участник группы администраторов домена в подготавливаемом домене или как участник группы администраторов предприятия леса, к которой принадлежит домен. Чтобы подготовить домен:'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804969"
---
# <a name="prepare-current-domain"></a>Подготовка текущего домена

Чтобы подготовить домен для серверов, на которые работают пользователи Skype для бизнеса Server 2015 или Skype для бизнеса [](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)Server, необходимо выполнить шаг **5.** Подготовка текущего домена, как описано в разделе "Использование программы установки для выполнения подготовки домена". Для выполнения этого шага необходимо войти в систему как участник группы администраторов домена в подготавливаемом домене или как участник группы администраторов предприятия леса, к которой принадлежит домен. Чтобы подготовить домен:

1. В папке или на носите для установки Skype для бизнеса Server 2015 запустите Setup.exe, чтобы запустить мастер развертывания Skype для бизнеса Server.

2. Щелкните **Подготовить Active Directory** и дождитесь, когда определится состояние развертывания.

3. На странице **Шаг 5. Подготовить текущий домен** нажмите кнопку **Выполнить**.

4. На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотреть журнал**.

5. В столбце **"Действие"** разйдите "Подготовка домена" **и** найдите результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка домена успешно завершена, закроем журнал и нажмите кнопку **\<Success\>** **"Готово".**

> [!TIP]
> If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step. Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp.


