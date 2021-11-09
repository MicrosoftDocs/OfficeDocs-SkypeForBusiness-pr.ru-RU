---
title: Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: Сводка. Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.
ms.openlocfilehash: 8218d0b51045d3962825555bd5b248cb58262a37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854323"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры, настроенные на уровне сайта, переопределяют глобальные параметры. Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.
  
Обратите внимание, что можно также "удалить" глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию чистка включена в наборе параметров конфигурации CDR. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
Параметры конфигурации CDR можно удалить с помощью панели управления Skype для бизнеса Server или [cmdlet Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации CDR с Skype для бизнеса Server панели управления

1. В Skype для бизнеса Server панели управления нажмите **кнопку Мониторинг и архива.** 
    
2. На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, щелкните первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.
    
3. Щелкните **Изменить** и **Удалить**.
    
4. В диалоговом окне Skype для бизнеса Server панели управления нажмите **кнопку ОК**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации CDR с помощью Windows PowerShell cmdlets

Параметры конфигурации записи параметров записи вызовов можно удалить с помощью Windows PowerShell и **cmdlet Remove-CsCdrConfiguration.** Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в [материале Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Этот процесс в Skype для бизнеса Server.
  
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

[Вручную очищают базы данных данных о детализации вызовов и качестве Skype для бизнеса Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)