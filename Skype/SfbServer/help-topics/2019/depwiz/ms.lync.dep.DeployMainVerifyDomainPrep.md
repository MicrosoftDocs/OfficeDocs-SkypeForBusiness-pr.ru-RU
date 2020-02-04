---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы убедиться в том, что подготовка домена была выполнена на этапе 1: подготовка схемы, необходимо выполнить командлет из командной консоли управления сервером Skype для Business Server Management Shell (Lync). Чтобы запустить командлет Windows PowerShell, войдите в систему на компьютере, который входит в состав домена, который вы подготовили, и в качестве участника группы администраторов домена. Выполните указанные ниже действия.'
ms.openlocfilehash: 7a9b8e90ce3c7c65f5f4b3d160ca7379b3bf8910
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705422"
---
# <a name="verify-replication-in-the-domain"></a>Проверка репликации в домене
 
Чтобы убедиться в том, что подготовка домена была выполнена на **этапе 1: подготовка схемы**, необходимо выполнить командлет из командной консоли управления сервером Skype для Business Server Management Shell (Lync). Чтобы запустить командлет Windows PowerShell, войдите в систему на компьютере, который входит в состав домена, который вы подготовили, и в качестве участника группы администраторов домена. Выполните указанные ниже действия.
  
1. Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.
    
2. В Windows PowerShell введите следующую команду:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Например:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Параметр GlobalSettingsDomainController позволяет указать место хранения глобальных параметров. Если параметры хранятся в системном контейнере (обычно это происходит при развертывании обновлений без глобального параметра, перенесенного в контейнер конфигурации), вы можете определить контроллер домена в корне леса доменных служб Active Directory. Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу. Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory. 
  
    Если параметр Domain не указан, в качестве значения используется локальный домен. В случае успешной подготовки домена этот командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.
    

