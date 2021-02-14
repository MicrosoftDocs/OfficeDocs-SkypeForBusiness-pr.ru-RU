---
title: Управление настройками конфигурации сервераконференций в Skype для бизнеса Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: Сводка. Узнайте, как управлять настройками конфигурации сервера конфигурации сервераконференций в Skype для бизнеса Server.
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828289"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Управление настройками конфигурации сервераконференций в Skype для бизнеса Server
 
**Сводка:** Learn how to manage conferencing server configuration settings in Skype for Business Server.
  
В этом разделе описывается, как управлять настройками конфигурации для conferencing. Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Параметры конфигурации проведения собраний определяют такие параметры, как максимальный допустимый размер содержимого собрания и раздаточной информации; максимальная пропускная способность для службы общего доступа к приложениям; ограничения хранилища и сроки действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получить справку и ресурсы по видеоконференциям; порты, используемые для общего доступа к приложениям, клиентского звука, передачи файлов и трафика мультимедиа; Эти параметры позволяют управлять фактическими серверами самостоятельно. Эти параметры можно настроить с помощью оболочки управления Skype для бизнеса Server.
  
При установке Skype для бизнеса Server система предоставляет одну коллекцию параметров конфигурации (глобальной коллекции). Если необходимо создать настраиваемые параметры для сайта или службы, это можно сделать с помощью cmdlet **New-CsConferencingConfiguration.** Обратите внимание, что новые параметры можно применять только на уровне сайта или службы; Невозможно создать глобальную коллекцию параметров конфигурации, но глобальную коллекцию можно изменить с помощью **cmdlet Set-CsConferencingConfiguration.** Кроме того, ни на одном сайте или в службе не может быть более одной коллекции параметров. Если попытаться создать новые параметры для сайта Redmond, а на сайте Redmond уже размещена коллекция параметров конфигурации, команда не будет работать.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Manage conferencing configuration settings by using Skype for Business Server Management Shell

Для управления настройками конфигурации с помощью skype для бизнеса Server Management Shell используйте следующие команды:
  
**Параметры конфигурации conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации для организации.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров конфигурации для собраний.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации conferencing.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
Следующая команда создает новую коллекцию параметров конфигурации для сайта Redmond (site:Redmond). В этом примере включается один дополнительный параметр (Organization), который используется для того, чтобы установить для свойства Organization значение Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Обратите внимание, что на сайте может быть только одна такая коллекция, поэтому эта команда не удастся, если на сайте Redmond уже есть коллекция параметров конфигурации для собраний. 
  
В следующем примере определяется новая коллекция параметров конфигурации, которые изначально хранятся в памяти, а затем применяются к сайту Redmond позже. 
  
Первая команда использует командлет **New-CsConferencingConfiguration** для создания новой коллекции параметров в памяти, хранимых в переменной $x. Параметр InMemory указывает, что коллекция должна создаваться в памяти, а не сразу применяться к сайту Redmond.
  
После создания коллекции вторая команда присваивает свойству Organization значение Litwareinc. 
  
Наконец, третья команда использует командлет **Set-CsConferencingConfiguration** для применения новых параметров к сайту Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Если не вызвать cmdlet **Set-CsConferencingConfiguration,** новые параметры никогда не будут действовать. Вместо этого они исчезнут, как только вы завершите сеанс Windows PowerShell или удалите переменную $x.
  

