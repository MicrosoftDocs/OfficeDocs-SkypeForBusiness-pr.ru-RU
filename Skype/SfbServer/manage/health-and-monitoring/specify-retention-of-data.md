---
title: Укажите хранение данных CDR в Skype для бизнеса Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: Сводка. Сведения об управлении данными записи детализации вызовов (CDR) для Skype для бизнеса Server.
ms.openlocfilehash: 8588447d7e12123c0d10ae15b07a7727d94c0f27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013763"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Укажите хранение данных CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять данными записи детализации вызовов (CDR) для Skype для бизнеса Server.
  
По умолчанию данные регистрации вызовов (CDR) удаляются по прошествии 60 дней. Можно использовать параметры на странице **Регистрация вызовов**, чтобы задать хранение данных в течение большего или меньшего времени. Если отключить CDR, то данные, которые были записаны до включения CDR, также будут удаляться.
  
> [!NOTE]
> Необходимо настроить CDR и качество взаимодействия (QoE) для хранения данных в течении одинакового числа дней. Каждый звонок в отчетах CDR, доступных на веб-странице отчетов сервера мониторинга, включает сведения CDR и качества взаимодействия. Если время для удаления данных CDR и качества взаимодействия отличается, некоторые звонки могут содержать только данные CDR, а другие могут содержать только данные качества взаимодействия. 
  
Для настройки параметров очистки данных CDR используется следующая процедура. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Настройка хранения данных CDR

1. С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.  
    
3. В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.
    
4. На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.
    
5. Чтобы включить удаление, выберите параметр **Enable Purging of CDRs** (Включить очистку CDR).
    
6. В параметре **Keep call detail recordings CDRs for maximum duration (days):** (Сохранять CDR не более (дней)) выберите максимальное число дней, в течение которых должны храниться данные регистрации вызовов.
    
7. В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.
    
8. Нажмите кнопку **Зафиксировать**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Указание хранения CDR с помощью Windows PowerShell-кодов

Параметры хранения CDR можно создать с помощью Windows PowerShell и командлета Set-CsCdrConfiguration. Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в материале [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) В Skype для бизнеса Server этот процесс является одинаковым.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Задание параметров хранения CDR для конкретного расположения

- Эта команда позволяет очищать данные CDR для сайта Redmond и настраивает сайт для обслуживания данных CDR и данных отчетов об ошибках в течение 20 дней.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Задание параметров хранения CDR для нескольких расположений

- Эта команда настраивает параметры хранения CDR для всех параметров конфигурации CDR, используемых в организации.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Дополнительные сведения см. в разделе справка для [cmdlet Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Запись детализации вызовов (CDR) в Skype для бизнеса Server](call-detail-recording-cdr.md)