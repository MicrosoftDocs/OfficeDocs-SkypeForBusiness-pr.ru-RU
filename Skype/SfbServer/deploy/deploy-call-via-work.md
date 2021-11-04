---
title: Развертывание вызовов с помощью Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: Сводка. Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.
ms.openlocfilehash: 98d7cc08b2cb4101f1d9d062e62ef32a3998691b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761613"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Развертывание вызовов с помощью Skype для бизнеса Server
 
**Сводка:** Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.
  
Используйте эти действия для развертывания call Via Work для пользователей. Соображения планирования обсуждаются в [plan for Call Via Work в Skype для бизнеса Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) В предыдущих версиях удаленного управления вызовами Lync Server была функция, которая позволяла пользователям управлять своими PBX-телефонами с помощью Lync Server. В Skype для бизнеса Server эта функция была заменена на Call Via Work. 
  
## <a name="prerequisites-for-call-via-work"></a>Необходимые условия для вызова с помощью работы

Call Via Work использует веб-API единой связи (UCWA), который автоматически устанавливается на Skype для бизнеса Server серверов переднего конца. Чтобы включить пользователей для вызова с помощью работы, необходимо также иметь следующие необходимые условия: 
  
- Необходимо развернуть сервер-посредник либо в составе переднего конечного сервера, либо в качестве автономных ролей. Необходимо также развернуть шлюз IP-PBX.
    
- Все пользователи, которые будут включены для вызова с помощью работы, должны иметь в телефонной системе PBX прямой вовне телефонный набор (DID). 
    
- Необходимо включить все пользователи call Via Work для Корпоративная голосовая связь. При этом необходимо настроить номер Skype для бизнеса did для каждого пользователя на соответствующий номер DID для соответствующей телефонной системы PBX. 
    
- Все пользователи, которые будут использовать  Call Via Work, должны иметь автоматическую конфигурацию, выбранную в их варианте **Расширенные** подключения в Skype для бизнеса клиенте. Это позволяет клиенту открывать URL-адреса UCWA. **Автоматическая конфигурация** — это выбор по умолчанию.
    
- Для каждого пользователя Call Via Work взовите переададку вызовов и одновременный звон. 
    
- Для каждого пользователя Call Via Work убедитесь в том, что диалоговое и телефонное диалоговое время включено. Это позволяет этим пользователям получать доступ к конференциям и Skype для бизнеса из них.
    
- Убедитесь, что для каждого пользователя Call Via Work отключена группа делегирования, вызова группы и группы ответа.
    
## <a name="deploy-call-via-work"></a>Развертывание функции вызовов с рабочего телефона

После создания необходимых условий сделайте следующее:
  
- Создайте глобальный телефонный номер для развертывания, Skype для бизнеса отображает в ID вызываемого PBX пользователей, которые звонят с помощью рабочих вызовов. 
    
- Создание одной или более политик call via work
    
- Назначение политики "Вызов с помощью работы" каждому пользователю, который будет включен для вызова с помощью работы
    
### <a name="create-the-call-via-work-global-phone-number"></a>Создание глобального номера телефона Call Via Work

- Введите следующий cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Например, в следующем cmdlet задает глобальный номер телефона 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Создание политики вызовов с помощью работы

- Введите следующий cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Например, в следующем наборе создается политика call Via Work contosoUser1CvWP, которая требует от пользователя использовать номер вызова администратора и задает этот номер вызова 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Назначение политики вызовов с помощью работы пользователю

- Введите следующий cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Например, следующий кодлет назначает политику Call Via Work "ContosoUser1CvWP" пользователю с именем **ContosoUser1.**
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>См. также

[Планирование вызова с помощью работы в Skype для бизнеса Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

