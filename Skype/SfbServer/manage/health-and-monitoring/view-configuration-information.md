---
title: Просмотр сведений о конфигурации CDR в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Сводка: Сведения об использовании регистрации вызовов соединений (CDR) в Скайп для Business Server 2015.'
ms.openlocfilehash: cd143db6ebc0c4e284763ccf4beb9c545fa24ff5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569444"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>Просмотр сведений о конфигурации CDR в Skype для бизнеса Server 2015
 
**Сводка:** Сведения об использовании регистрации вызовов соединений (CDR) в Скайп для Business Server 2015.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
Когда вы устанавливаете Скайп для Business Server 2015, single, глобальной коллекции параметров конфигурации CDR будет создан автоматически. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Можно просмотреть параметры конфигурации CDR используется в вашей организации с помощью Скайп для панели управления Business Server или командлет [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Просмотр сведений о конфигурации CDR с помощью Скайп для панели управления Business Server

1. В Скайп для панели управления Business Server щелкните **мониторинг и Архивация**.
    
2. Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации CDR с помощью командлетов Windows PowerShell

Параметры конфигурации CDR можно просмотреть с помощью Windows PowerShell и командлет Get-CsCdrConfiguration. Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Просмотр данных конфигурации CDR

- Чтобы просмотреть сведения обо всех параметрах конфигурации CDR, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:
    
  ```
  Get-CsCdrConfiguration
  ```

    Команда возвращает примерно следующую информацию:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Для получения дополнительных сведений см раздел справки для командлета [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

