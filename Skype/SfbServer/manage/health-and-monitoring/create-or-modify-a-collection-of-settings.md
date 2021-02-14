---
title: Создание или изменение коллекции параметров конфигурации CDR в Skype для бизнеса Server
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: Сводка. Сведения о регистрации вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: 77529204483924664a462913e8d33eaa54e55453
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817019"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Создание или изменение коллекции параметров конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Узнайте о регистрации вызовов (CDR) в Skype для бизнеса Server.
  
Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.
  
При установке Skype для бизнеса Server создается одна глобальная коллекция параметров конфигурации CDR. Администраторы также имеют возможность создания пользовательских параметров на уровне сайта. При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами. Например, если вы создаете параметры на уровне сайта для сайта Redmond, эти параметры (а не глобальные параметры) будут использоваться для управления CDR в Редмонде.
  
Параметры конфигурации CDR можно создать с помощью панели управления Skype для бизнеса Server или с помощью [cmdlet New-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings. Если для создания или изменения параметров используется панель управления Skype для бизнеса Server, вам будут доступны следующие параметры:
  
|**Параметр пользовательского интерфейса**|**Параметр PowerShell**|**Описание**|
|:-----|:-----|:-----|
|Имя  <br/> |Identity  <br/> |Уникальный идентификатор для параметров конфигурации CDR, которые создаются. Эти параметры можно создать только на уровне сайта.  <br/> |
|Включить мониторинг CDRs  <br/> |EnableCDR  <br/> |Указывает, включен ли мониторинг регистрации вызовов (CDR).  <br/> |
|Включить purging of CDRs  <br/> |EnablePurging  <br/> |Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.  <br/> |
|Хранить CDRs в течение максимальной продолжительности (дней)  <br/> |KeepCallDetailForDays  <br/> |Указывает количество дней, в течение которое записи CDR будут храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удалены. (Обратите внимание, что она будет происходить только в том случае, если она включена.)  <br/> |
|Хранить данные отчета об ошибках в течение максимальной продолжительности (дней)  <br/> |KeepErrorReportForDays  <br/> |Указывает количество дней, в течение которое хранятся отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удалены. Отчеты об ошибках CDR — это диагностические отчеты, загруженные клиентских приложений.  <br/> |
   
> [!NOTE]
> The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel. Дополнительные сведения см. в справке [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) и [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Создание параметров конфигурации CDR с помощью панели управления Skype для бизнеса Server

1. In Skype for Business Server Control Panel click **Monitoring and Archiving**.
    
2. На **вкладке "Регистрация вызовов"** нажмите кнопку **"Новый"**.
    
3. В **диалоговом окне "Выбор** сайта" выберите сайт, на котором будут созданы новые параметры конфигурации. Если диалоговое окно пустое, это означает, что всем сайтам уже назначена коллекция параметров конфигурации CDR. Каждый сайт ограничен одной такой коллекцией. В этом случае можно либо удалить, а затем повторно создать параметры, либо просто изменить существующие параметры.
    
4. В **диалоговом окке** "Настройка регистрации вызовов" (CDR) выберите нужные параметры и нажмите кнопку **"Зафиксировать".**
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение существующих параметров конфигурации CDR с помощью панели управления Skype для бизнеса Server

1. In Skype for Business Server Control Panel click **Monitoring and Archiving**.
    
2. Дважды щелкните коллекцию параметров, которые необходимо изменить, или выберите коллекцию, нажмите кнопку **"Изменить"** и выберите **"Показать сведения".** Обратите внимание, что одновременно можно изменять только одну коллекцию. Чтобы внести одинаковые изменения в несколько коллекций, используйте вместо этого оболочку управления Skype для бизнеса Server.
    
3. В **диалоговом окте** "Изменение параметров регистрации вызовов" (CDR) выберите нужные параметры и нажмите кнопку **"Зафиксировать".**
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации CDR с помощью Windows PowerShell cmdlets

Можно также создать параметры конфигурации CDR с помощью Windows PowerShell и с помощью Windows PowerShell **New-CsCdrConfiguration.** Вы можете запустить этот Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Создание новой коллекции параметров конфигурации CDR

 Эта команда создает новую коллекцию параметров конфигурации CDR, применяемых к сайту Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Создание коллекции параметров конфигурации CDR, которые отключят регистрацию вызовов

 Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации регистрации вызовов, которые по умолчанию позволяют отключить регистрацию вызовов, используйте данная команда:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR

 Можно изменить несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохраняемых записей call Detail в течение 30 дней и отчетов об ошибках в течение 90 дней:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Дополнительные сведения см. в разделе справки по [cmdlet New-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
  

