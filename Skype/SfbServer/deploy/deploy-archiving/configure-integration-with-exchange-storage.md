---
title: Настройка взаимодействия Skype для бизнеса Server 2015 с хранилищем Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как настроить интеграцию с хранилищем Exchange в Скайп для Business Server 2015.'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a>Настройка взаимодействия Skype для бизнеса Server 2015 с хранилищем Exchange
 
**Сводка:** Прочтите этот раздел, чтобы узнать, как настроить интеграцию с хранилищем Exchange в Скайп для Business Server 2015.
  
При использовании интеграции с Microsoft Exchange для всех пользователей в вашем развертывании не нужно настроить Скайп для Business Server политик архивации для пользователей. Вместо этого настройте политики хранения на месте Exchange для поддержки архивации для пользователей, размещенных на сервере Exchange, с их почтовых ящиков, поставленных на хранение на месте. Перед настройкой интеграции с хранилищем Exchange чтение [Планирование архивации в Скайп для Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Для получения дополнительных сведений о политиках хранения на месте Exchange обратитесь к документации Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Настройка интеграции с хранилищем Microsoft Exchange

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.
    
  - Чтобы включить интеграцию с хранилищем Exchange, установите флажок **Интеграция с Microsoft Exchange** .
    
  - Чтобы отключить интеграцию с хранилищем Exchange, снимите флажок **Интеграция с Microsoft Exchange** .
    
5. Нажмите **Исполнить**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>При развертывании Скайп Business Server и Microsoft Exchange в разных лесах

При использовании интеграции с Microsoft Exchange и Microsoft Exchange Server не развертываются в том же лесу, что Скайп для Business Server, необходимо убедиться, что следующие атрибуты Active Directory в Exchange синхронизируется в лес где Скайп для Развертывается Business Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses.
    
Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.
  

