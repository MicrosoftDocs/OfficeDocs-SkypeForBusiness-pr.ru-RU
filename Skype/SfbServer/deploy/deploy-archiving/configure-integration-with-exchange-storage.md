---
title: Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: Сводка. В этом разделе вы узнаете, как настроить интеграцию с хранилищем Exchange в Skype для бизнеса Server.
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825069"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server
 
**Сводка:** В этом разделе вы узнаете, как настроить интеграцию с хранилищем Exchange в Skype для бизнеса Server.
  
Если вы используете интеграцию Microsoft Exchange для всех пользователей в развертывании, вам не нужно настраивать политики архивации Skype для бизнеса Server для пользователей. Вместо этого политики удержания In-Place Exchange настраиваются для поддержки архива для пользователей, которые были In-Place exchange. Перед настройкой интеграции с хранилищем Exchange ознакомьтесь с планом архивации [в Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md) Подробные сведения о политиках In-Place Exchange см. в документации по продуктам Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Настройка интеграции с хранилищем Microsoft Exchange

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**
    
4. Щелкните имя соответствующей конфигурации — глобальной, сайта или пула — в списке конфигураций архивирования, затем щелкните **Правка**, щелкните **Показать подробности** и выполните следующие действия:
    
   - Чтобы включить интеграцию с хранилищем Exchange, выберите **этот** окне.
    
   - Чтобы отключить интеграцию с хранилищем Exchange, с помощью этого окне необходимо с **помощью** этого окна.
    
5. Щелкните **Исполнить**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Развертывание Skype для бизнеса Server и Microsoft Exchange в разных лесах

Если вы используете интеграцию Microsoft Exchange и Microsoft Exchange Server развернуты не в том же лесу, что и Skype для бизнеса Server, необходимо убедиться, что следующие атрибуты Exchange Active Directory синхронизированы с лесом, в котором развернут Skype для бизнеса Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.
  

