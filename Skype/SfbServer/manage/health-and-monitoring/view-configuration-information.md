---
title: Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Сводка: сведения о том, как использовать запись сведений о звонке (CDR) в Skype для бизнеса Server.'
ms.openlocfilehash: 976f61ac98cb02a0cd69750a581bfa5190156ff7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991684"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как использовать запись сведений о звонке (CDR) в Skype для бизнеса Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Вы можете просматривать параметры конфигурации CDR, используемые в Организации, с помощью панели управления Skype для бизнеса Server или командлетом [Get-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Просмотр сведений о конфигурации CDR с помощью панели управления Skype для бизнеса Server

1. На панели управления Skype для бизнеса Server нажмите кнопку **наблюдение и архивация**.
    
2. Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации CDR с помощью командлетов Windows PowerShell

Вы можете просматривать параметры конфигурации CDR с помощью Windows PowerShell и командлета Get-Кскдрконфигуратион. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.
  
### <a name="to-view-cdr-configuration-information"></a>Просмотр данных конфигурации CDR

- Чтобы просмотреть сведения о всех параметрах конфигурации CDR, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.
    
  ```PowerShell
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

Дополнительные сведения можно найти в разделе справки по командлету [Get-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

