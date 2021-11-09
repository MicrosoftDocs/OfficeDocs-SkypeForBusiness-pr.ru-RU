---
title: Настройка интеграции с Exchange для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как настроить интеграцию с Exchange в Skype для бизнеса Server.
ms.openlocfilehash: 12d93a48e88d7086a1c8b1fec83c44a080ebf4af
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853803"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Настройка интеграции с Exchange для Skype для бизнеса Server
 
**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить интеграцию с Exchange в Skype для бизнеса Server.
  
Если вы используете Exchange microsoft для всех пользователей в развертывании, вам не нужно настраивать Skype для бизнеса Server архивации для пользователей. Вместо этого вы Exchange In-Place политики hold для поддержки архива для пользователей, Exchange на сайте, а их почтовые ящики In-Place Hold. Перед настройкой интеграции с Exchange хранения ознакомьтесь с планом архивации в [Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md) Сведения о политиках Exchange In-Place удержания см. в Exchange документации по продуктам. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Настройка интеграции с хранилищем Exchange Майкрософт

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**
    
4. Щелкните имя соответствующей конфигурации — глобальной, сайта или пула — в списке конфигураций архивирования, затем щелкните **Правка**, щелкните **Показать подробности** и выполните следующие действия:
    
   - Чтобы включить интеграцию с Exchange хранилищем, выберите Exchange **microsoft.**
    
   - Чтобы отключить интеграцию с Exchange хранилищем, **зачистим** Exchange microsoft.
    
5. Щелкните **Исполнить**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Когда Skype для бизнеса Server и microsoft Exchange развертываются в различных лесах

Если используется интеграция Microsoft Exchange и Microsoft Exchange Server не развертывается в том же лесу, что и Skype для бизнеса Server, необходимо убедиться, что следующие атрибуты Exchange Active Directory синхронизируются с лесом, в котором Skype для бизнеса Server развернута:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.
  

