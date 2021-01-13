---
title: Удаление параметров конфигурации качества работы в Skype для бизнеса Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: Сводка. Узнайте, как удалить параметры качества обслуживания (QoE) в Skype для бизнеса Server.
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816939"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации качества работы в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить параметры качества обслуживания в Skype для бизнеса Server.
  
Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.
  
При установке Skype для бизнеса Server создается одна глобальная коллекция параметров конфигурации QoE. Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам. Параметры, настроенные на уровне сайта имеют более высокий приоритет, чем параметры, настроенные в глобальной области. В случае удаления параметров уровня сайта качество взаимодействия на этом сайте будет управляться с использованием глобальных параметров.
  
Обратите внимание, что вы также можете "удалить" глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию в коллекции параметров конфигурации качества взаимодействия включена очистка. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации качества работы с помощью панели управления Skype для бизнеса Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.
    
4. На странице **Данные о качестве взаимодействия** щелкните требуемую политику, щелкните элементы **Изменить** и **Удалить**.
    
5. Нажмите кнопку **ОК**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации QoE с помощью Windows PowerShell

Параметры конфигурации QoE можно удалить с помощью Windows PowerShell и с помощью Windows PowerShell **Remove-CsQoEConfiguration.** Вы можете запустить этот Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с помощью удаленной службы PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации качества взаимодействия

 Эта команда удаляет параметры конфигурации качества взаимодействия, примененные к сайту Redmond:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации качества взаимодействия, примененных на уровне сайта

 Эта команда удаляет все параметры конфигурации качества взаимодействия, примененные на уровне сайта:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Удаление всех параметров конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия

 Эта команда удаляет все параметры конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Подробные сведения см. в [подстроке Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Ручная очистка баз данных регистрации вызовов и качества обслуживания в Skype для бизнеса Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

