---
title: Управление настройками конфигурации серверов для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: Сводка. Узнайте, как управлять настройками конфигурации серверов для Skype для бизнеса Server.
ms.openlocfilehash: 9e0b6cbd83ebebcb2f66d178ee8c69d42702a249
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841261"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Управление настройками конфигурации серверов для Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять настройками конфигурации серверов для Skype для бизнеса Server.
  
В этом разделе описывается управление настройками конфигурации конференций. Дополнительные сведения о планировании и развертывании конференций см. в Skype для бизнеса Server Plan [for conferencing in Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры конфигурации конференций определяют такие вещи, как максимально допустимый размер для контента собраний и раздаток; максимальный объем пропускной способности для службы конференций общего доступа к приложениям; ограничения хранения и сроки действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получать помощь и ресурсы для конференциалов; и порты, используемые для общего доступа к приложениям, клиентского аудиозаписи, передачи файлов и трафика мультимедиа. Эти параметры позволяют управлять самими серверами. Эти параметры можно установить с помощью Skype для бизнеса Server управленческой оболочки.
  
При установке Skype для бизнеса Server система предоставляет вам единую коллекцию параметров конфигурации конференций (глобальная коллекция). Если необходимо создать настраиваемые параметры для сайта или службы, вы можете сделать это с помощью комлета **New-CsConferencingConfiguration.** Обратите внимание, что новые параметры можно применять только на сайте или в области службы; Вы не можете создать новую глобальную коллекцию параметров конфигурации конференций, но можно изменить глобальную коллекцию с помощью комлета **Set-CsConferencingConfiguration.** Кроме того, ни один сайт или служба не могут принимать более одной коллекции параметров. Если вы попробуете создать новые параметры для сайта Redmond, а на сайте Redmond уже размещена коллекция параметров конфигурации конференциации, то команда не справилась с управлением.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Управление настройками конфигурации конференций с помощью Skype для бизнеса Server shell

Для управления настройками конфигурации конференций с помощью Skype для бизнеса Server management Shell используйте следующие команды:
  
**Параметры конфигурации конференциации**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференций для организации.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров конфигурации конференций.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанный набор параметров конфигурации конференциации.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
Следующая команда создает новую коллекцию параметров конфигурации для веб-сайта Redmond (site:Redmond). В этом примере включен один дополнительный параметр (Organization), который используется для задания значения свойства Организации в Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Обратите внимание, что на сайте может быть только одна такая коллекция, поэтому эта команда будет неустойка, если на сайте Redmond уже есть коллекция параметров конфигурации конференциации. 
  
В следующем примере определяется новая коллекция параметров конфигурации конференциалов, которые сначала хранятся в памяти, а затем применяются к сайту Redmond в более позднее время. 
  
Первая команда использует командлет **New-CsConferencingConfiguration** для создания новой коллекции параметров в памяти, хранимых в переменной $x. Параметр InMemory указывает, что коллекция должна создаваться в памяти, а не немедленно применяться к сайту Redmond.
  
После создания коллекции вторая команда присваивает свойству Organization значение Litwareinc. 
  
Наконец, третья команда использует командлет **Set-CsConferencingConfiguration** для применения новых параметров на сайте Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Если вы не вызываем комлет **Set-CsConferencingConfiguration,** новые параметры никогда не вступает в силу. Вместо этого они исчезнут, как только завершите сеанс Windows PowerShell или удалите переменную $x.
