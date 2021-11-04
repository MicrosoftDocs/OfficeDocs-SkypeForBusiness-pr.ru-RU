---
title: Проверка развертывания Edge в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: Сводка. Узнайте, как убедиться, что развертывание пула Edge Server или Edge Server работает в Skype для бизнеса Server.
ms.openlocfilehash: d3552d814a9b30433cbeb53674737563b11f8283
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771611"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Проверка развертывания Edge в Skype для бизнеса Server
 
**Сводка:** Узнайте, как убедиться, что развертывание пула Edge Server или Edge Server работает в Skype для бизнеса Server.
  
После развертывания пула Edge Server или Edge Server необходимо знать, работает ли он должным образом. Вот несколько вещей, которые могут помочь в подтверждении подключения среды Edge к внутренним серверам, а также подключения внешних пользователей к вашей Skype для бизнеса Server среде с помощью edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Проверка подключения между внутренними серверами и edge-серверами

Хотя проверка подключения автоматически делается в пуле Edge Server или Edge Server при установке edge Server, вы можете подтвердить это самостоятельно с помощью Windows PowerShell. Запустите Get-CsManagementStoreReplicationStatus на внутреннем сервере, на котором хранится центр управления, или на любом компьютере, на котором Skype для бизнеса Server основных компонентов (OcsCore.msi).
  
Первоначальный результат запуска этой команды может дать для репликации ложный статус, а не True. Если это произойдет, запустите Invoke-CsManagementStoreReplication. Дайте ему некоторое время для завершения репликации, а затем запустите Get-CsManagementStoreReplicationStatus еще раз.
  
## <a name="verify-connectivity-for-your-external-users"></a>Проверка подключения для внешних пользователей

У нас есть отличный инструмент для подтверждения конфигурации edge Server, а также возможность подключения, отправки и получения правильных сообщений для сценариев Edge Server. Это сайт [Удаленного подключения Anaylzer](https://testconnectivity.microsoft.com/). Это сайт, управляемый и поддерживаемый Службой поддержки Майкрософт. Чтобы использовать этот инструмент, просмотрите веб-сайт и следуйте инструкциям, чтобы выбрать правильный сценарий для вас.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Что следует учитывать при тестировании внешних подключений пользователей

Любой тест для внешнего доступа к пользователю должен включать каждый тип внутреннего пользователя, поддерживаемого организацией, который может включать любой из следующих ниже.
  
- Пользователи из хотя бы одного федератного домена (мы рекомендуем их все тестировать).
    
- Анонимные пользователи.
    
- Пользователи в организации, которые вошли в систему Skype для бизнеса удаленно, но не используют VPN.
    
Эти тесты определят, является ли ваш edge Server:
  
- Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.
    
  - Например: telnet sip.contoso.com 443
    
  - В зависимости от развертывания необходимо выполнить предыдущий тест в портах, которые вы используете в вашем пуле Edge Server или Edge Server.
    
- Выполнение точного разрешения внешнего DNS.
    
  - Из-за пределов сети, ping каждый из внешних FQDNs вашего edge Server или Edge Server пула. Даже если сбой 1000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000 000
    

