---
title: Создание и изменение коллекции параметров конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Сводка: сведения о записи звонков в Skype для бизнеса Server (CDR).'
ms.openlocfilehash: c0a54835fe74a32a92996874cb6fd895fd49fafc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305836"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Создание и изменение коллекции параметров конфигурации CDR в Skype для бизнеса Server
 
**Сводка:** Сведения о записи звонков в Skype для бизнеса Server (CDR).
  
Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.
  
При установке Skype для бизнеса Server для вас создается единая глобальная коллекция параметров конфигурации CDR. Администраторы также могут создавать особые параметры на уровне сайта. Если такие параметры на уровне сайта используются, то они имеют преимущество перед глобальными параметрами. Например, если создаются параметры для сайта Redmond на уровне сайта, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR на сайте Redmond.
  
Вы можете создавать параметры конфигурации CDR с помощью панели управления "Skype для бизнеса Server" или командлетом [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Вы можете использовать панель управления Skype для бизнеса Server или командлет [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) для изменения существующих параметров. Если вы используете панель управления Skype для бизнеса Server для создания и изменения параметров, вам будут доступны следующие параметры:
  
|**Параметр пользовательского интерфейса**|**Параметр PowerShell**|**Описание**|
|:-----|:-----|:-----|
|Имя  <br/> |Identity  <br/> |Уникальный идентификатор создаваемых параметров конфигурации CDR. Эти параметры можно создавать только на уровне сайта.  <br/> |
|Enable monitoring of CDRs (Включить мониторинг CDR)  <br/> |EnableCDR  <br/> |Указывает, включен ли CDR.  <br/> |
|Enable purging of CDRs (Включить очистку CDR)  <br/> |EnablePurging  <br/> |Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.  <br/> |
|Keep CDRs for maximum duration (days) (Сохранять CDR не более (дней))  <br/> |KeepCallDetailForDays  <br/> |Указывает число дней, в течение которых записи CDR должны храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удаляться (обратите внимание, что удаление выполняется только при включении очистки).  <br/> |
|Keep error report data for maximum duration (days) (Сохранять данные отчетов об ошибках не более (дней))  <br/> |KeepErrorReportForDays  <br/> |Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удаляться. Отчеты об ошибках CDR представляют собой диагностические отчеты, которые отправляют клиентские приложения.  <br/> |
   
> [!NOTE]
> Командлеты New-Кскдрконфигуратион и Set-Кскдрконфигуратион включают дополнительные параметры, недоступные на панели управления Skype для бизнеса Server. Для получения дополнительных сведений ознакомьтесь с разделами справки [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) и [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Создание параметров конфигурации CDR с помощью панели управления "Skype для бизнеса Server"

1. На панели управления Skype для бизнеса Server нажмите кнопку **наблюдение и архивация**.
    
2. На вкладке **запись сведений о звонке** нажмите кнопку **создать**.
    
3. В диалоговом окне **выбора сайта** выберите сайт, в котором должны быть созданы новые параметры конфигурации. Если диалоговое окно пустое, это означает, что всем вашим сайтам уже назначена коллекция параметров конфигурации CDR. На каждом сайте может быть только одна такая коллекция. В этом случае можно либо удалить параметры и создать их заново, либо просто изменить существующие параметры.
    
4. В диалоговом окне **создания параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение существующих параметров конфигурации CDR с помощью панели управления Skype для бизнеса Server

1. На панели управления Skype для бизнеса Server нажмите кнопку **наблюдение и архивация**.
    
2. Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**. Note that you can only modify a single collection at a time. Чтобы внести одни и те же изменения в несколько коллекций, вместо этого используйте командную консоль управления Skype для бизнеса Server.
    
3. В диалоговом окне **изменения параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell

Вы также можете создавать параметры конфигурации CDR с помощью Windows PowerShell и командлета **New-кскдрконфигуратион** . Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.
  
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

Дополнительные сведения можно найти в разделе справки по командлету [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

