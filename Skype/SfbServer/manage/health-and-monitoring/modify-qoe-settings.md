---
title: Изменение параметров качества работы в Skype для бизнеса Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: Сводка. Узнайте, как указать хранение данных QoE в Skype для бизнеса Server.
ms.openlocfilehash: 9a060955167ce7440dabe9b88943a11775b4607760862b2cc72f468676e44966
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313207"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Изменение параметров качества работы в Skype для бизнеса Server

**Сводка:** Узнайте, как указать хранение данных QoE в Skype для бизнеса Server.

По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.

> [!NOTE]
> Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.

Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Чтобы указать хранение данных QoE с помощью Skype для бизнеса Server панели управления

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3. В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.

4. На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, щелкните **Изменить** и затем щелкните **Показать сведения**.

5. Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия** .

6. В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.

7. Щелкните **Зафиксировать**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Указание хранения QoE с помощью Windows PowerShell cmdlets

Параметры хранения QoE можно создать с помощью Windows PowerShell **и комлета Set-CsQoEConfiguration.** Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". Этот процесс в Skype для бизнеса Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Указание срока хранения данных о качестве взаимодействия для определенного расположения

- Эта команда включает очистку данных о качестве взаимодействия и настраивает их хранение в течение 20 дней для сайта Redmond.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Указание срока хранения данных о качестве взаимодействия для нескольких расположений

- Эта команда настраивает срок хранения для всех параметров конфигурации качества взаимодействия, используемых в организации.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Дополнительные сведения см. в разделе Справка для [cmdlet Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>См. также

[Мониторинг развертывания](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)