---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Для проверки репликации подготовки домена, выполненной в шаге 1: Подготовка схемы, необходимо выполнить командылет из Skype для бизнеса Server shell управления Lync Server Management Shell. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.'
ms.openlocfilehash: 86a58198797b40942e5ac165065a4fda17add9e9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404321"
---
# <a name="verify-replication-in-the-domain"></a>Проверка репликации в домене
 
Для проверки репликации подготовки домена, выполненной в шаге **1:** Подготовка схемы, необходимо выполнить командылет из Skype для бизнеса Server управленческой оболочки Lync Server Management Shell. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.
  
1. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку **Skype для бизнеса и** нажмите кнопку Skype для бизнеса Server **управленческой оболочки**.
    
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
    

