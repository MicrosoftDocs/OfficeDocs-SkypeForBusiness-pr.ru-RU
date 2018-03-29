---
title: Включение функции отслеживания качества взаимодействия в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Сводка: Узнайте, как включить качества взаимодействия (QoE) в Скайп для Business Server 2015.'
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a>Включение функции отслеживания качества взаимодействия в Skype для бизнеса Server 2015
 
**Сводка:** Включение качества взаимодействия (QoE) в Скайп для Business Server 2015.
  
Служба отслеживания качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса. Дополнительные сведения см [мониторинг](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) в документации по планированию.
  
Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.
  
> [!NOTE]
> Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга. Дополнительные сведения см [Развертывание мониторинга](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Включение службы качества взаимодействия с помощью Скайп для панели управления Business Server

1.  Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**. 
    
4. На странице **данных качества взаимодействия** выберите соответствующую коллекцию в таблице и последовательно выберите пункты **Действие** и **Включить отслеживание качества взаимодействия**.
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Включение службы качества взаимодействия с помощью командлетов Windows PowerShell

Можно включить качества взаимодействия с помощью Windows PowerShell и командлет **Set-CsQoEConfiguration** . Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-enable-qoe-for-a-single-location"></a>Включение службы качества взаимодействия для одного расположения

 Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Отключение службы качества взаимодействия для одного расположения

 Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Использование одной команды для включения службы качества взаимодействия в нескольких расположениях

 Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Дополнительные сведения см [Командлета Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>См. также

[Планирование мониторинга](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Мониторинг развертывания](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

