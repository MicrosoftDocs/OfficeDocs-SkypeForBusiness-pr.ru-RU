---
title: Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: Сводка. Узнайте, как использовать запись детализации вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: 058a6538c8486c52fd47354fe4116e339c83a8b9479ec2da214c4f39d8558308
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341884"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте, как использовать запись детализации вызовов (CDR) в Skype для бизнеса Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры конфигурации CDR, использующиеся в организации, можно просмотреть с помощью панели управления Skype для бизнеса Server или [комлета Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Просмотр сведений о конфигурации CDR с помощью Skype для бизнеса Server панели управления

1. В Skype для бизнеса Server панели управления щелкните **Мониторинг и архива.**
    
2. Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации CDR с помощью Windows PowerShell-кодов

Параметры конфигурации CDR можно просматривать с помощью Windows PowerShell и Get-CsCdrConfiguration. Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". Этот процесс в Skype для бизнеса Server.
  
### <a name="to-view-cdr-configuration-information"></a>Просмотр данных конфигурации CDR

- Чтобы просмотреть сведения обо всех параметрах конфигурации CDR, введите следующую команду в командной Skype для бизнеса Server и нажмите кнопку ENTER:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Это приведет к возврату приблизительно такой информации:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
