---
title: Указание срока хранения данных CDR в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Сводка: Сведения об управлении данных регистрации вызовов (CDR) для Скайп для Business Server.'
ms.openlocfilehash: ce35d8d2cac0968cca912031ec5e406ebe93e2eb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005834"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Указание срока хранения данных CDR в Скайп для Business Server
 
**Сводка:** Сведения об управлении данных регистрации вызовов (CDR) для Скайп для Business Server.
  
По умолчанию данные регистрации вызовов (CDR) удаляются по прошествии 60 дней. Можно использовать параметры на странице **Регистрация вызовов**, чтобы задать хранение данных в течение большего или меньшего времени. Если отключить CDR, то данные, которые были записаны до включения CDR, также будут удаляться.
  
> [!NOTE]
> Необходимо настроить CDR и качество взаимодействия (QoE) для хранения данных в течении одинакового числа дней. Каждый звонок в отчетах CDR, доступных на веб-странице отчетов сервера мониторинга, включает сведения CDR и качества взаимодействия. Если время для удаления данных CDR и качества взаимодействия отличается, некоторые звонки могут содержать только данные CDR, а другие могут содержать только данные качества взаимодействия. 
  
Для настройки параметров очистки данных CDR используется следующая процедура. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Настройка хранения данных CDR

1. Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.
    
4. На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.
    
5. Чтобы включить удаление, выберите параметр **Enable Purging of CDRs** (Включить очистку CDR).
    
6. В параметре **Keep call detail recordings CDRs for maximum duration (days):** (Сохранять CDR не более (дней)) выберите максимальное число дней, в течение которых должны храниться данные регистрации вызовов.
    
7. В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.
    
8. Щелкните **Исполнить**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Указание параметров хранения CDR с помощью командлетов Windows PowerShell

Можно создавать параметры хранения CDR с помощью командлета Set-CsCdrConfiguration и Windows PowerShell. Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Задание параметров хранения CDR для конкретного расположения

- Эта команда позволяет очищать данные CDR для сайта Redmond и настраивает сайт для обслуживания данных CDR и данных отчетов об ошибках в течение 20 дней.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Задание параметров хранения CDR для нескольких расположений

- Эта команда настраивает параметры хранения CDR для всех параметров конфигурации CDR, используемых в организации.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Для получения дополнительных сведений см раздел справки для командлета [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>См. также

[Вызовов компании recording (CDR) в Скайп for Business Server](call-detail-recording-cdr.md)