---
title: Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться настраивать интеграцию с хранилищем Exchange в Skype для бизнеса Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234333"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server
 
**Сводка:** В этой статье рассказывается, как настроить интеграцию с хранилищем Exchange в Skype для бизнеса Server.
  
Если вы используете Microsoft Exchange Integration для всех пользователей в развертывании, вам не нужно настраивать политики архивации в Skype для бизнеса Server для пользователей. Вместо этого вы настраиваете политики хранения на месте Exchange для поддержки архивирования для пользователей, размещенных на Exchange, с почтовыми ящиками, которые помещаются на хранение на месте. Перед настройкой интеграции с хранилищем Exchange Читайте [план архивации в Skype для бизнеса Server](../../plan-your-deployment/archiving/archiving.md). Дополнительные сведения о политиках удержания на месте Exchange можно найти в документации по продукту Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Настройка интеграции с хранилищем Microsoft Exchange

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.
    
   - Чтобы включить интеграцию с хранилищем Exchange, установите флажок **интеграция Microsoft Exchange** .
    
   - Чтобы отключить интеграцию с хранилищем Exchange, снимите флажок **интеграция Microsoft Exchange** .
    
5. Нажмите **Исполнить**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Развертывание Skype для бизнеса Server и Microsoft Exchange в разных лесах

Если вы используете Microsoft Exchange Integration и Microsoft Exchange Server не развернут в том же лесу, что и Skype для бизнеса Server, необходимо убедиться, что указанные ниже атрибуты Exchange Active Directory синхронизированы с лесом, в котором Skype для Развернут сервер Business Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.
  

