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
description: Сводка. Узнайте, как указать хранение данных о QoE в Skype для бизнеса Server.
ms.openlocfilehash: 18776e9b8eec9dcff6ced9f654d8153d7fa01777
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827799"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Изменение параметров качества работы в Skype для бизнеса Server

**Сводка:** Узнайте, как указать хранение данных о QoE в Skype для бизнеса Server.

По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.

> [!NOTE]
> Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.

Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Указание хранения данных качества работы с помощью панели управления Skype для бизнеса Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3. В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.

4. На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, щелкните **Изменить** и затем щелкните **Показать сведения**.

5. Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия** .

6. В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.

7. Щелкните **Зафиксировать**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Указание хранения данных о Windows PowerShell с помощью Windows PowerShell данных

Параметры хранения QoE можно создать с помощью Windows PowerShell и с помощью Windows PowerShell **Set-CsQoEConfiguration.** Вы можете запустить этот Windows PowerShell из оболочки управления Skype для бизнеса Server. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.

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

Дополнительные сведения см. в разделе справки по [cmdlet Set-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>См. также

[Мониторинг развертывания](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
