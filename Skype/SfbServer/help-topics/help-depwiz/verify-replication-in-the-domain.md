---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: Чтобы проверить репликацию подготовки домена, выполненной на шаге 1 "Подготовка схемы", необходимо выполнить из оболочки управления Skype для бизнеса Server Lync Server. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.
ms.openlocfilehash: d002a0623d6788183a5b09f8e58262fc1c68a823
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800599"
---
# <a name="verify-replication-in-the-domain"></a>Проверка репликации в домене
 
Чтобы проверить репликацию подготовки домена, выполненной на шаге **1**"Подготовка схемы", необходимо выполнить из оболочки управления Skype для бизнеса Server Lync Server. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.
  
1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. В Windows PowerShell введите следующее:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Пример:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > С помощью параметра GlobalSettingsDomainController можно указать место, где хранятся глобальные параметры. Если параметры хранятся в контейнере System (что обычно используется в развертываниях обновления, в которых глобальный параметр не был перенесен в контейнер Configuration), необходимо определить контроллер домена в корне леса доменных служб Active Directory. Если глобальные параметры размещены в контейнере конфигурации (что типично для новых или обновленных развертываний, в которых глобальный параметр был перенесен в контейнер конфигурации), определите любой контроллер домена в лесу. Если этот параметр не указан, он предполагает, что параметры хранятся в контейнере Configuration и ссылаются на любой контроллер домена в Active Directory. 
  
    Если параметр Domain не указан, в качестве значения используется локальный домен. Если подготовка домена прошла успешно, командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.
    

