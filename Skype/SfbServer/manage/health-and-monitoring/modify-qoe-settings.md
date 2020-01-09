---
title: Изменение параметров качества работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Сводка: сведения о том, как указать хранение данных QoE в Skype для бизнеса Server.'
ms.openlocfilehash: c597c0e5e3fbd2a8a92304ffd55d866a15c121a9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992044"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Изменение параметров качества работы в Skype для бизнеса Server

**Сводка:** Сведения о том, как указать хранение данных QoE в Skype для бизнеса Server.

По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.

> [!NOTE]
> Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.

Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Настройка хранения данных QoE с помощью панели управления Skype для бизнеса Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3. На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.

4. На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, нажмите **Изменить** и выберите **Показать сведения**.

5. Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия**.

6. В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.

7. Нажмите **Исполнить**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Указание хранения QoE с помощью командлетов Windows PowerShell

Вы можете создать параметры хранения QoE с помощью Windows PowerShell и командлета **Set-кскоеконфигуратион** . Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.

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

Дополнительные сведения можно найти в разделе справки по командлету [Set-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .

## <a name="see-also"></a>См. также

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
