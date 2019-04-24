---
title: Удаление параметров конфигурации качества взаимодействия в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Сводка: Узнайте, как удалить параметры качества взаимодействия (QoE) в Скайп для Business Server.'
ms.openlocfilehash: 1324029be12816abcc6c70de34363043df78277a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197718"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации качества взаимодействия в Скайп для Business Server
 
**Сводка:** Узнайте, как удалить параметры качества взаимодействия (QoE) в Скайп для Business Server.
  
Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.
  
Когда вы устанавливаете Скайп для Business Server, single, глобальной коллекции параметров конфигурации качества взаимодействия будет создан автоматически. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Параметрам, заданным на уровне сайта, назначен более высокий приоритет, чем параметрам, заданным на глобальном уровне. Если параметры уровня сайта удалены, управление качеством взаимодействия на этом сайте осуществляется на основе глобальных параметров.
  
Обратите внимание на то, что можно также «удалить» глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию в коллекции параметров конфигурации качества взаимодействия включена очистка. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
Можно удалить параметры конфигурации качества взаимодействия с помощью Скайп для панели управления Business Server или с помощью командлета [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации качества взаимодействия с помощью Скайп для панели управления Business Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.
    
4. На странице **Данные о качестве взаимодействия** щелкните требуемую политику и выберите **Изменить**, затем **Удалить**.
    
5. Нажмите **ОК**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации качества взаимодействия с помощью командлетов Windows PowerShell

Можно удалить параметры конфигурации качества взаимодействия с помощью Windows PowerShell и командлет **Remove-CsQoEConfiguration** . Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации качества взаимодействия

 Эта команда удаляет параметры конфигурации качества взаимодействия, примененные к сайту Redmond:
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации качества взаимодействия, примененных на уровне сайта

 Эта команда удаляет все параметры конфигурации качества взаимодействия, примененные на уровне сайта:
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Удаление всех параметров конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия

 Эта команда удаляет все параметры конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия:
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Дополнительные сведения см [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>См. также

[Вручную удалить базы данных качества взаимодействия в Скайп и регистрации вызовов для Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

