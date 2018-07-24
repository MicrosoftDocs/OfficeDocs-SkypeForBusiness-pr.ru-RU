---
title: Создание или изменение коллекции параметров конфигурации CDR в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Сводка: Сведения о регистрации вызовов (CDR) в Скайп для Business Server.'
ms.openlocfilehash: f1bbf12f3766156b5f30ef3f2760669791e8c4c0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970374"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Создание или изменение коллекции параметров конфигурации CDR в Скайп для Business Server
 
**Сводка:** Сведения о регистрации вызовов (CDR) в Скайп для Business Server.
  
Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.
  
При установке Скайп для Business Server single глобальной коллекции параметров конфигурации CDR будет создан автоматически. Администраторы также могут создавать особые параметры на уровне сайта. Если такие параметры на уровне сайта используются, то они имеют преимущество перед глобальными параметрами. Например, если создаются параметры для сайта Redmond на уровне сайта, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR на сайте Redmond.
  
Параметры конфигурации CDR можно создать с помощью любого из Скайп для панели управления Business Server или командлет [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Скайп для панели управления Business Server или командлета [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) можно использовать для изменения существующих параметров. Если Скайп для панели управления Business Server используется для создания или изменения параметров, будут доступны вам следующие параметры:
  
|**Параметр пользовательского интерфейса**|**Параметр PowerShell**|**Описание**|
|:-----|:-----|:-----|
|Имя  <br/> |Identity  <br/> |Уникальный идентификатор создаваемых параметров конфигурации CDR. Эти параметры можно создавать только на уровне сайта.  <br/> |
|Enable monitoring of CDRs (Включить мониторинг CDR)  <br/> |EnableCDR  <br/> |Указывает, включен ли CDR.  <br/> |
|Enable purging of CDRs (Включить очистку CDR)  <br/> |EnablePurging  <br/> |Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.  <br/> |
|Keep CDRs for maximum duration (days) (Сохранять CDR не более (дней))  <br/> |Качестве значения этого свойства  <br/> |Указывает число дней, в течение которых записи CDR должны храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удаляться (обратите внимание, что удаление выполняется только при включении очистки).  <br/> |
|Keep error report data for maximum duration (days) (Сохранять данные отчетов об ошибках не более (дней))  <br/> |KeepErrorReportForDays  <br/> |Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удаляться. Отчеты об ошибках CDR представляют собой диагностические отчеты, которые отправляют клиентские приложения.  <br/> |
   
> [!NOTE]
> Командлеты New-CsCdrConfiguration и Set-CsCdrConfiguration включать дополнительные параметры, не доступны в Скайп для панели управления Business Server. В разделе [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) и [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) разделов справки для получения дополнительных сведений.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Создание параметров конфигурации CDR с помощью Скайп для панели управления Business Server

1. В Скайп для панели управления Business Server щелкните **мониторинг и Архивация**.
    
2. На вкладке **Регистрация вызовов** нажмите кнопку **Создать**.
    
3. В диалоговом окне **выбора сайта** выберите сайт, в котором должны быть созданы новые параметры конфигурации. Если диалоговое окно пустое, это означает, что всем вашим сайтам уже назначена коллекция параметров конфигурации CDR. На каждом сайте может быть только одна такая коллекция. В этом случае можно либо удалить параметры и создать их заново, либо просто изменить существующие параметры.
    
4. В диалоговом окне **создания параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение существующих параметров конфигурации CDR с помощью Скайп для панели управления Business Server

1. В Скайп для панели управления Business Server щелкните **мониторинг и Архивация**.
    
2. Дважды щелкните набор параметров для изменения, или выберите коллекцию, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**. Обратите внимание на то, что можно изменять только одна коллекция за раз. Чтобы изменить же нескольких семейств сайтов, используйте Скайп для консоли Business Server.
    
3. В диалоговом окне **изменения параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell

Можно создать конфигурации CDR, параметры также можно создавать с помощью Windows PowerShell и командлет **New-CsCdrConfiguration** . Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Создание новой коллекции параметров конфигурации CDR

 Следующая команда создает новую коллекцию параметров конфигурации CDR, относящуюся к сайту Redmond:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Создание коллекции параметров конфигурации CDR, которая отключает регистрацию вызовов

 Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации CDR, которая по умолчанию отключает регистрацию вызовов, используйте команду, аналогичную следующей:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR

 Можно изменить несколько значений свойств, включив несколько параметров. Например, следующая команда настраивает новые параметры таким образом, чтобы записи CDR хранились 30 дней, а отчеты об ошибках 90 дней:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Для получения дополнительных сведений см раздел справки для командлета [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

