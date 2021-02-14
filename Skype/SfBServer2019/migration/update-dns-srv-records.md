---
title: Обновление записей DNS SRV
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
description: Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753271"
---
# <a name="update-dns-srv-records"></a>Обновление записей DNS SRV

Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
  
В этом разделе описывается обновление записей DNS после перехода на Skype для бизнеса Server 2019. After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain. В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Настройка DNS-записи SRV

1. На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.
    
2. В дереве консоли для домена SIP разйдите зоны **"Вперед** и просмотр", разойдите домен SIP, в котором установлен Skype для бизнеса Server 2019, и перейдите к _tcp параметров. 
    
3. В правой области щелкните правой кнопкой **мыши** _sipinternaltls выберите **"Свойства".**
    
4. В **хост-сервере,** предлагая эту службу, обновим его, указав на пул Skype для бизнеса Server 2019.
    
5. Нажмите кнопку **ОК**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition

1. Войдите на клиентский компьютер в домене.
    
2. Нажмите кнопку **Пуск** и выберите команду **Выполнить**.
    
3. В поле **"Открыть"** введите cmd и нажмите кнопку **"ОК".**
    
4. В командной подсказке введите nslookup _\<FQDN of the Front End pool\>_ или , а затем нажмите  _\<FQDN of the Standard Edition server\>_ ввод.
    
5. Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.
    

