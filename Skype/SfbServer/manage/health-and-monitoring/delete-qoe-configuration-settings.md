---
title: Удаление параметров конфигурации качества обслуживания в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Сводка: сведения о том, как удалить настройки качества взаимодействия (QoE) в Skype для бизнеса Server.'
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992426"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации качества обслуживания в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как удалить настройки качества взаимодействия (QoE) в Skype для бизнеса Server.
  
Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.
  
При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации QoE. Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам. Параметрам, заданным на уровне сайта, назначен более высокий приоритет, чем параметрам, заданным на глобальном уровне. Если параметры уровня сайта удалены, управление качеством взаимодействия на этом сайте осуществляется на основе глобальных параметров.
  
Обратите внимание, что вы также можете "Удалить" глобальные параметры. Однако фактическое удаление глобальных параметров при этом не выполняется. Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию. Например, по умолчанию в коллекции параметров конфигурации качества взаимодействия включена очистка. Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку. Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию. В данном случае это означает, что очистка будет снова включена.
  
Вы можете удалить параметры конфигурации QoE с помощью панели управления сервера Skype для бизнеса или с помощью командлета [Remove-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации QoE с помощью панели управления Skype для бизнеса Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.
    
4. На странице **Данные о качестве взаимодействия** щелкните требуемую политику и выберите **Изменить**, затем **Удалить**.
    
5. Нажмите **ОК**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации QoE с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации QoE с помощью Windows PowerShell и командлета **Remove-кскоеконфигуратион** . Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.
  
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

Подробности можно найти в разделе [Remove-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>См. также

[Очистка записей и данных качества связи в Skype для бизнеса Server вручную](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

