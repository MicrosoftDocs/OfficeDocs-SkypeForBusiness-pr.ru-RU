---
title: Развертывание вызова с помощью работы в Skype для бизнеса Server
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
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: Сводка. Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825009"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Развертывание вызова с помощью работы в Skype для бизнеса Server
 
**Сводка:** Узнайте, как развернуть call Via Work в Skype для бизнеса Server для некоторых или всех пользователей.
  
Используйте эти действия для развертывания call Via Work для пользователей. Вопросы планирования обсуждаются в плане "Позвонить [с работы" в Skype для бизнеса Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) В предыдущих версиях удаленного управления вызовами Lync Server была возможностью, которая позволяла пользователям управлять телефонами УАЦ с помощью Lync Server. В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы". 
  
## <a name="prerequisites-for-call-via-work"></a>Необходимые условия для вызова с помощью работы

Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Server. Чтобы включить для пользователей возможность "Позвонить с помощью работы", необходимо также иметь следующие необходимые условия: 
  
- Сервер-посредник должен быть развернут как в составе сервера переднего плана, так и в качестве автономных ролей. Также необходимо развернуть шлюз IP-PBX.
    
- Все пользователи, которым будет включена возможность вызова с помощью работы, должны иметь прямой включаемой набор (DID) в телефонной системе УАЦ. 
    
- Необходимо включить для всех пользователей call Via Work Корпоративная голосовая связь. При этом необходимо настроить для каждого пользователя номер DID Skype для бизнеса на соответствующий номер DID для соответствующей телефонной системы УАТС. 
    
- Для всех пользователей, которые будут  использовать функцию "Позвонить с работы", в клиенте Skype для бизнеса должна быть выбрана автоматическая настройка.  Это позволяет клиенту обнаружить URL-адреса UCWA. **Автоматическая настройка** — это выбор по умолчанию.
    
- Для каждого пользователя «Позвонить с работы». 
    
- Убедитесь, что для каждого пользователя "Позвонить с помощью работы" включена возможность телефонного и телефонного звонка. Это позволяет этим пользователям получать доступ к конференциям Skype для бизнеса и выход из них.
    
- Убедитесь, что делегирования, групповые вызовы и группы ответа отключены для каждого пользователя "Позвонить с работы".
    
## <a name="deploy-call-via-work"></a>Развертывание функции вызовов с рабочего телефона

После создания необходимых условий сделайте следующее:
  
- Создайте глобальный номер телефона для развертывания, который Skype для бизнеса отображает в ИД вызываемого УАТБ пользователя, который звонит с помощью работы. 
    
- Создание одной или более политик "Позвонить с помощью работы"
    
- Назначение политики "Позвонить с помощью работы" каждому пользователю, для которого будет включена возможность вызова с помощью работы
    
### <a name="create-the-call-via-work-global-phone-number"></a>Создание глобального номера телефона "Позвонить с помощью работы"

- Введите следующий cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Например, следующий cmdlet задает глобальный номер телефона 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Создание политики "Позвонить с помощью работы"

- Введите следующий cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Например, следующий cmdlet создает политику call Via Work под названием ContosoUser1CvWP, требует от пользователя использовать номер вызова администратора и устанавливает для этого номера вызова 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Назначение пользователю политики "Позвонить с помощью работы"

- Введите следующий cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Например, следующий cmdlet назначает политику Call Via Work "ContosoUser1CvWP" пользователю с именем **ContosoUser1.**
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>См. также

[Планирование звонков с помощью работы в Skype для бизнеса Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

