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
description: Сводка. Узнайте, как использовать регистрацию вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816639"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте, как использовать регистрацию вызовов (CDR) в Skype для бизнеса Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
При установке Skype для бизнеса Server создается одна глобальная коллекция параметров конфигурации CDR. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры конфигурации CDR, которые используются в организации, можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью [cmdlet Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Просмотр сведений о конфигурации CDR с помощью панели управления Skype для бизнеса Server

1. In Skype for Business Server Control Panel click **Monitoring and Archiving**.
    
2. Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации CDR с помощью Windows PowerShell управления

Параметры конфигурации CDR можно просмотреть с помощью Windows PowerShell и Get-CsCdrConfiguration управления. Вы можете запустить этот Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-view-cdr-configuration-information"></a>Просмотр данных конфигурации CDR

- Чтобы просмотреть сведения обо всех параметрах конфигурации CDR, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:
    
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

Дополнительные сведения см. в разделе справки по [cmdlet Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  

