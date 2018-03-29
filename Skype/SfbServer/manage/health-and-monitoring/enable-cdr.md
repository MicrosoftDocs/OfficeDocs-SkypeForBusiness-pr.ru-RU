---
title: Включение регистрации вызовов в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Сводка: Узнайте, как Включение регистрации вызовов (CDR) записей в Скайп для Business Server 2015.'
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a>Включение регистрации вызовов в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как включить регистрации вызовов (CDR) записей в Скайп для Business Server 2015.
  
Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями. 
  
Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.
  
> [!NOTE]
> Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см [Развертывание мониторинга](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Чтобы включить CDR с помощью Скайп для панели управления Business Server

1.  Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**. 
    
4. На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.
    
    > [!NOTE]
    > По умолчанию функция CDR включена. 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Включение CDR с помощью командлетов Windows PowerShell

Можно включить CDR с помощью командлета **Set-CsCdrConfiguration** и Windows PowerShell. Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-enable-cdr-for-a-single-location"></a>Включение CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Чтобы отключить CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не приводит к удалению мониторинга. Оно приостанавливает сбор и сохранение данных CDR.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия

 Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

Для получения дополнительных сведений см раздел справки для командлета [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>См. также

[Планирование мониторинга](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Мониторинг развертывания](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)