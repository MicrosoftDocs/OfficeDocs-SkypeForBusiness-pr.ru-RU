---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Для проверки репликации подготовки домена, выполненной в шаге 1: Подготовка схемы, необходимо выполнить командылет из Skype для бизнеса Server shell управления Lync Server Management Shell. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.'
ms.openlocfilehash: 600d024aa1f2d024c56e08afa20b7f24de086710
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857786"
---
# <a name="verify-replication-in-the-domain"></a>Проверка репликации в домене
 
Для проверки репликации подготовки домена, выполненной в шаге **1: Подготовка** схемы, необходимо выполнить командылет из Skype для бизнеса Server управленческой оболочки Lync Server Management Shell. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.
  
1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. В Windows PowerShell введите следующее:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Пример:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > С помощью параметра GlobalSettingsDomainController можно указать место, где хранятся глобальные параметры. Если параметры хранятся в контейнере System (что характерно для развертывания обновлений, которые не переносили глобальный параметр в контейнер Configuration), вы определяете контроллер домена в корне леса служб домена Active Directory. Если глобальные параметры размещены в контейнере конфигурации (что типично для новых или обновленных развертываний, в которых глобальный параметр был перенесен в контейнер конфигурации), определите любой контроллер домена в лесу. Если этот параметр не указан, то в этом документе предполагается, что параметры хранятся в контейнере Configuration и ссылаются на любой контроллер домена в Active Directory. 
  
    Если параметр Domain не указан, в качестве значения используется локальный домен. Если подготовка домена прошла успешно, командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.
    

