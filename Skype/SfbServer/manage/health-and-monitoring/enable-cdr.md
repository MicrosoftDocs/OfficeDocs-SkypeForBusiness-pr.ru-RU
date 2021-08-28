---
title: Включить запись детализации вызовов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: Сводка. Сведения о том, как включить записи детализации вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: cc9b3d4f19a4598638093d92733a0917fca7c2c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622371"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Включить запись детализации вызовов в Skype для бизнеса Server

**Сводка:** Узнайте, как включить запись детализации вызовов (CDR) в Skype для бизнеса Server.

Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.

Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.

> [!NOTE]
> Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Включить CDR с Skype для бизнеса Server панелью управления

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой вы развернули Skype для бизнеса Server.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3. В левой панели навигации щелкните элемент **Мониторинг и архивация**, затем **Служба регистрации вызовов**.

4. На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.

    > [!NOTE]
    > По умолчанию функция CDR включена.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Включение CDR с помощью Windows PowerShell-кодов

Можно включить CDR с помощью Windows PowerShell **и комлета Set-CsCdrConfiguration.** Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". Этот процесс в Skype для бизнеса Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Включение CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Чтобы отключить CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не исключает мониторинг. Приостанавливется сбор и хранение данных CDR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия

 Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Дополнительные сведения см. в разделе справка для [cmdlet Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>См. также

[Планирование мониторинга](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Мониторинг развертывания](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)