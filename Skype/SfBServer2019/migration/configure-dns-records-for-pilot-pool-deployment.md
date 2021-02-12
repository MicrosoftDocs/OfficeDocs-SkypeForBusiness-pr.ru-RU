---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Перед развертыванием пилотного пула необходимо обновить записи DNS Host A для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754059"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Настройка DNS-записей для развертывания пилотного пула

Перед развертыванием пилотного пула необходимо обновить записи DNS Host A для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Настройка записей A узла DNS

1. На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.
    
2. В дереве консоли домена разйдите зоны прямого подсмотра **и** щелкните правой кнопкой мыши домен, в котором будет установлен Skype для бизнеса Server 2019.
    
3. Выберите команду **Создать узел (A или AAAA)**.
    
4. Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).
    
5. Щелкните **IP-адрес** и введите IP-адрес для пула переднего входа.
    
6. Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**. 
    
7. По завершении нажмите кнопку **Готово**.
    

