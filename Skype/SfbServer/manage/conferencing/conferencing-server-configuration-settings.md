---
title: Управление параметрами конфигурации сервера конференций в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Сводка: Узнайте, как управлять параметрами конфигурации сервера конференц-связи в Скайп для Business Server 2015.'
ms.openlocfilehash: 88c127acdd569945eddb41e997034e5ea23ea2a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>Управление параметрами конфигурации сервера конференций в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как управлять параметрами конфигурации сервера конференц-связи в Скайп для Business Server 2015.
  
В этом разделе описывается, как управлять параметрами конфигурации конференц-связи. Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры конфигурации конференц-связи определить такие параметры, как максимальный допустимый размер содержимого собрания и раздаточные материалы; Максимальный объем пропускной способности для службы конференц-связь, совместное использование приложений; ограничения для хранилища и срок действия; загружаемые файлы для URL-адреса для внутренних и внешних поддерживаемые клиента; указатели на внутренних и внешних URL-адреса, где пользователи могут получить помощь конференц-связи и ресурсов; и портов, используемых для общего доступа к приложениям, клиент аудио-, передача файлов и трафика мультимедиа. Эти параметры позволяют управлять фактический самого сервера. Эти параметры можно настроить с помощью Скайп для консоли Business Server.
  
При установке Скайп для Business Server система предоставляет одной коллекции конференц-связи параметры конфигурации (глобальной коллекции). Если вам необходимо создать настраиваемые параметры для сайта или службы, это можно сделать с помощью командлета **New-CsConferencingConfiguration** . Обратите внимание на то, что новые параметры могут применяться только на уровне сайта или службы; не удается создать новую коллекцию глобальных конференц-связи, параметры конфигурации, однако можно изменить глобальную коллекцию с помощью командлета **Set-CsConferencingConfiguration** . Кроме того не сайта или службы может размещаться более чем одной коллекции параметров. Если вы попытаетесь для создания новых параметров для Redmond сайта и Redmond уже хранится коллекция параметров конфигурации конференц-связи сайтов, а затем команда завершится с ошибкой.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Управление параметрами конфигурации конференц-связи с помощью Скайп для консоли Business Server

Для управления параметрами конфигурации конференц-связи с помощью Скайп для консоли Business Server, используйте следующие командлеты:
  
**Параметры конфигурации конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференц-связи для организации.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации конференц-связи.  <br/> |
|[SET-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
Приведенная ниже команда создает новую коллекцию параметров конфигурации конференц-связи для сайта Redmond (site:Redmond). В этом примере используется один дополнительный параметр (Organization), с помощью которого свойству Organization присваивается значение Litwareinc. 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc

```

Обратите внимание на то, что для каждого сайта может быть только одна такая коллекция. Эта команда завершится сбоем, если у сайта Redmond уже есть коллекция параметров конфигурации конференц-связи. 
  
В следующем примере определяется новая коллекция параметров конфигурации конференц-связи, которые изначально хранилась в памяти, а позднее были применены к сайту Redmond. 
  
Первая команда с помощью командлета **New-CsConferencingConfiguration** создает в памяти новую коллекцию параметров, хранящуюся в переменной $x. Параметр InMemory указывает на то, что коллекцию необходимо создать в памяти, а не применить немедленно к сайту Redmond.
  
После создания коллекции вторая команда присваивает свойству Organization значение Litwareinc. 
  
Наконец, третья команда вызывает командлет **Set-CsConferencingConfiguration**, который применяет созданные параметры к сайту Redmond.
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x

```

Без вызова командлета **Set-CsConferencingConfiguration** новые параметры никогда не вступят в силу. Вместо этого они исчезнут сразу после завершения текущего сеанса Windows PowerShell или удаления переменной $x.
  

