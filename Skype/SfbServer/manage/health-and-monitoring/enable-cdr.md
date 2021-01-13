---
title: Включить регистрацию вызовов в Skype для бизнеса Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: Сводка. Узнайте, как включить записи регистрации вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816889"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Включить регистрацию вызовов в Skype для бизнеса Server

**Сводка:** Узнайте, как включить записи регистрации вызовов (CDR) в Skype для бизнеса Server.

Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.

Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.

> [!NOTE]
> Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Чтобы включить CDR с помощью панели управления Skype для бизнеса Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3. В левой панели навигации щелкните элемент **Мониторинг и архивация**, затем **Служба регистрации вызовов**.

4. На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.

    > [!NOTE]
    > По умолчанию функция CDR включена.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Включение CDR с помощью Windows PowerShell управления

Включить CDR можно с помощью Windows PowerShell и с помощью Windows PowerShell **Set-CsCdrConfiguration.** Вы можете запустить этот Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.

### <a name="to-enable-cdr-for-a-single-location"></a>Включение CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Чтобы отключить CDR для отдельного места

 Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не означает, что мониторинг будет отключен. Приостанавливовка сбора и хранения данных CDR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия

 Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Дополнительные сведения см. в разделе справки по [cmdlet Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>См. также

[Планирование мониторинга](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Мониторинг развертывания](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
