---
title: Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: Сводка. Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.
ms.openlocfilehash: 3ac961df352f26891ece9c69b7d62b37c4c015d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095313"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры, настроенные на уровне сайта, переопределяют глобальные параметры. Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.
  
Обратите внимание, что можно также "удалить" глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию чистка включена в наборе параметров конфигурации CDR. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
Параметры конфигурации CDR можно удалить с помощью панели управления Skype для бизнес-серверов или группы [remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации CDR с панели управления Skype для бизнес-серверов

1. В панели управления Skype для бизнес-серверов нажмите **кнопку Мониторинг и архива.** 
    
2. На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, щелкните первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.
    
3. Щелкните **Изменить** и **Удалить**.
    
4. В диалоговом окне Панель управления Skype для бизнес-серверов нажмите **кнопку ОК**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации CDR с помощью Windows PowerShell cmdlets

Параметры конфигурации записи детализации вызовов можно удалить с помощью Windows PowerShell и **cmdlet Remove-CsCdrConfiguration.** Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс является одинаковым.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Удаление определенной коллекции параметров конфигурации CDR

 Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации CDR, примененных к области сайта

 Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Вручную очищать записи детализации вызовов и базы данных по качеству работы в Skype для бизнеса Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)