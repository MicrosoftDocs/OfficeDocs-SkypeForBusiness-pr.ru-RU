---
title: Управление параметрами конфигурации сервера конференций в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Сводка: сведения об управлении параметрами конфигурации сервера конференций в Skype для бизнеса Server.'
ms.openlocfilehash: be6ccb094cc19a29534d1ca78eb2cae1457d6512
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991904"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Управление параметрами конфигурации сервера конференций в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как управлять параметрами конфигурации сервера конференций в Skype для бизнеса Server.
  
В этом разделе описывается, как управлять параметрами конфигурации конференц-связи. Дополнительные сведения о планировании и развертывании конференций можно найти [в разделе Планирование конференций в Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и [развертывание конференций в Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры настройки конференц-связи определяют максимально допустимый размер контента и выдач для собрания; Максимальная пропускная способность для службы конференц-связи с приложениями. ограничения хранилища и периоды срока действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получить справку по Конференции и ресурсы; и порты, используемые для общего обмена приложениями, звука клиента, передачи файлов и мультимедийного трафика. These settings allow you to manage the actual servers themselves. Эти параметры можно настроить с помощью командной консоли Skype для бизнеса Server.
  
При установке Skype для бизнеса Server система предоставляет единую коллекцию параметров конфигурации конференций (глобальную коллекцию). Если вам нужно создать пользовательские параметры для сайта или службы, это можно сделать с помощью командлета **New-ксконференЦингконфигуратион** . Обратите внимание на то, что новые параметры можно применять только в области веб-сайта или службы; Вы не можете создать новую глобальную коллекцию параметров конфигурации конференций, но вы можете изменить глобальную коллекцию с помощью командлета **Set-ксконференЦингконфигуратион** . Кроме того, ни один из сайтов или служб не может разместить больше одной коллекции параметров. Если вы попытаетесь создать новые параметры для сайта Redmond и на сайте Redmond уже размещена коллекция параметров настройки конференц-связи, команда завершится сбоем.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Управление параметрами настройки конференц-связи с помощью командной консоли Skype для бизнеса Server

Для управления параметрами настройки конференц-связи с помощью командной консоли Skype для бизнеса Server выполните следующие командлеты:
  
**Параметры конфигурации конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференц-связи для организации.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации конференц-связи.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
Приведенная ниже команда создает новую коллекцию параметров конфигурации конференц-связи для сайта Redmond (site:Redmond). В этом примере используется один дополнительный параметр (Organization), с помощью которого свойству Organization присваивается значение Litwareinc. 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Обратите внимание на то, что для каждого сайта может быть только одна такая коллекция. Эта команда завершится сбоем, если у сайта Redmond уже есть коллекция параметров конфигурации конференц-связи. 
  
В следующем примере определяется новая коллекция параметров конфигурации конференц-связи, которые изначально хранилась в памяти, а позднее были применены к сайту Redmond. 
  
Первая команда с помощью командлета **New-CsConferencingConfiguration** создает в памяти новую коллекцию параметров, хранящуюся в переменной $x. Параметр InMemory указывает на то, что коллекцию необходимо создать в памяти, а не применить немедленно к сайту Redmond.
  
После создания коллекции вторая команда присваивает свойству Organization значение Litwareinc. 
  
Наконец, третья команда вызывает командлет **Set-CsConferencingConfiguration**, который применяет созданные параметры к сайту Redmond.
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Без вызова командлета **Set-CsConferencingConfiguration** новые параметры никогда не вступят в силу. Вместо этого они исчезнут сразу после завершения текущего сеанса Windows PowerShell или удаления переменной $x.
  

