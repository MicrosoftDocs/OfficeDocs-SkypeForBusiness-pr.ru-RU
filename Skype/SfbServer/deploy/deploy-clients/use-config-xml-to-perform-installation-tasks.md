---
title: Использование файла Config.xml для выполнения задач установки в Скайп пользователей
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: Сводка. Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003510"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Использование файла Config.xml для выполнения задач установки в Скайп пользователей
 
**Сводка.** Сведения об использовании файла Config.xml для определения дополнительных инструкций по установке.
  
Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:
  
- задание пути для точки сетевой установки;
    
- выбор устанавливаемых продуктов;
    
- настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;
    
- задание параметров установки, таких как имя пользователя;
    
- копирование локального источника установки на компьютер пользователя без установки Office;
    
- добавление и удаления языков из установки.
    
Мы рекомендуем использовать файл Config.xml для настройки Скайп для бизнеса автоматической установки. 
  
По умолчанию в файле Config.xml, который хранится в папке основного продукта (например, \ _продукта_. WW) направляет программы установки для установки продукта. Например файл Config.xml в папке устанавливает Скайп для бизнеса:
  
- \\server\share\Skype15\Skype.ww \Config.xml
    
В следующей таблице перечислены элементы Config.xml, чаще всего используемые для Скайп для установки Business.
  
**Элементы Config.xml**

|**Элемент**|**Описание**|
|:-----|:-----|
|Configuration  <br/> |Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync. (Это работает только для клиентов Skype для бизнеса.)  <br/> |
|OptionState  <br/> | Определяет, как при установке будут обрабатываться компоненты конкретного продукта. Используйте следующие атрибуты для предотвращения установки служб Business Connectivity Services, который включает в себя общие компоненты, которые мешают Outlook: <br/>  ID = «LOBiMain» <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Display  <br/> | Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты: <br/>  CompletionNotice = «Yes» | No"(default) « <br/>  AcceptEula = «Yes» | No"(default) « <br/> |
|Logging  <br/> | Параметры ведения журнала программой установки. Обычно используются следующие атрибуты: <br/>  Тип = «Off» | Standard"(default) « | «Verbose» <br/>  Шаблон =» _filename_.txt» (имя файла журнала)  <br/> |
|Setting  <br/> | Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:<br/>  Setting Id =» _имя_"(имя свойства установщика Windows)  <br/>  Значение =» _значение_"(значение, задаваемое свойству)  <br/> |
|DistributionPoint  <br/> | Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:<br/>  Расположение =» _путь_"  <br/> |
   
Следующий пример показывает файл Config.xml для типичной автоматической установки Скайп для клиента Business. 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Подробные сведения об использовании файла Config.xml для выполнения задач установки и обслуживания Office доступном по адресу [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).
  
## <a name="to-customize-the-configxml-file"></a>Изменение файла Config.xml

1. Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".
    
2. Найдите строки, содержащие элементы, которые нужно изменить.
    
3. Измените запись для элемента, используя нужные значения параметров автоматической установки. Убедитесь в том, что вы удалить разделители комментариев "\<!--» и «--\>«. Например, используйте следующий синтаксис:
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. Сохраните файл Config.xml.
    

