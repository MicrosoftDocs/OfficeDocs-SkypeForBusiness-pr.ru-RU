---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Для проверки репликации подготовки домена, выполнить на этапе Step 1: Подготовка схемы, это необходимо для запуска командлета из Скайп для Business Server Management Shell Командная консоль Lync Server. Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена". Выполните следующие действия.'
ms.openlocfilehash: 8adec80d9f0874e395150941cada02f58099bce9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216076"
---
# <a name="verify-replication-in-the-domain"></a>Проверка репликации в домене
 
Для проверки репликации подготовки домена, выполнена в **Шаг 1: Подготовка схемы**, необходимо выполнить командлет из Скайп для Business Server Management Shell Командная консоль Lync Server. Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена". Выполните следующие действия.
  
1. Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.
    
2. В Windows PowerShell введите следующую команду:
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Например:
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Параметр GlobalSettingsDomainController позволяет указать место хранения глобальных параметров. Если параметры хранятся в контейнере System (как правило, с помощью обновления развертывания, которые не были глобальным параметром перенесенных к контейнеру конфигурации), можно определить контроллер домена в корне леса доменных служб Active Directory. Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу. Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory. 
  
    Если параметр Domain не указан, в качестве значения используется локальный домен. В случае успешной подготовки домена этот командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.
    

