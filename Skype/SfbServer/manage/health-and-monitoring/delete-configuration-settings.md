---
title: Удаление существующей коллекции параметров конфигурации CDR в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Сводка: Узнайте, как для удаления параметров конфигурации CDR в Скайп для Business Server.'
ms.openlocfilehash: 470aade77fce211ba771c628b913efa4376a4a6f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218961"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Удаление существующей коллекции параметров конфигурации CDR в Скайп для Business Server
 
**Сводка:** Узнайте, как для удаления параметров конфигурации CDR в Скайп для Business Server.
  
Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.
  
Когда вы устанавливаете Скайп для Business Server, single, глобальной коллекции параметров конфигурации CDR будет создан автоматически. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Параметры, настроенные на уровне сайта, переопределяют глобальные параметры. Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.
  
Обратите внимание на то, что можно также «удалить» глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например по умолчанию очистку включена в коллекции параметров конфигурации CDR. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
Параметры конфигурации CDR можно удалить с помощью Скайп для панели управления сервера Business или командлет [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации CDR с помощью Скайп для панели управления Business Server

1. В Скайп для панели управления Business Server щелкните **мониторинг и Архивация**. 
    
2. На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, выберите первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.
    
3. Нажмите **Изменить**, затем кнопку **Удалить**.
    
4. В Скайп для диалогового окна панели управления Business Server нажмите **кнопку ОК**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации CDR с помощью командлетов Windows PowerShell

Можно удалить регистрации вызовов параметров конфигурации с помощью Windows PowerShell и командлет **Remove-CsCdrConfiguration** . Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Удаление определенной коллекции параметров конфигурации CDR

 Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации CDR, применяемых на уровне сайта

 Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Удаление всех параметров конфигурации CDR, которые отключают регистрацию вызовов

 Эта команда удаляет все параметры конфигурации CDR, которые отключают регистрацию вызовов:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Для получения дополнительных сведений см раздел справки по командлет [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>См. также

[Вручную удалить базы данных качества взаимодействия в Скайп и регистрации вызовов для Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

